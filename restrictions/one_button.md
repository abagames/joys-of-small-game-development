## ワンボタンの可能性

ゲームジャムにおけるインタラクトへの制約において、プレイヤーが使える操作をただ 1 つのボタンに限るという、いわゆるワンボタンゲームのゲームジャムもある。ここで言うワンボタンゲームは、レバーによる移動の他にボタンが 1 つ、といったものではなくて、純粋に 1 つのボタンしか操作に使わないゲームを指す。

ワンボタンゲームの利点は、操作が分かりやすく、タッチデバイスでも操作しやすい点にある。とにかく何かボタンを押せばそれがプレイヤーが取れる動作の全てであり、操作説明がほぼ不要である。またタッチデバイスでも画面中のどこかをタップあるいはホールドすれば操作ができるので、バーチャルパッドでよく起こる、ボタンを押した感触が無いので操作がしずらいという問題が発生しない。

欠点は、当然のことながら、動作にバリエーションを与えるのが難しいことである。レバーがあれば簡単に実現できる左右移動さえ、ボタンを押すと進行方向が反転する、というちょっと特殊な操作にせざるを得ない。

そのため、ワンボタンゲームを作る際に問題になるのは、たった 1 つのボタンによるゲームへのインタラクションに、どのようにバリエーションを与えられるか、という点になる。その点に関して、今まで作ったいくつかのワンボタンゲームを例に整理してみたい。

### 特殊な動作を取り入れる

ボタンを押した瞬間にプレイヤーが以下の動作を行う、というのがワンボタンゲームでは良く見られる。

- 移動方向が反転する、90 度回る。
- ジャンプ、羽ばたく。
- ショットを撃つ。

ボタンで移動方向が反転する例としては、THUNDER というゲームを作った（画像クリックでプレイ）。

