## ターゲットデバイスと開発環境、何向けに何で作ろうか

じゃあ小さなゲームを作ってみようか、と思ったときに、まず考えないといけないことの一つに、PC、スマホ、ゲーム機などなど、どのデバイスで動くゲームを作るかということがある。

特にこだわりがないのであれば、PC の Web ブラウザ向けのゲームを作るのがおススメだ。今のブラウザは様々な開発環境で開発されたゲームを動作させるためのプラットフォームとして成熟しているし、他の人にプレイしてもらうにも、ネット上の URL 告知からシームレスに遊んでもらえてお手軽だ。

ゲーム作りを楽しむ、という面では、どの開発環境・プログラミング言語・ゲームエンジンでゲームを作りたいか、から考える手もある。これについては小さなゲームだからどうこう、ということは特になくて、自分の好みで決めて良いと思う。ただ、重厚な 3D ゲームを主なターゲットとしている Unreal Engine [^1] などは小さなゲームを作るにはリッチすぎる、などは考慮しても良いかもしれない。

ブラウザ向けに作るとして、開発環境の選択肢は色々ある。

- JavaScript

ブラウザで動くプログラムは JavaScript で書く。だからゲームも JavaScript で書こう、というのは自然な発想だ。p5.js [^2] や Phaser [^3] などのライブラリを利用することで、画面描画などの面倒な部分を楽して書くことができる。p5.js なら、文系大学生のための p5.js 入門 [^4] や p5.js 日本語リファレンス [^5] を見ながら、p5.js web editor [^6] を使えば、すぐに始めることができる。

- ファンタジーコンソール

ゲームの実行環境と開発環境、キャラクタ・レベル・音のエディタなどを内包した、軽量なゲームエンジンをファンタジーコンソールと呼ぶ。代表的なものとしては PICO-8 [^7]、Pyxel [^8]、TIC-80 [^9] などがある。オールインワンの環境で、機能も意図的に絞られているため、小さなゲームを作るには良い選択だ。それぞれ使えるプログラミング言語などが異なるので、自分の好みのものを見つけると良い。PICO-8 を試してみるなら、PICO-8 日本語版マニュアル [^10] や PICO-8 API 早見表 [^11] を見ながら、PICO-8 Education Edition [^12] を使ってみよう。

- ゲームエンジン

Unity [^13]、GameMaker [^14]、Godot [^15]、など多くのゲームエンジンは、ブラウザ (HTML5)向けにゲームをエクスポートすることができ、ブラウザ上で作ったゲームを遊ぶことができる。画像や音などのアセット管理機能が充実していたり、ブラウザだけでなく PC・スマホ向けにもゲームをリリースできるなど、採用するメリットは大きい。

- ツクール

RPG が作りたい、ノベルゲームが作りたい、などのジャンルが決まっているのであれば、専用のツールが使える。RPG ツクール MV [^16] に代表されるツクールが歴史的にも有名なため、このカテゴリのツールは伝統的にツクールと呼ばれがちだ。RPG ツクール以外にも WOLF RPG エディター [^17] などもあるし、ノベルゲームならティラノスクリプト [^18] などがある。最近の多くのツクールはブラウザ向けのエクスポート機能を備えている。

- ビジュアルプログラミング言語

テキストベースのプログラムにそもそも慣れていない場合は、Scratch [^19] や MakeCode [^20] などのビジュアルプログラミング言語が利用できる。複雑なゲームを作ることは大変だが、あらかじめ絵や音なども用意されていて、小さなゲームであれば十分に制作することができる。

- 他のプログラミング言語

今のブラウザは、JavaScript 以外の言語も WebAssembly [^21] などの技術を活用することで動作させることができる。ただし動作させるためのコンパイルなどの作業が複雑なことも多く、可能であれば上記ファンタジーコンソールやゲームエンジンの助けを借りた方が良い。Python で作りたかったら Pyxel、C#で作りたかったら Unity、など。HSP [^22] など、オフィシャルで対応している言語は手間は少なくて済みそうだ。

<br>

ブラウザ向けに作る場合、タッチ操作（PC 上ではマウス操作）のみでゲームを操作可能にすることで、スマホ対応を行うこともできる。より多くの人に遊んでもらいたい場合は検討したい。

ゲームを作る体験それ自身を楽しみたい、という面では別にブラウザ向けにこだわる必要もない。PC 用アプリやスマホ用アプリでもよい。プチコン 4 [^23] などを使って Switch 向けゲームを作っても良い。MakeCode で作ったゲームは好きなハンドヘルドデバイス [^24] で遊ぶこともできる。PICO-8 用ゲームをハンドヘルドデバイスで動かしている [^25] 人もいる。多くの人に手軽に遊んでもらいたい！という考え方だけでなく、このデバイス向けに作ってみるのが面白そう！というモチベーションで作るのも楽しい。自由に作ろう。

---

[^1]: [Unreal Engine](https://www.unrealengine.com/ja/)
[^2]: [p5.js](https://p5js.org/)
[^3]: [Phaser](https://phaser.io/)
[^4]: [文系大学生のための p5.js 入門](https://zenn.dev/ojk/books/intro-to-p5js)
[^5]: [p5.js 日本語リファレンス](https://processing-fan.firebaseapp.com/refer.html)
[^6]: [p5.js web editor](https://editor.p5js.org/)
[^7]: [PICO-8](https://www.lexaloffle.com/pico-8.php)
[^8]: [Pyxel](https://github.com/kitao/pyxel/blob/main/docs/README.ja.md)
[^9]: [TIC-80](https://tic80.com/)
[^10]: [PICO-8 日本語版マニュアル](https://raw.githubusercontent.com/kitao/pico8-jp/master/pico8-jp.txt)
[^11]: [PICO-8 API 早見表](https://kitao.github.io/pico8-api-jp/)
[^12]: [PICO-8 Education Edition](https://www.pico-8-edu.com/)
[^13]: [Unity](https://unity.com/ja)
[^14]: [GameMaker](https://gamemaker.io/ja-JP)
[^15]: [Godot](https://godotengine.org/)
[^16]: [RPG ツクール MV](https://rpgmakerofficial.com/product/mv/)
[^17]: [WOLF RPG エディター](https://www.silversecond.com/WolfRPGEditor/)
[^18]: [ティラノスクリプト](https://tyrano.jp/)
[^19]: [Scratch](https://scratch.mit.edu/)
[^20]: [MakeCode](https://www.microsoft.com/ja-jp/makecode)
[^21]: [WebAssembly](https://developer.mozilla.org/ja/docs/WebAssembly)
[^22]: [hsp3dish.js プログラミングガイド](https://www.onionsoft.net/hsp/v34/doclib/hsp3dish_js.htm)
[^23]: [プチコン 4](https://www.petc4.smilebasic.com/)
[^24]: [MakeCode ハードウェア](https://arcade.makecode.com/hardware)
[^25]: [【RG351P】PICO-8 を動かして CELESTE を遊ぼう](https://yoshives.com/rg351p-pico8-celeste/)
