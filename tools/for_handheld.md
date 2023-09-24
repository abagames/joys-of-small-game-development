## ハンドヘルドデバイスでもゲームを動かそう

最近は、Arduino [^1] を代表とするワンボードマイコンをコアとし、それにディスプレイやボタンを追加したハンドヘルドゲーム機を DIY で作るというトレンドがある。自分好みのゲーム機を自由に作れるのが利点である一方、様々なデバイスが乱立してしまい、多くの人が持っている共通のデバイスというものはあまり無い。

これらのデバイスで動作するためのゲームは、C 言語で書かれることが多い。なので付随するライブラリも C 言語で実装する必要がある。

今回、私はブラウザ向けに JavaScript (TypeScript)で実装した自作ライブラリを C 言語に移植した。名前を crisp-game-lib-portable [^2] という。

![PyBadge crisp-game-lib-portable screenshot](https://abagames.github.io/crisp-game-lib-portable/screenshotPyBadge.gif)

crisp-game-lib-portable で作ったゲームは、M5StickC PLUS [^3] や Adafruit PyBadge [^4] などで動く。また、Emscripten [^5] を活用することで、ブラウザでも遊べるようにした。

また、ライブラリ本体 [^6]と ゲームのコード [^7]はブラウザを含むすべてのデバイス向けで共通、デバイス向けには最小限の個別コードを書けば対応できる、というのを目指している。

デバイス個別コードで書かないといけない処理は、

- デバイスの初期化処理（Arduino なら`setup()`）とそこからの`initGame()`の呼び出し。
- フレームの更新処理（Arduino なら`loop()`）とそこからの`setButtonState()`呼び出しによるボタン状態の通知と`updateFrame()`の呼び出し。
- machineDependent.h [^8] で定義された描画や音周りの処理。

だけである。そのため、一般的なデバイスで固有に必要な実装は 250 行程度だ。

音回りの実装は`md_playTone(float freq, float duration, float when)`で特定の周波数を、特定の期間、特定の開始時間で鳴らすことを要求していて、デバイスごとにこれに対応することが多少面倒かもしれない。PyBadge のようなブザー音量が`analogWrite()`で設定できる機能しか無いデバイスだと、音のタイミング管理をしつつ、矩形波を自力で生成しないといけない。

`md_drawCharacter(unsigned char grid[CHARACTER_HEIGHT][CHARACTER_WIDTH][3], float x, float y, int hash)`でドット絵を表示する機能も少し手間がかかる。最後にハッシュ値が付いているのは、毎回ドット絵のパターン定義をパース・描画するのではなくて、ハッシュ値でキャッシュしておいてそれを使う実装を想定している。LovyanGFX ライブラリ [^9] を使って描画しているならば、`LGFX_Sprite`とハッシュ値をペアで保存しておいて、それを取り出して`pushSprite()`すれば良い。

こういった移植性を考えながらコードを書くことは、色々なデバイスを相手にしたライブラリでないとできないことなので、なかなか楽しい経験ではある。あまたあるマイコンボードに対して、Arduino IDE などの共通な開発環境、Adafruit Arcada [^10] や LovyanGFX などの多デバイス対応ライブラリを駆使しつつ独自のゲームライブラリを作るのは、PC やスマホをターゲットとしたゲームライブラリとはまた違った面白さがある。興味があれば試していただきたい。

---

[^1]: [Arduino](https://ja.wikipedia.org/wiki/Arduino)
[^2]: [crisp-game-lib-portable](https://github.com/abagames/crisp-game-lib-portable)
[^3]: [M5StickC PLUS](https://shop.m5stack.com/products/m5stickc-plus-esp32-pico-mini-iot-development-kit)
[^4]: [Adafruit PyBadge](https://learn.adafruit.com/adafruit-pybadge)
[^5]: [Emscripten](https://emscripten.org/)
[^6]: [crisp-game-lib-portable src/lib](https://github.com/abagames/crisp-game-lib-portable/tree/main/src/lib)
[^7]: [crisp-game-lib-portable src/games](https://github.com/abagames/crisp-game-lib-portable/tree/main/src/games)
[^8]: [machineDependent.h](https://github.com/abagames/crisp-game-lib-portable/blob/main/src/lib/machineDependent.h)
[^9]: [LovyanGFX](https://github.com/lovyan03/LovyanGFX)
[^10]: [Adafruit Arcada](https://github.com/adafruit/Adafruit_Arcada)
