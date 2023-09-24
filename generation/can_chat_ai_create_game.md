## チャット AI は新しいゲームを作れるのか

ChatGPT を用いたゲーム考案の試みはいくつか考えられるが、新しいゲームを考え、それを実装することは難しいように思える。少なくとも現状の ChatGPT では以下の問題がある。

- ChatGPT に、実装可能なアルゴリズムのレベルまで詳細化された、新しいゲームのアイデアを考えさせるのは難しい。
- ChatGPT は、今までにない新しいアルゴリズムを、ソースコードとして実装することを不得意としている。

### ChatGPT に新しいゲームのアイデアを考えさせるのは難しい

ChatGPT は与えられた問に対して愚直に正しい答えを返すので、単に新しいアクションミニゲームのアイデアを教えて、と聞いても当たり障りのない凡庸なアイデアが返ってくる（以下は GPT-3.5 での入出力例である。また GPT のモデルは逐次改良されるので、異なる結果が得られる場合もある）。

> I want you to act as a game designer. Show me ideas for new action mini-games.

このプロンプトに対する回答例は、以下のような漠然とした当たり障りのないゲームアイデアが返ってきただけだ。

> Certainly! Here are some ideas for action mini-games that could be integrated into a larger video game or used as standalone experiences:
>
> Laser Maze Runner:
>
> The player navigates through a complex maze filled with laser beams. They must use their agility and quick reflexes to dodge and jump over the lasers to reach the exit.

プロンプトの工夫で、ある程度は ChatGPT にありきたりではないゲームを考えさせることができる。ただ、そのような工夫を経ても、返ってきたアイデアはまだぼんやりとしていて、ブレーンストーミングの元ネタにはなるが、ここから具体的なゲームのルール、アルゴリズムまで到達させることは難しい。

より詳細なアルゴリズムにするために、以下のようなプロンプトで、そのゲームの疑似コードを書いてもらうことはできる。

> I want you to act as a game programmer. Write a pseudo code outlining the detailed algorithm representing the rules of the following game:
>
> Game 2: Pinball Panic
>
> Selected tags: player: circle, weapon: bounce, field: pins, on pressed: shoot
>
> Description: In this game, the player controls a circular character that bounces around a pinball-like field. The player can shoot projectiles by pressing the button, which bounce off the pins and destroy enemies. The objective is to survive as long as possible while racking up points by destroying enemies and collecting power-ups.

しかし、結果として出力されるコードにはあまり具体性が無く、実装可能な解像度までは遠い。

### ChatGPT は新しいアルゴリズムを実装するのは不得意

別の問題として、ChatGPT は既存のアルゴリズムを様々なプログラミング言語で実装するのは得意だが、前例の無い新しいアルゴリズムをコードにするのは不得意なのでは、という点がある。

'Can GPT-4 _Actually_ Write Code?'という記事 [^1] には、可能であればなるべく火を通らないように目的地までのパスを探索する、というアルゴリズムを ChatGPT に書かせようとしたがうまくいかなかった、ということが書いてある。一般的な A\*の探索アルゴリズムのコードであれば ChatGPT は難なく出力するが、それをアレンジした要求をするとうまく答えられなくなるという例だ。

ChatGPT はユーザーの要求を解釈してそれに合致する既存コードを持ってくることや、それに対する追加要求に応じてコードを書き換える、といったことは得意だ。だが、今までに無いアルゴリズムやルールを含むコードを生成する能力がどの程度あるのかは未知数だ。

今までにない簡単なゲームの例として、自作したゲームの一つである PIN CLIMB を、なんとかして ChatGPT に書かせられないかということを試していた。

