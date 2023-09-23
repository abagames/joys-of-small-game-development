## ゲームメカニクスをチャット AI に教えたら

前の章で、アクションミニゲームのゲームメカニクスをタグとして列挙するということを行った [^1]。このタグの使い方として、複数のタグを適当に組み合わせてそれら仕組みを使ったゲームを考える、ということを示したが、これを ChatGPT にしてもらうことで、新たなゲームが考えられるかもしれない。

ChatGPT に以下のプロンプトを与えて、ゲームデザイナーとして振舞ってもらう。

> I want you to act as a game designer. Remember the following tags related to game mechanics. The tags are written in a format of 'Category: Name, "Description"', with one line for each tag. Randomly combine those tags and come up with a new game that contains only the game mechanics corresponding to that tag. Make that game an action mini-game that utilizes only a single button. The maximum number of tags that may be combined is 5. Describe what kind of game it is and the selected tags. Try to devise 5 different games without using the same game mechanic tags as much as possible.
>
> player: rotate, "The player character rotates."<br>
> player: reciprocate, "The player character reciprocates horizontally or vertically."<br>
> player: reflect, "The player character reflects upon colliding with a wall or object."<br>
> ...

以下タグ一覧ファイル [^2] にあるタグとその概要説明が続く。プロンプト全体は、それらタグを全て記載したものになる [^3]。

すると以下のような回答が得られる。

> Game 1: Scaffold Jump<br>
> Selected tags: player: scaffold, on pressed: jump
>
> Description: In this game, the player controls a character that moves along scaffolds. The character constantly moves forward, and the player can make the character jump by pressing the button. The objective is to avoid falling off the scaffolds or hitting obstacles while collecting coins or power-ups. The game gets progressively faster and more difficult as the player advances.
>
> Game 2: Pinball Panic<br>
> Selected tags: player: circle, weapon: bounce, field: pins, on pressed: shoot
>
> Description: In this game, the player controls a circular character that bounces around a pinball-like field. The player can shoot projectiles by pressing the button, which bounce off the pins and destroy enemies. The objective is to survive as long as possible while racking up points by destroying enemies and collecting power-ups.
>
> Game 3: Springy Strings<br>
> Selected tags: player: string, player: bounce, field: gravity, on pressed: jump
>
> Description: In this game, the player controls a spring-like character that bounces around a zero-gravity field. The character can jump by pressing the button, which sends it bouncing higher into the air. The objective is to avoid obstacles and enemies while collecting power-ups and reaching the end of the level.

> Game 4: Wipeout Warriors<br>
> Selected tags: player: bar, field: water, obstacle: chase, weapon: wipe, on pressed: jump
>
> Description: In this game, the player controls a bar-shaped character that races through a water course filled with obstacles and enemies. The character automatically moves forward, and the player can make the character jump by pressing the button. The character can also use a wiping weapon to clear the way of obstacles and enemies. The objective is to reach the end of the course in the shortest time possible.
>
> Game 5: Color Conundrum<br>
> Selected tags: rule: match, rule: time limit, field: roughness, on pressed: turn
>
> Description: In this game, the player controls a character that must navigate a rough terrain while matching colors. The character automatically moves forward, and the player can turn left or right by pressing the button. The objective is to match as many colors as possible before the time runs out, while avoiding obstacles and enemies on the way.

ゲーム名と選択したタグ、ゲームの内容が出力される。ここから面白そうなゲームをピックアップすれば、ゲームアイデアとして使えるかもしれない。

例えばゲーム 2「ピンボールパニック」を考えてみよう。ピンボールのようなフィールドにピンや敵がいて、ボタンを押すと発射される球で敵を破壊する。ピンで跳ね返る球をうまく制御して敵に当てる必要がある。球をピンボールのフリッパーで打ち出すようにしても面白そうだ。

ゲーム 3「スプリンギーストリングス」はどうだろう。重力の無い空間を、バネの伸縮を利用して障害物や敵をかわしながら進んでいく。障害物を蹴って進んだり、腕の振りなどで推進するゲームだろうか。

ゲーム 5「カラーコンランダム」は、デコボコした地形の上を、ボタン操作で左右に曲がるプレイヤーキャラクタを操作して、色をマッチさせながら進む。見下ろし型のゲームで、出っ張った地形を避けつつ、同色のカラーアイテムを集めるようなゲームが思いつく。

このまま ChatGPT がゲームの実装をしてくれるととても楽なのだが、さすがにそれはまだ無理だ。'Implement Game 1 in p5.js.'のように頼むと一応頑なんらかのコードは出力されるが、これらゲームメカニクスを正しくは反映できない。

ChatGPT にゲームメカニクスのタグを教え、それらを組み合わせてもらう。ゲームアイデアのベースを考えるには良い方法ではないだろうか。こういったブレーンストーミング的な使い方には ChatGPT はよくマッチする。

---

[^1]: [ゲームを仕組みに分解し、組み立てる](../ideas/break_down_game.html)
[^2]: [action-mini-game-mechanic-tags/src/tags.csv](https://github.com/abagames/action-mini-game-mechanic-tags/blob/main/src/tags.csv)
[^3]: [combine_tags_with_chatgpt.md](https://github.com/abagames/action-mini-game-mechanic-tags/blob/main/combine_tags_with_chatgpt.md#prompt)
