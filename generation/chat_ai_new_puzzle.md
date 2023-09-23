## チャット AI が考えるパズルゲーム]

'ChatGPT invented its own puzzle game.' [^1] という記事で、ChatGPT に今までに無かった新しいロジックパズルを考えてとお願いしたら、Sumplete というゲームが提案されたという話があった。2 次元のグリッド上に数字が、右端と下端に各行と列の数字の合計が書いてあるので、グリッド上の数字に × をつけて、書いてある合計になるようにするゲームだ。

ところがこのゲームは実はすでに存在していた。Summer と呼ばれるスマホ向けゲームだ [^2]。世の中の全てのゲームを知ることは、人にも AI にも無理なので、新しいゲームを考えたけどすでにあったということは往々にしてある。なので本当に新しいかを保証するのは無理だ。

だが、ChatGPT に新しいロジックパズルを考えてもらうのは面白い試みである。例えば、以下のプロンプトを ChatGPT に与えると、いくつかのパズルを提案してくれる。

> I want you to act as a logic puzzle game designer. Devise 5 novel logic puzzles. Create rules that are different from logic puzzles that already exist, such as Sudoku. The puzzle should consist of a two-dimensional grid. Several grids may be divided by walls. The initial state of the cells consists of both cells containing numerals or symbols, as well as empty cells. The player fills in the blank squares and tries to reach the correct solution.

2D のグリッドのいくつかのマスに数字やシンボルが入っていて、空いているマスを埋めるタイプのロジックパズルを 5 つ考えて、というプロンプトである。グリッドは壁で区切られていてもよい。へやわけ [^3] のようなパズルが提案されることを想定している。

いくつかの提案の中に、以下のパズルがあった。

> "Magnet Blocks"
>
> In this puzzle, the grid contains magnets of opposite polarity (north and south). The player must fill in the grid with blocks of positive and negative polarity, such that each block attracts or repels adjacent magnets according to their polarities. A block can only be placed if it fits in with the surrounding magnets, and no two blocks of the same polarity can touch each other.

Magnet Blocks という、磁石を題材にしたパズルのようだ。ChatGPT に日本語への翻訳もしてもらうと以下になる。

> このパズルでは、グリッドには異なる極性（北極と南極）を持つ磁石が含まれています。プレイヤーは、各ブロックが隣接する磁石の極性に応じて引き付けまたは反発するように、正および負の極性のブロックでグリッドを埋める必要があります。ブロックは周囲の磁石に合わせて配置され、同じ極性のブロックは互いに触れてはいけません。

パズルのルールとしてはあまりに漠然としているが、要は磁石を N と N、S と S が触れないように配置するゲームだと解釈し、実装した（画像クリックでプレイ）。

[![Magnet Blocks](https://raw.githubusercontent.com/abagames/crisp-game-lib-11-games/main/docs/magnetblocks/screenshot.gif)](https://abagames.github.io/crisp-game-lib-11-games/?magnetblocks)

具体的なルールは以下になる。

- グリッド上に棒磁石と壁が配置されている
- N と N、S と S が隣接しないように空いているマスに棒磁石を置く。棒磁石は 3 マス以上の任意の長さで置ける
- 全ての空いているマスに棒磁石が置ければクリア

レベル生成ロジックがイマイチのこともあって、パズルとしての深みは出せていないが、一応パズルとして成り立っている。

で、このパズルははたして新しいのか。似たルールのパズルとして、Magnets [^4] というパズルがあった。磁石が題材のところは同じだが、ルールはかなり異なる。

- 棒磁石が置ける場所、方向はあらかじめ決まっていて、長さは 2 で固定
- ＋とーが行と列に何回出現するかの制約がグリッドの外周に書いてある
- 全ての空きマスを埋める必要はない

現時点では同じルールのパズルは見つかってない。だが、磁石モチーフではない同じルールのパズルとかがある可能性はある。

ロジックパズルは様式が定まっていることもあって、その様式の制約をとっかかりに、ChatGPT に新しいルールを考えてもらうモチーフとしては良いように思える。ただ、その定まった様式ゆえに、新しいと思って作ったものが既存のものと一致してしまうことも多いと考えられる。

また、パズルとして成り立つ厳密なルールを ChatGPT に生成させるのは難しいので、あいまいな提案を具体的なルールにするのにはまだ人手がいる。遊べる形のプログラムコードにすることはまだ難しい。

できたパズルが解いていて楽しいかということを判断する、というのもまた別の難しさだ。これはルールだけでなくて、問題の生成ロジックにもかかわってくる。

厳密なルールを作る、などの ChatGPT が不得意とする作業は、ChatGPT とは別の方法、プログラムやプラグインで補うということができれば、チャット AI の応用範囲はさらに広がるだろう。

---

[^1]: [ChatGPT invented its own puzzle game.](https://puzzledpenguin.substack.com/p/chatgpt-invented-its-own-puzzle-game)
[^2]: [Summer](https://play.google.com/store/apps/details?id=com.rohitpailwangames.summerpro)
[^3]: [へやわけ](https://www.nikoli.co.jp/ja/puzzles/heyawake/)
[^4]: [Magnets](https://www.chiark.greenend.org.uk/~sgtatham/puzzles/js/magnets.html)
