## ファンタジーコンソールを自作する

ファンタジーコンソール [^1] は、こんなゲーム機があったら面白いなという開発者の妄想を具現化したものだ。実在しなかった別のゲームボーイやファミコンを勝手に考えて PC 上で実装して遊ぶ、それがファンタジーコンソールだ。

ファンタジーコンソールの代表例はなんといっても PICO-8 [^2] だ。128x128 ドットの画面、4 音同時再生、256 個の 8x8 スプライトを持ち、Lua での開発環境やドット絵エディタ、音楽エディタ、マップエディタなどを含むとてもリッチなマシンだ。

コンソール（Video game console [^3] = ゲーム機）という名前にもかかわらず、ファンタジーコンソールは開発環境を内包した作りになっていることが多い。どちらかというと MSX のようなマイコンやファミリーベーシックっぽいものになっている。

PICO-8 レベルのファンタジーコンソールを作るのはとても大変だ。しかし自分でもファンタジーコンソールを作ってみたい。ならば思いっきり仕様を絞る必要がある。ごく小さな画面、単純な音出力、簡素な入力手段しか持たないファンタジーコンソールを目指した結果、PEEKPOKE [^4] というファンタジーコンソールを作ってみた。

PEEKPOKE は、PC やスマホのブラウザで遊べる（下の画面をクリック）。

[![BOMB SNAKE](https://raw.githubusercontent.com/abagames/peekpoke/main/docs/screenshot.gif)](https://abagames.github.io/peekpoke/bombsnake/)

上下左右 or WASD キーで蛇を動かして赤い爆弾を取るスネークゲームだ。スマホでも画面下のバーチャルパッドで操作できる。

![PEEKPOKE memory map](https://raw.githubusercontent.com/abagames/peekpoke/main/docs/memorymap.png)

PEEKPOKE では peek 命令と poke 命令しかマシンの制御に使えない。32x30 ドット 8 色の画面と 8x5 のテキスト画面、7 つのキー入力、単音ブザーのみ、という限定された機能を、メモリから操作できるメモリマップド I/O [^5]にあんっている。開発環境は入っていない。ゲームは JavaScript で記述できる [^6]。

コンソール独自の機能はすべてメモリに押し込んだうえで、開発環境は JavaScript に丸投げしたので、作りはかなり簡単にできた。作れるゲームもかなり簡単なものに限られるが、ぎりぎりファンタジーコンソールを名乗れるのではないか。あと起動時にスプラッシュスクリーンを入れると、なんとなくファンタジーコンソールっぽくなる。

開発環境抜きであればファンタジーコンソールを作る手間はだいぶ削減できるので、何か面白いスペックのコンソールを妄想して作ってみるのも楽しい。今回作ったものはだいぶ素直なアーキテクチャのものだが、もっと変わった機能を持ったコンソールだったり、カセットビジョンや ATARI 2600 などの既存コンソールをオマージュしたものなどを考えてみるのも楽しそうだ。

---

[^1]: [ファンタジーコンソール](https://ja.wikipedia.org/wiki/%E3%83%95%E3%82%A1%E3%83%B3%E3%82%BF%E3%82%B8%E3%83%BC%E3%82%B3%E3%83%B3%E3%82%BD%E3%83%BC%E3%83%AB)
[^2]: [PICO-8](https://www.lexaloffle.com/pico-8.php)
[^3]: [Video game console](https://en.wikipedia.org/wiki/Video_game_console)
[^4]: [PEEKPOKE](https://github.com/abagames/peekpoke)
[^5]: [メモリマップド I/O](https://ja.wikipedia.org/wiki/%E3%83%A1%E3%83%A2%E3%83%AA%E3%83%9E%E3%83%83%E3%83%97%E3%83%89I/O)
[^6]: [peekpoke bombsnake/main.js](https://github.com/abagames/peekpoke/blob/main/docs/bombsnake/main.js)
