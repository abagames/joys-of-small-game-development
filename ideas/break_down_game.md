## ゲームを仕組みに分解し、組み立てる

ゲームのアイデアの考え方として、今まで作ったゲームがどのような仕組みから出来上がっていて、その仕組みがプレイヤーにとってどのような楽しさや難しさを提供しているかを整理し、それら仕組みを組み合わせて新たなゲームを作る、という方法も考えられる。

一例として、今まで私が作ってきたゲームを仕組みに分解してみた。各ゲームが、どのようなプレイヤーキャラクタ、武器、障害物、フィールド、ルール、操作から構成されているかを、カテゴリごとのタグで整理した [^1]（画像クリックでトップページへ移動）。

<a href="https://abagames.github.io/action-mini-game-mechanic-tags/index_ja.html"><img src="https://abagames.github.io/action-mini-game-mechanic-tags/twitter_card_image.png" alt="action-mini-game mechanic tags" width="600" /></a>

各タグの詳細（Detail）ボタンを押すと、それぞれのタグの説明、およびそのタグが付加されたゲームの一覧を見ることができる。

タグには、例えば以下のような仕組みが対応している。

- プレイヤーキャラクタが回転する [^2]：回転のタイミングに合わせて操作する。
- 武器が放物線状に飛ぶ [^3]：投げ方や投げるもの、着弾した時の効果などにバリエーションがある。
- ペナルティのある物を混ぜる [^4]：何も考えずに攻撃を続けるのではなく、画面の状況をよく見て攻撃タイミングを図る必要がある。
- 1D フィールド [^5]：ゲーム画面が 1 次元でも表現でき、キャラクタは左右（もしくは上下）にしか動けない。
- 近接ボーナス [^6]：障害物の近くにボーナス点を配置することで、リスク・リワードの基本形が実現できる。
- ボタンを押したら属性反転 [^7]：特殊なプレイヤー操作の一例である。

これらページの使い方としては、以下を想定している。

- タグ一覧ページを見てアクションミニゲームに組み込める仕組みを把握する。
- タグ詳細ページを見てその仕組みを使った別のゲームを考える。
- 複数のタグを適当に組み合わせてそれら仕組みを使ったゲームを考える。

こういったゲームの仕組みは、よくゲームメカニクスと呼ばれる [^8]。

ゲーム内でとれるプレイヤーの行動や、その行動に対応して起こるゲーム内の出来事などを整理したものがゲームメカニクスだ。あるゲームがどのようにデザインされているかを解析するためや、新たなゲームを考える際の助けとして使われたりする。ゲームプレイはゲームメカニクスの間のフローと言われたりする [^9] が、ゲームメカニクスをベースに、それらを組み合わせたゲームプレイ体験をどのようにするか、プレイヤーに対するチャレンジをどう与えるかなどを考えることができる。

ゲームメカニクスとしてどの程度の粒度のものを挙げるべきかは、特に決まった指標が無いように思える。ターン、リソース管理、リスクとリワード、など抽象的な要素をメカニクスとして挙げる場合もあれば、ジャンプ、シールド、回転、パワーアップなど細かなゲーム内アクションを挙げる場合もある。

今回は新しいアクションミニゲームを考える助けになるために、という目的のもと整理し、後者の細かなゲーム内アクションに近い粒度でまとめた。あと各メカニクスに対してそれを取り入れた実例が見えることが、そのメカニクスをどのように他のメカニクスと組み合わせているか、どのようなリスク（チャレンジ）やリワードをプレイヤーに与えているかを把握することを重視し、実例のゲームが見られて遊べるようにした。

自作ゲームを例に整理したので、アクションミニゲーム、とくにワンボタンゲームに偏重した内容になっていることは否めないが、今回はゲームアイデアの発想法の一例として示した。

---

[^1]: [action-mini-game-mechanic-tags](https://github.com/abagames/action-mini-game-mechanic-tags)
[^2]: [回転する](https://abagames.github.io/action-mini-game-mechanic-tags/player_rotate_ja.html)
[^3]: [重力の影響を受けて砲弾のように放物線状に飛ぶ](https://abagames.github.io/action-mini-game-mechanic-tags/weapon_artillery_ja.html)
[^4]: [接触したり破壊したりすることでペナルティになる物が混在している](https://abagames.github.io/action-mini-game-mechanic-tags/obstacle_penalty_ja.html)
[^5]: [1 次元に制限されたフィールド](https://abagames.github.io/action-mini-game-mechanic-tags/field_1D_ja.html)
[^6]: [リスクに近接すると点が入る](https://abagames.github.io/action-mini-game-mechanic-tags/rule_proximity_bonus_ja.html)
[^7]: [属性や状態を反転させる](https://abagames.github.io/action-mini-game-mechanic-tags/on_pressed_reverse_state_ja.html)
[^8]: [Game mechanics](https://en.wikipedia.org/wiki/Game_mechanics)
[^9]: [Video Game Mechanics: A Beginner’s Guide (with Examples)](https://gamedesignskills.com/game-design/video-game-mechanics/#ancor4)
