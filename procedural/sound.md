## BGM や効果音の自動生成

小さなゲームに合う BGM とはどのようなものだろう。一つ考えられるのは、昔のアーケードゲームのような BGM だろう。昔というのはゼビウスとかディグダグとか、1980 年代前半までさかのぼるくらいの昔を想定している。この頃のレトロアーケードゲームの BGM は、4 ～ 8 小節くらいの短いフレーズを繰り返すものがあった。

そのような BGM を自動生成する技術はいくつかある。一つは WolframTones [^1] だ。セルラオートマタを切り出してメロディにする手法である。これはお手軽でよさそうなのだが、16 分音符で完全五度で往復するベースとか、昔のゲームでよく見るフレーズが再現できないのが弱点に見える。

最新のものだと OpenAI の Jukebox [^2] があるが、これは楽譜ではなく音楽の波形を生成するものなので、レトロゲーム向けではない。同様の技術である MusicLM [^3] には 8 bit というサンプルがあり、チップチューンっぽい楽曲も作れるようだ。ただ、まだ表現としてリッチすぎる感じがある。

そこで Magenta [^4]だ。Magenta は Google が開発している、機械学習を音楽や絵に応用するリサーチプロジェクトだ。ブラウザで動かせる実装として、Magenta.js [^5] が公開されている。

Magenta.js は曲の楽譜を入力すると、それに続くフレーズを自動生成してくれる、MusicRNN [^6]を備えている。これにレトロゲームの短い楽譜を与えれば、それっぽい別の曲が生成される。それを簡単に試せるデモプログラムを作成した（画像クリックでデモページへ）[^7]。

<a href="https://abagames.github.io/short-vgm-generator/build/"><img src="https://raw.githubusercontent.com/abagames/short-vgm-generator/main/docs/screenshot.png" alt="Short VGM generator" width="700"/></a>

真ん中の「Generate」ボタンを押すと、画面左のフレーズを元に新たなフレーズを生成し、画面右に表示、再生する。メロディとベースの 2 トラックのみから成るシンプルなフレーズの生成だが、一応それっぽいものが生成できる。複数トラックについては、それぞれ別々にフレーズを作成した上で、ベースがメロディと不協和音だった場合に調整（振動数が 1 ～ 4 くらいの比率になるようにする）している。画面中央下のチェックボックスを外すとこの調整を行わなくなるので、より自由なフレーズが生成される。

Magenta.js の JavaScript からの詳しい使い方については、他の記事 [^8] を参照いただきたい。

効果音の自動生成については、メロディをターゲットとして MusicRNN では対応が難しいと思われる。その代わりに、sfxr [^9] をベースとした波形生成ベースのものが多数あるので、それらを利用すると良い。これらのツール、ライブラリは、'coin', 'laser'などの音のタイプに対してプリセットの波形パラメタを持ち、それをランダムに変更することで様々な効果音を生成する。アクションゲームなどに簡単な効果音をつけるために活用したい。

---

[^1]: [WolframTones](https://tones.wolfram.com/about/how-it-works)
[^2]: [Jukebox](https://openai.com/blog/jukebox/)
[^3]: [MusicLM: Generating Music From Text](https://google-research.github.io/seanet/musiclm/examples/)
[^4]: [Magenta](https://magenta.tensorflow.org/)
[^5]: [Magenta.js](https://hello-magenta.glitch.me/)
[^6]: [MusicRNN](https://magenta.github.io/magenta-js/music/classes/_music_rnn_model_.musicrnn.html)
[^7]: [short-VGM-generator](https://github.com/abagames/short-vgm-generator)
[^8]: [機械学習・AI で音を作れる「Magenta」の JavaScript 版（Magenta.js）を p5.js Web Editor 上で動かしてみる](https://qiita.com/youtoy/items/32eedd5c5c9280fe3f0f)
[^9]: [sfxr](http://www.drpetter.se/project_sfxr.html)
