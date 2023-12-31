## 小さなゲームを作ること、それ自身が楽しいのだ

小さなゲームとは何か。スモールゲームマニフェスト（宣言書）[^1] によれば、1 プレイが 10 分以内に終わる、ブラウザなどで手軽に遊べるゲームを指す。

その定義で言うと、私は小さなゲームをすでに 350 個以上 [^2] 作っていることになる。1 年間で 139 個作ったこともある [^3] 。無類の小さなゲーム好きだ。

赤い棒を等分に切るシンプルなゲーム、例えばこれが小さなゲームだ（以下の画像をクリックすると、ブラウザで直接プレイできる）。

[![TIMBER TEST](https://github.com/abagames/crisp-game-lib-11-games/raw/main/docs/timbertest/screenshot.gif)](https://abagames.github.io/crisp-game-lib-11-games/?timbertest)

タップでひもを切り画面下に触れないようにするゲーム、これも小さなゲームで、スマホなどのタッチパネルデバイスでも楽しめる。

[![C NODES](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/cnodes/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?cnodes)

小さなゲームの何が良いって、短時間で作れるのが良い。速くて 2 時間、ちょっと苦戦しても 10 時間くらいでできるだろう。アートワークなどを凝り始めるといくらでも時間はかけられるが、ここでは 1 週間に 1 つゲームを作る、Game a week [^4] のような取り組みでできる規模の、開発者目線でも小さなゲームとしたい。

短時間で作れるということは、いろんなアイデアを簡単に試すことができるということだ。「ヘンテコにおもしろい小さなゲームを作ろう」[^5] というエッセイを「ゲームクリエイターが知るべき 97 のこと 2」という本に寄稿したのは、だいぶ昔の 2013 年のことだが、そのころから私はちょっと変わったゲームを、いろいろ作って試してみるのが好きなのだ。

なぜ小さなゲームを作るのか。それは小さなゲームを作ることが、より大規模で完成度の高いゲームを作るための準備として大切である、というような話がよくある。ちょっと前に、初めてゲームを作る人向けのアドバイスとして、まず小さなゲームを作れという意見が圧倒的に多いという記事 [^6] があった。

> 「小規模でシンプルなもので構わないから、とにかく完成させリリースするんだ」とアドバイスする。そうした経験を重ねることで、開発のプロセスやツールの扱いに慣れていくとのこと。

"Make and release lots of small games before making a big one"というブログ記事 [^7] でも、大きなゲームを作る前に多くの小さなゲームを作る重要性を述べている。

> 最初のゲームとして大きなゲームにいきなり飛び込むのは、モチベーションを失い、そのゲームを最後までやり遂げることができなかったり、何年もかけて作ったものを見るのも嫌になったりすることにつながる。

でもそれだけじゃないんだ。小さなゲームには小さなゲームにしかない、ある種の魅力がある。そう私は思っている。

"How To Make Good Small Games"というブログ記事 [^8] がある。この記事では、小さなゲームでも優れたものはあり、それをどうやって作るかについて述べている。

> このマニフェストのようなものである「優れたスモールゲームの作り方」は、この視点（小さなゲームは簡単な気晴らしにしかならず、「本物の」ゲームと同列に考えるべきではない）と折り合いをつけようとする試みである。それは 12 の考えに分かれており、主に難解な創造的理論（なぜ私は小さなゲームが好きなのか、なぜ私は小さなゲームを作るのが好きなのか）と、少し実践的なアドバイスで構成されている。あなたに「小さなゲームを作ろう」と言っても、最初から小さなゲームも良いものになると信じていないのであれば、あなたが本当に作りたいゲームを作る前にやらなければならない宿題だとしか聞こえないだろう。

12 の考えとは以下の内容だ。

1. ゲームの質はその規模とは無関係だ：小規模なゲームは作るのが簡単なだけでなく、うまく作るのも簡単である。ゲームが大きければ大きいほど、ゲーム内で気にかけなければならない部分が多くなり、失敗する可能性も高くなる。

2. ゲームの質はその感情的な広がりとは無関係だ：短編小説が長大な小説や叙事詩とは機能が異なるのと同じように、小規模ゲームでは「成功」を構成する条件が異なる。

3. ゲームは自らの成功の条件を定義する：あるがままを受け入れる。そして、そのあるがままが良いかどうかを判断する。

4. ゲームはその約束を果たすことで成功する：新しいキャラクター、新しいメカニクスの登場はすべて約束だ。面白いアイデアを導入してすぐに放棄するのではなく、そのアイデアが発展し、ゲーム全体の展開に関わるものであることを約束する。

5. 小さな約束をしたほうがゲームは成功しやすい：メカニクス、敵、アセット、キャラクター、ステージを少なくする。3 つのアイデアを導入し、満足のいくクライマックスへと発展させるのは、10 や 100 のアイデアよりも簡単だ。

6. 面白く楽しい方法で約束を果たす：何があなたを笑顔にするのか？自分らしいゲームを作るという、あなたの個人的なスタイルが発揮される場所だ。

7. 約束を過剰に果たさないこと：ゲームは長すぎることなく、適切なタイミングで終わること。

8. フォームファクターはゲームの約束事の一部だ：プレイヤーに与える情報を少なくし、ゲームを起動してすぐにプレイを始められるようにすることで、プレイヤーの期待をかわす。

9. ゲームを完成させてからリリースすること：「体験版」と銘打ったり、サブタイトルに「プロローグ」と入れたりしてリリースする前に、なぜゲームが完成する前にリリースしたいのか、自問するべきである。

10. 連作は近道ではない：ゲームをエピソードごとに 2 回以上に分けて、長い期間にわたってリリースすること。これはほとんど常に悪いアイデアだ。

11. 流行る流行らないを心配する必要はない：ゲームで小さく具体的な目標を追求することは、小さく具体的な観客を呼び込むことでもある。

12. 良いものは十分良い：自分が満足できるゲーム、心の底から良いと思えるゲームをコンスタントに作れるようになれば、大多数のゲーム開発者よりも何光年も先に進んでいることになる。

ちなみにこの記事には 13 個目があって、それは"Have fun :)"だ。新しいメカニクスを考えて、それを自分らしい方法でゲームにする。その過程が楽しいから、小さなゲームを作るのだ。それが一定数の人に届いて楽しんでもらえれば、それはさらに嬉しい。

小さなゲームを作ることは、ゲーム開発のスキルアップの文脈で語られることが多い。だけど、いろんなゲームのアイデアを考えて、実験して、うまくいったいかなかったと一喜一憂して、たまにみんなにお披露目する。そういったプロセスそれ自身が楽しめるに越したことはない。

---

[^1]: [Manifesto Jam](https://itch.io/jam/manifesto-jam)という、まずマニフェストを書いてからゲームを投稿する必要がある特殊な Game Jam 向けに書かれた、[小さなゲームのマニフェスト](https://ebeth.itch.io/small-games-manifesto)。

> Small Games should be 10 minutes or less and it's best if they're playable in a web browser.

[^2]: [JavaScript のゲーム](http://www.asahi-net.or.jp/~cs8k-cyu/browser.html)と、[今はもう動作しない Flash のゲーム](http://www.asahi-net.or.jp/~cs8k-cyu/flash.html)、合わせて 350 個以上を制作した。
[^3]: [ゲーム作りをパターン化して 1 年で 139 個のミニゲームを作る](https://aba.hatenablog.com/entry/2021/12/28/192244)
[^4]: [Game A Week の定義まとめ](https://2dgames.jp/game_a_week/)
[^5]: [ヘンテコにおもしろい小さなゲームを作ろう](https://xn--972-o73bf2b4jwbzftixktbzfvb4o4tqfvmg57147a.com/%E3%82%A8%E3%83%83%E3%82%BB%E3%82%A4/%E3%83%98%E3%83%B3%E3%83%86%E3%82%B3%E3%81%AB%E3%81%8A%E3%82%82%E3%81%97%E3%82%8D%E3%81%84%E5%B0%8F%E3%81%95%E3%81%AA%E3%82%B2%E3%83%BC%E3%83%A0%E3%82%92%E4%BD%9C%E3%82%8D%E3%81%86/)
[^6]: [ゲーム開発者らが「初めてゲームを制作する人への、もっとも大事なアドバイス」を SNS 上に続々投稿。“ある意見”だけダントツで多い](https://automaton-media.com/articles/newsjp/20220914-219051/)
[^7]: [Make and release lots of small games before making a big one](https://tylerglaiel.substack.com/p/make-and-release-lots-of-small-games)

> It's here because, jumping straight into a big game as your "first" game is exactly how you end up losing motivation and never finishing that game, or ending up with something that ate years of your life that you can't even stand looking at anymore.

[^8]: [How To Make Good Small Games](https://farawaytimes.blogspot.com/2023/02/how-to-make-good-small-games.html)

> This manifesto of sorts, “How to Make Good Small Games”, is an attempt to meet this perspective halfway. It’s divided into twelve thoughts, made up mostly of esoteric creative theory (why do I like small games? why do I like making small games?), and hopefully a little actionable advice. I can tell you “scope small uwu”, but if you don’t believe small games can be good in the first place, all you’ll hear is a homework assignment you have to do before you can make the games you really care about.