[![PIN CLIMB](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/pinclimb/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?pinclimb)

上記のゲーム実装方法を説明する文章を元に、以下のプロンプトでゲームのアルゴリズムを示す疑似コードを作成し、

<blockquote>
<p>
I want you to act as a game programmer. Write a pseudo code outlining the detailed algorithm for the following game inside one unique code block. Do not write explanations.<br>
# Characters<br>
- bar<br>
- pins<br>
# Controls<br>
- The bar stretches as long as the button is held down and shrinks to a default length when the button is released.<br>
# Rules<br>
- One end of the bar is fixed to the pin and the other end rotates around the pin.<br>
- The game screen scrolls down so that the bar is positioned slightly above the bottom edge of the screen.<br>
- Pins appear at random locations at the top edge of the screen after each scrolling of a certain distance.<br>
- When the bar catches on another pin, the bar is fixed to that pin.<br>
# Initial state<br>
- Pins are placed in about 10 random positions on the screen, and the bar is fixed to the bottom pin.
</p>
</blockquote>

その後、以下のプロンプトで具体的な Phaser のソースコードにする、ということを試した。Phaser を選んだのは、JavaScript ベースのゲームライブラリで一番 Web 上に情報が豊富なのは Phaser だろうという予測の元だ。

> Implement the game using the HTML5 game framework "Phaser 3" without using external resources such as image files or audio files. Just show me the JavaScript source code.

結果としてはうまくいかなかった。最初の疑似コード時点で十分な情報量があるか怪しいものが出てくるし、そこから Phaser への変換もあまりうまくいかない。

疑似コードを挟まず、ピンを書く、スクロールさせる、ひもを回す、のようにステップバイステップで指示して直接ソースコードを書かせても、ひもが他のピンに当たるとそのピンへ固定される、のあたりでうまくいかなくなる。ここの実装難度が高いことは分かる。回転する矩形の当たり判定を取ることも、当たった後にそのピンへ固定することも、両方とも処理としては特殊であり、この辺が限界であっても納得はできる。

### プロンプトの工夫でこれらの課題を乗り越えられる？

分からない。

ゲームのアイデア発想はなるべく自由に、それをルールや実装へ落とすところは具体的に、のようなことをプロンプトでうまく制御するのはかなり難しいのでは、と直感的には思われる。また、モデルの限界はプロンプトでは乗り越えられない。

### GPT-〇〇 になればこの辺の問題は解決される？

分からない。

画像生成 AI の急激な改善を見ていると、半年後にはこの辺の問題は解決するのかもしれない。モデルの規模で乗り越えられる課題なのか、そもそもアプローチとして筋悪なのか、どちらかは現時点では不明だ。

実際、最初に試したアクションミニゲームのアイデアについて、GPT-3.5 でなく GPT-4 に聞いてみると、下記のような少し改良された回答が得られる。

> Certainly! Here are some unique action mini-game ideas:
>
> Asteroid Surfing
>
> Setting: Outer space, amidst a field of rapidly moving asteroids.<br>
> Objective: Ride the largest asteroids and jump between them to reach a goal point in the least amount of time.<br>
> Mechanics: Players must balance on moving asteroids, time their jumps, and avoid smaller, more hazardous space debris.

ゲームアイデアとしてはまだ凡庸だが、より詳細なゲーム内容が得られる。言語モデルの発展と、プロンプトの工夫で、より面白く具体的なゲームが考案できる可能性はある。

### 今でもできる他のアプローチがあるのでは？

分からない。

ポンとかブロック崩しとか、既存のゲームのコードをまず提示させて、そこから対話的に新しい要素を加えていく、のような方法は今でもうまくいく可能性がある。その場合、どのくらいの新しさなら許容されるのか、どの程度細切れに指示するのが効率が良いのか、などのプロンプトエンジニアリングが必要となる。

そのようにゲームを作るのが直接コードを書くのに比べて効率良いかと問われると、おそらく悪いので、これは効率性の問題ではなく、ChatGPT を使ってゲームを作るという縛りプレイとしての楽しさを追い求めることになる。「AI にゲームを作らせるゲーム」という新しいゲームを、旬のうちにいろいろ試してみるのも楽しいだろう。

---

[^1]: [Can GPT-4 _Actually_ Write Code?](https://tylerglaiel.substack.com/p/can-gpt-4-actually-write-code)