[![THUNDER](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/thunder/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?thunder)

2 方向に移動するだけのゲームであれば、障害物やボーナスアイテムなどを工夫して、ワンボタンゲームに仕上げることはできる。が、ワンボタンならではの特徴があるゲームとはあまり言えない。

ボタン操作で発生する動作を、通常のゲームではあまり見かけないものにすれば、ワンボタン操作ならではのゲームであることを、プレイヤーに強く印象づけることができる。

#### 瞬間移動

[![CYWALL](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/cywall/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?cywall)

プレイヤーが移動可能な点を画面上に用意しておいて、押した瞬間に一番近い点へ瞬間移動する。ワンボタンでテンポ良く移動できるのがこの動作の良いところである。

#### 分裂

[![DIVARR](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/divarr/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?divarr)

ボタンを押すたびにミサイルが分裂する。ボタンをバシバシ押すだけで攻撃力アップが楽しめるが、むやみにボタンを押すことを防ぐために撃ってはいけないものを混ぜるなどの工夫が必要になる。

#### 選択

[![JUMP ON](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/jumpon/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?jumpon)

あるポイントで曲がる、床に飛び移るなどの動作を選択する。ここにどっちにいくのかを選択する場所・瞬間がある、というのがプレイヤーにはっきり分かる必要があるので、ゲームフィールドとその見せ方には工夫が必要である。

#### 属性反転

[![NS CLIMB](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/nsclimb/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?nsclimb)

ボタンを押すたびに属性、例えば N 極と S 極が入れ替わる。属性になにを用いるか、それが外界とどのように関わるかを考えるところがゲームの肝になる。

#### その他特殊なもの

[![LADDER DROP](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/ladderdrop/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?ladderdrop)

左右に移動している床とはしごをタイミング良く落とす。落ち物ゲームのワンボタンゲーム化でもある。

[![NUMBER LINE](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/numberline/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?numberline)

流れている数字を合計する。これはあまりに特殊で参考にならないが、ボタンに割り当てる動作はいくらでも考えられるという一例だ。

### ボタン押しっぱなしの活用

ワンボタンゲームはボタンを押した瞬間に何かが起こるのが普通だが、押している間に継続的に何かが起きる、という動作をさせることもできる。

#### 角度や距離を調整する

[![NUMBER BALL](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/numberball/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?numberball)

ゴルフゲームでよくある操作だが、ボタンを押している間打ち出す角度が徐々に増えるので、ちょうどよいタイミングでボタンを放して打ち出す。このゲームは打ち出した数字と床の数字が一致すると床が消えるという謎のルールで、ゴルフとは差別化している。

[![FROOOOG](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/froooog/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?froooog)

カエルが飛ぶ距離を、ボタンを押している時間で決定する。ワンボタンでプレイヤーを上下左右に動かすことは難しいということを強引に解決した一例である。

#### 伸縮する

[![PIN CLIMB](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/pinclimb/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?pinclimb)

ボタンを押している間、棒が伸びて、放すと縮む。伸びたものがなにかに引っかって先に進めるなど、なんらかの地形と組み合わせて使われることが多い。

[![SQUARE BAR](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/squarebar/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?squarebar)

幾何学図形と組み合わせると、伸縮だけで複雑な動きを実現することもできる。

[![TAPE J](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/tapej/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?tapej)

伸ばせば伸ばすほど点が伸びるが、リスクも高まるようにするのも、リスク・リワードのバランスが取れて良い。

#### 防御する・当たらなくなる

[![EMBATTLED](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/embattled/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?embattled)

ボタンを押している間、砲弾に当たらなくなる。そのままだと戦車にひかれて終わるので、ある程度ひきつけたら防御を解いて上下に避けると、戦車同士が勝手に戦ってくれる。

[![REFLECTOR](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/reflector/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?reflector)

敵弾を反射してくれる防御壁が常に下に付いているが、ボタンを押している間は強力な反撃ができる代わりに、防御壁が小さくなる。

[![BAMBOO](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/bamboo/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?bamboo)

ボタンを押していると竹に当たらなくなり、竹の裏をすり抜けることができる。そうすると竹の間に入り込んでバウンドすることができるようになり、素早く竹を刈ることができる。

#### その他特殊なもの

[![CHARGE BEAM](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/chargebeam/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?chargebeam)

エネルギーをチャージする。チャージ量をうまく調整することに意味があるゲームにしないと成り立たない。

[![LASER FORTRESS](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/laserfortress/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?laserfortress)

薙ぎ払う。ショットを撃つの超強力な亜流。敵に味方を混ぜることで、超強力な攻撃が仇になるように調整している。

[![SHINY](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/shiny/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?shiny)

雨が降る・晴れる。雨が降っている間は人が早く移動してくれるので、それを利用して早めに右端まで退避させる。あまりに特殊な動作で、他のゲームには転用できそうに無い。

### 複数の動作の組み合わせ

上記動作を組み合わせるのも王道の作り方だ。

[![SCRAMBIRD](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/scrambird/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?scrambird)

羽ばたき＋ショットや、

[![TILTED](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/tilted/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?tilted)

多段ジャンプ＋移動方向反転、

[![UP SHOT](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/upshot/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?upshot)

ショット＋停止など。

また、ある動作がゲーム内に複数の影響を与えるようにする手もある。

[![BOMB UP](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/bombup/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?bombup)

これはボタンで爆弾を落とす・爆発させるという動作に加えて、その爆風でプレイヤーを吹き飛ばすという影響を与えるようにしてある。そのために爆発させる位置とプレイヤーの位置を調整することで、プレイヤーの移動を制御することができる。こうすることによってかなり複雑な動作をワンボタンで実現できるが、やりすぎると制御が難しくなりすぎるので、加減が重要になる。

### 回転運動との組み合わせ

角度調整に似ているが、プレイヤーや砲身が常に回っていて、タイミングよく飛び出したり撃ったりという、タイミング重視のゲームにする手もある。

[![ORBIT MAN](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/orbitman/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?orbitman)

飛び出し方向が回転しているので、星がある方向にタイミング良く飛び出す。

[![ARCFIRE](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/arcfire/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?arcfire)

砲身が回転しているので、敵を向いている時にタイミングよく撃つ。このゲームでは押しっぱなしで射程と攻撃範囲が調整できたり、発射と同時にその方向に少し前進するなど、いろいろな行動がワンボタンでできるようになっている。

### 地形の活用

入力によって動作にバリエーションをもたせるのが難しいのならば、プレイヤーの立っている地形によって動作が変わるようにするのも良い。

[![TURBULENT](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/turbulent/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?turbulent)

ボタンでジャンプする、という動作に対しても、そのジャンプする地形を荒れた海面にすることで、タイミングによって飛び出す方向を変化させることができる。

[![SUB JUMP](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/subjump/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?subjump)

画面下半分を海中、上半分を空中、とすることで海中ではボタンで上昇、空中ではジャンプと、複数の役割をボタンに持たせることができる。

### アイテムの活用

地形以外にもアイテムを活用する方法もある。アイテムを取るとなにかのモードが変わるようにして、アイテムを取る・取らないという選択を入力の代わりに利用する。

[![MIRROR FLOOR](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/mirrorfloor/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?mirrorfloor)

コインを取るたびに重力方向が切り替わる。次の床の位置をよく見て取るか取らないかを選択しないと、次の床に飛び移ることができなくなる。

[![LIFT UP](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/liftup/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?liftup)

アイテムを取ると進行方向が変わる。左右のトゲトゲにぶつかる前に反転アイテムをうまく取りつつ、コインを集める必要がある。

[![REBIRTH](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/rebirth/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?rebirth)

トラックにひかれて逆の世界へ移動する。トラックがアイテムであるかは議論の余地があるが、次のダイヤの位置を見てトラックにひかれるかひかれないかを選択する。

[![R WHEEL](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/rwheel/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?rwheel)

アイテムを取ると下方向にレーザーを発射して、障害物のトゲを破壊する。このゲームはその他にジャンプすると下方向にトゲを生やすレーザーを発射する、トゲはぐるっと回ってもう一度プレイヤーのところに来る、アイテムはジャンプすることにより出現する、など複数のことがボタンを押すとジャンプするという動作に対して発生するようになっている。

### まとめ

このように、ワンボタンだと大した動作バリエーションを作ることはできないだろう、と考えるのは早計であり、ここに挙げただけでもかなり多様なタイプのゲームを作ることができることが分かった。ワンボタンゲームの持つポテンシャルを活かして、今後も様々なゲームを作ってみたい。

ワンボタンゲームは操作が簡単であることが利点だが、それ故に思わぬ罠にかかる場合がある。それは、ボタンを連打するだけ・押しっぱなしにするだけでいくらでも点が入る、いわゆる永久パターンがあるゲームがたまに出来上がることだ。なので作った後に、必ず連打プレイ・押しっぱなしプレイを行うこと。本人が意図していなくても、そこそこの確率でそういうゲームになることがあるので注意したほうが良い。

あと大前提として、ワンボタンゲームであることと、そのゲームが面白いかつまらないか、ということに因果関係はない。そのため、そのゲームが爽快感・緊張感を備えていること、リスク・リワードのバランスが取れていること、などゲームとしての面白さはちゃんと追求しないといけない。その上で、そのゲームをワンボタンゲームに落とし込めるかを考えることは必要である。
