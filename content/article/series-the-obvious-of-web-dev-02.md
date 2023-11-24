---
title: "Web開発技術のあたりまえ 2 - 「Web開発技術」って何だろう -"
date: 2023-11-19
toc: true
series:
  - 'Web開発技術のあたりまえ'
categories:
  - 'Web開発技術のあたりまえ'
  - 'Develop'
  - '勉強会'
draft: false
math: true
---

## Web開発技術のあたりまえとは？

---

> 語りえぬものについては、沈黙しなければならない。  
> — _Ludwig Josef Johann Wittgenstein_[^1]

[^1]: [『論理哲学論考』](https://ja.wikipedia.org/wiki/%E8%AB%96%E7%90%86%E5%93%B2%E5%AD%A6%E8%AB%96%E8%80%83)より。

---


「はじめに」で述べた通り、「あたりまえ」とは特定の事象に対して複数の人間が持つメンタルモデルが一致している状態のことを指す。  
特定の事象に対して人間の内面が完全に一致するのは不可能だ。そこで、普通は規範となるべき質の高いモデルを選定し、その合意や理解、実践によって「あたりまえ」としたり、その集団において適切な形になるようにモデルをカスタマイズしたりする。特にシステム開発においては、このような「あたりまえ」の作られ方が非常に多い。

ただ、ベースとなる規範的モデルを選ぼうにも、Web開発技術のモデルを選定しようとするとその時点で足が止まることも多々ある。それも当然で、Web開発技術、もといシステム開発は多数の要素が絡み合い成立している複雑系だからだ。複雑系を知るためにはいくつかのアプローチがあるが、本文ではまず大枠を示した後、複雑系を構成する要素とその要素同士の関係性を知るアプローチの方法を取ろうと思う。

そのモデルはどのような事象をどのような観点から切り抜いて見たのか、そのモデルがどんな業務や所属分野における基礎知識となっていてほしいのか……等々、語るべきことはいろいろとあるが、まず初めにモデルにおいて必要な「何についてのモデルか」という部分、つまり「Web開発技術」という大枠とは何かから始めていこう。

---

### Web開発技術とは何を指すのか

Web開発技術は、システム開発においてもはや触れないで進めることが不可能となるほど巨大な技術体系だ。ほとんどのシステムは、なんらかの形でWeb開発技術を利用しているといっても過言ではない。

このWeb開発とは何なのか、ものすごく乱暴に言ってしまうと **「Webブラウザ上で動くアプリケーションを作る」** ことだ。  
では、Web開発技術とは「Webブラウザ上で動くアプリケーションを作るための技術」のことかと言うと、実は少しだけニュアンスが違う。  
**Web開発技術とは、主にWeb開発で使われる技術である** のは間違いないが、**その技術はWeb開発以外にも利用可能だ。**

例を挙げると、*JSON*なんかが代表的だろう。これはブラウザ上で非同期通信と画面更新を行う技術……いわゆる*Ajax*の普及とともに広まったデータフォーマットで、*JavaScript*のオブジェクトに由来する一定の形式をもった文字列を表す。  
*JSON*は*JavaScript*のみならず、プログラム言語で利用される構造化されたオブジェクトの形を模したものであり、読みやすく、メモリ上のデータに展開しやすいという特徴から、現代では様々なプログラム言語間でデータを共有するフォーマットとして利用されている。これは後述する *Web標準(Web Standard)* の一部であるが、用途はWeb開発に限らず、スタンドアローンで動くプログラムの設定記述フォーマットとしても使われることがある。

加えて、現代はSaaS[^2]の普及により、Webでデータを相互利用するビジネスを実現したいという要求は多いし、今までdllなどのコンパイルされた形式で提供されてきたライブラリが提供元の都合ですべてWeb APIを経由した機能提供に変わったり、組み込み分野でもIoT[^3]を求められるなんてこともあり得るだろう。

**Web開発技術は、システム開発に関わる限り、もはや必須のものとなっている。**  
**今まではブラウザを扱うアプリケーション開発におけるあたりまえであったものが、今やシステム開発に関わるもの全員のあたりまえとして扱われるべき、という世界になっているのだ。**

[^2]: *Software as a Service* の略称。パッケージングされた複数の機能を持つアプリケーションやソフトウェアを旧来のものとしたとき、それに対し、アプリケーションが持つ機能だけを提供する形態のサービスのこと。モノを届けるのではなく利用可能な状態にすることが納品になるような製品、すなわち、現代でインターネットを通じて提供されるブラウザベースのWebサービスはほぼほぼSaaSもしくはXaaS( *X as a Service* 一つの目的を達成するパッケージングではなく、機能を提供する形態全てを差す)であると言っても過言ではない。

[^3]: *Internet of Things* の略称。モノのインターネットとも呼ばれる。インターネットを通じて、ブラウザなどから現実世界に存在する物を操作するリモートコントロールの総称だが、ここにはWeb技術由来の技術が使われている。


---

{{< figure src="https://asset.watch.impress.co.jp/img/iw/docs/1107/574/001.png" width="640" title="図 2-1. スマートスピーカーの世界にブラウザは無いが、構成を見ると、インターネットの仕組みを利用したWebサーバーのようになっている。" caption="[Internet Watch /『呼び掛けにどう応答しているのか？　Amazon EchoやGoogle Homeが動く仕組み』](https://internet.watch.impress.co.jp/docs/column/nettech/1107574.html)より画像引用。">}}

---

### 「広さ」の深堀：Web開発技術についてのモデルの細かなカテゴライズ

Web開発技術と一言で言っても、すべてを把握するのは大変だ。  
Web開発技術という言葉で人が想像するものは多岐にわたるし、そもそも技術体系という広範なものを一見で理解することは難しい。

それでもなお人がモデルを作り出すとき、人は「焦点」と「分類」と呼ばれるものを使ってきた。語るべきものと語らないものについて分け、語るものについてはどのような立場から見て言ったものかを明らかにし、必要なもののみを抜き出す。そして、そうやって抜き出した必要なものを、ある一つの言葉でひとまとめにして、簡単に扱えるようにしていく。

この節では、僕というWebソフトウェア・アプリケーションの開発者の観点から、「Web開発技術」という大きな体系に対し、概ね人はこうやって「Web開発技術」を分類し、切り取って扱っているであろうという考えについての話をする。  
僕が開発者としてモデルを学んできた中で考えてきたことの一つに、「Web開発技術について人がモデルを示すとき、概ね全体のことではなく、あるカテゴリについて観点を置いている」というものがある。これはそういったモデルの焦点、および多くの人に共通するカテゴリの分け方の観測結果について示したものだ。

ただし、ざっくりと挙げても、Web開発技術において知るべきとされる要素のカテゴライズや、現実を切り取るときの切り口……つまり、僕のメタモデルの構成要素には以下のような知識群がある。

- **データ構造とアルゴリズム**
- **プログラミング**
- **プログラミングパラダイム**
- **システム開発のメソドロジー**
- **プラクティス**
- **ブラウザの仕組み**
- **Web標準とインターネットプロトコル**
- **主要なWebシステムのソフトウェアアーキテクチャスタイル**
- **ライブラリとツール**
- **テクノロジースタック・ツールチェイン・エコシステム**
- **フレームワーク**
- **トレンド**

ちょっと挙げただけでも盛りだくさんだ。だが、これらのカテゴリに含まれる詳細な要素はともかく、カテゴリ自体について避けて通ることはできない。  
単語を挙げただけでは僕自身のメンタルモデルは伝わらないと思うので、少しずつ説明していこう。

#### ■ コンピュータサイエンスとプログラム開発の基本
**データ構造**と**アルゴリズム**、**プログラミング**がこれにあたる。  
**プログラミングパラダイム**はこの領域とプロセスや考え方の領域にもまたがっていると考えていいが、詳細についてはまた後述する。

**データ構造** :  
データを情報を扱いやすくする一定のまとまりとしたとき、可視化・利用しやすくするための階層構造や、ある一定の方法で別の媒体に送りやすくするための方法論・運用手法などがある。これらをデータ構造として総称する。

**アルゴリズム** :  
何かの問題を解決するための手順・考え方・効率的な計算方法の総称。

**プログラミング** :  
データとアルゴリズムをコンピュータに認識させ、解いてもらうための行為全般のことを指す。これが可能なコンピュータ語がプログラミング言語と言える。

Web開発はソフトウェア開発の分野の一つであり、コンピュータを利用したシステムを扱うものだ。ソフトウェアである以上、どうしてもコンピュータサイエンスからは離れることができない。「Web開発をやりたいです！ところで、変数って何ですか？」というような状態だと、正直言って、この後の話は理解が難しいかもしれない。  
どのようなモデルを知るのであろうと、最低でも「FizzBuzz問題を解き、解いた結果を逆順に再度出力する[^4]」ということができる程度には、なんらかのプログラミング言語、およびデータ構造についての知識習得は必要だと思う。[^5]

[^4]: https://ja.wikipedia.org/wiki/Fizz_Buzz による順次・反復・条件分岐の把握、および連結リストや配列の利用・データ格納と標準出力へのアクセスができるかどうかを見る簡単なテストとして想定。言語によっては標準入力からの型変換や変換検証も含む。

[^5]: この点は諸説ある。ライブラリの力が強くなった現代では、普遍的なアルゴリズムやデータ構造を深く知らなくとも開発はできるという人もいれば、スタックやキュー、ツリーのようなデータ構造が説明可能で、貪欲法などの頻出アルゴリズムがある程度理解できているのはあたりまえであってほしい、という人もいると思う。僕はどちらかというと前者寄り・人のメンタルモデルを一致させ、知識習得を促すコストよりも、富豪的にコンピューティングリソースを使ったり、「内部的にどうやって目的を達成するのかはわからないが、とにかく目的を達成できる」ようなライブラリを使った方が総合的なコストは安いという立場だ。だがそうであっても、ある一定の段階からは必ずアルゴリズムやデータ構造軽視によるパフォーマンスやセキュリティの痛みが発生するため、いつかはデータ構造とアルゴリズムを知っていかなければ越えられない壁が出てくる、という認識でいる。データ構造とアルゴリズムを最初の一歩を踏み出すときの壁として扱うのではなく、定期的に少しずつ拾い集めるのが最善の方法であると考え、最低限開発者としてできていなければいけないハードルとしてはかなり低いものを置いている。

#### ■ 考え方とプロセス
**プログラミングパラダイム**と**システム開発のメソドロジー**、そして**プラクティス**はこの領域となる。

**プログラミングパラダイム** :  
プログラミングおよびプログラム言語の利用を支える思想や考え方、捉え方のこと。これはプログラミング言語の書き方・作り方と言った方法論や、良いプログラム・システムの作り方とはどのようなものと考えるか、どのような課題を解決したいのかと言ったものも含む。有名なところで言うと、「オブジェクト指向プログラミング」などが挙げられるだろう。プログラミングに対する哲学の流派、と考えてもいいかもしれない。

**システム開発のメソドロジー** :  
「システム開発手法」と言い換えた方が多くの人に馴染みがあるだろう。あるいは、「ウォーターフォール」のような具体例の方がわかりやすいかもしれない。システムの作成には多くの人が絡み、一人にだけわかるような手順でプログラムを書くだけでは完成しない。システムとして完成させるために、特定のステップを定め、それに従っていくことで成功に近づいていくための試みがメソドロジーである。

**プラクティス** :  
プログラミングパラダイムにもメソドロジーにも関わるもので、日本語で「慣習」と言い換えてもいい。特定の考え方や手法に従ってシステム開発を行っていったとき、往々にしてパラダイムやメソドロジーなどの概念・大きな枠組みではどうするべきかというHowが詳細に明示されていないことがある。  
そういった小さな領域で採用・実践していくとパラダイムやメソドロジーに沿った良い効果がある方法論・パターンのことを指す。パラダイムやメソドロジーは、このプラクティスの集合や連携とセットで語られることが多い。

これら3つをひとまとめにしたのには理由がある。この3つは、**モデルの構成要素として扱うときに特に注意が必要な領域だ。**  
というのも、こういった複雑系を簡単にとらえるために一言で説明される考え方やプロセスは、得てして独自の定義に化けやすく、その効果が有効になる前提や背景があやふやになりやすいからだ。

「オブジェクト指向プログラミング」というプログラミングパラダイムを例に取ろう。オブジェクト指向プログラミングとは、継承とカプセル化とポリモーフィズム（多態性）をうまいこと使ってプログラムを作ると、なんかいい感じのプログラムができて、`bark()`というメソッドを持つ`Animal`抽象クラスを継承した`Dog`や`Cat`の実態クラスを作ると鳴き声を変えられて多態性が実現できるとかどうとか説明されるアレである。僕はいわゆるオブジェクト指向プログラミングを実現できると謳われている*Java*というプログラミング言語を使って仕事をしているが、 正直言ってこの説明がオブジェクト指向プログラミングを説明しているとは思わない。しかし、これはたしかにオブジェクト指向プログラミングの説明なのだ。……どういうことだろうか？

詳しい定義や経緯はかなりの量の説明が必要になってしまうので省くが、「オブジェクト指向」と呼ばれるモデルが歴史上いくつか存在し、それらが統合されたり分岐されたりを繰り返し、誰かのメンタルモデル化とモデルとしての表出を繰り返した結果、様々な「オブジェクト指向」の特徴を持つ独自の「オブジェクト指向」が構築され、それを*Java*および*Java*の記法を模した言語で実現するための方法論が、しばしば語られる「*Java*っぽい特徴の独自のオブジェクト指向（*Javaject指向*なんて言う人もいる）」になっている[^6]。というのが僕の理解だ。

[^6]: 「ストラウストラップ アランケイ オブジェクト指向」でGoogle検索して、この二人の功績に触れたオブジェクト指向に関する記事を探してみると良い。「オブジェクト指向」というバズワードがいかに異なる意味の同じ言葉として扱われてきたかわかる。

システム開発において、このような原義とは異なるパラダイムやメソドロジーを採用し、しかし、それが原義とは異なるとは誰も気付いていないということは多い。時には、毒にも薬にもならない、ただ面倒なだけの半端な独自方式が採用されていることもある。  
それにもかかわらず、 **原義とは異なる定義の考え方や進め方が、「あたりまえ」として扱われることが多々ある。** これはパラダイムやメソドロジーが本来持つ強みを生かすことなく、しかも新規参入者にはわかりにくいという不幸の再生産を作りやすい。

加えて、パラダイムやメソドロジーには、発案当時の状況において有効だったが今になっては時代遅れになってしまったものも多々あるため、時代背景にも気を配る必要がある。例えばオブジェクト指向（として現在扱われている、例の三大要素のパラダイム）における継承は、現代のプログラミング言語機能やツール群を利用した開発においては、メリットよりもデメリットの方が多いというのが近年の定説となっている。

これらを踏まえて注意点を明確にすると、**規範的モデルは要素を入れ替えてカスタマイズされるべきだが、規範的モデルを構成する要素そのものの意味を変えて使ってはならない。** ということになる。  
名前がついているものには、それ相応の経緯と前提となる情報が凝縮されている。特に長年使われているものならなおさらだ。

この領域の要素を適切に扱うためには、とにかく原義・経緯・現在の動向や評価という3つの視点を重視することだ。  
そして、可能な限り「あたりまえ」とされているパラダイムやメソドロジーを、用語やプラクティス、解決しようとしていた課題などに分解し、見直しを行い、原義と異なる要素を少しずつ抽出していくことが必要だ。

「あたりまえ」を捉える時、対象についての知識をすぐ揃えるのはほぼ不可能に違いが、「我々はオブジェクト指向プログラミングを行っています（あるいはドメイン駆動開発やスクラムといった、ある種流行に乗った方法論や考え）」という「一言で我々を説明する系」の言葉が出た時に、それが原義通りなのかどうかを少し疑ってかかり、真に原義と一致している部分はどれだろうと考えたり、考え方のズレを適切に議論するのが良いだろう。

「Web開発技術のあたりまえ」というタイトルにおいて、「考え方やプロセス」という項目で知るべきものは、実はこれがすべてだ。  
「オブジェクト指向というパラダイムや、関数型というパラダイムがあり、このパラダイムはこういった特徴を持っていて……」といった風に、パラダイムやメソドロジー一つ一つについて詳細に知ることをするつもりは無いし、そのうちどれかを「当然知っているべき技術」として扱うつもりは無い。というか、もし書くのならば僕は少なくともあと半年はこの文章を書くのに費やす必要がある。

現代のWeb開発技術、およびそれに付随する考え方の変化や発展はとにかく早いし、ある情報に対する解説コンテンツの広がりの速度はどんどんと増している。となれば、オブジェクト指向に起こった言葉の意味のキメラ化や、時代に合わないプラクティスの顕出、そしてそれを改善した発展的な新たな考え方やプロセスの出現も、どんどん早いサイクルで為されることが予想される。

プログラミングパラダイム・メソドロジー・プラクティスという単語の使い分けと、「色んな人や書籍から学び、歴史と今を見て、実際の自分の周囲での使われ方と比較して、定期的にみんなで見直すことを継続的に続ける」という最重要知識(と、あとは、出てきた単語をGoogleで調べられるくらいのちょっとの検索力と英語翻訳のツール)さえわかれば、「Web開発技術のあたりまえ」として伝えるべきこととしては十分だろう。もちろん、色んなパラダイムやメソドロジーを熟知し、集団や環境に合った良い方法を提供できることができればもっと素晴らしいということも伝えておこう。

#### ■ ブラウザとWebを支える技術

TBD

- ブラウザの仕組み
- Web標準とインターネットプロトコル

#### ■ 組み合わせの技術

TBD

- 主要なWebシステムのソフトウェアアーキテクチャスタイル
https://qiita.com/cocoa-maemae/items/69fe13def286c7e37d5d

- ライブラリ・テクノロジースタック
LAMPとかMEANとかJamstackとか

- ツールチェインとエコシステム
- フレームワーク


#### ■ トレンド

TBD

---

### 「深さ」の深堀：「前提知識」の選定基準

前節までは「Web開発技術」という言葉が示す領域の **「広さ」** と **「誰が知るべきか」** を示したが、 **「深さ」** についても見ていこう。具体的には、どこからどこまでの時点のモデルまでを現代Web開発技術の基礎知識、つまり、ある組織や集団に限らない世間一般の規範的モデルおよび共通マインドモデルと考えるかという **「いつにおける」** **「誰にとっての知識」** の観点だ。

結論から言うと、**2015年半ばごろから2018年ごろまでの日本において、Web開発技術者に普及した新しい技術体系と考え方**、および、**2015年以前からも続く、Web技術の変わっていない基盤要素** のことを2023年における世間一般の共通マインドモデルとして選定する。

2015年は、アジャイルムーブメントから始まる理想や考えが実際の技術系統に影響を与えて萌芽し、様々な技術体系を別物と言って差し支えないほど変えていった時代だ。この時代に浸透した技術群や考え方は現代のWeb開発技術群のベースモデルとなっている。  
そのため、2023年の現代でも通用するような知識群が大いに詰まっていると考え選定した。

以下はもっと具体的に、なぜそこをベースラインとするか、2015年を境にどのような技術がどう変わったのかという話だ。  
正直言って、かなり長いうえ、言葉の定義や歴史の話を多く含む。興味の無い人は読み飛ばしてもらって構わない。

---

技術そのものの抽象や考え方といったモデルは、誰かのとらえたマインドモデルを表現したものである以上、そのモデルが表現された時世に大きく影響を受ける。例えば企業が採用する最新のコンピュータのメモリ容量が1GBもなかった時代と、どのようなコンピュータでも最低限8GBのメモリが確保され、クラウドコンピューティングが普及している時代では、良いプログラムの書き方やプロセスの進め方はまったく異なってくる。

あるものに対する「良い」の価値観の変化が起こった際、古くからある規範的モデルが時世に合わなくなり、今まではなかった課題や問題が出てくることがある。そうなった時、一部の環境で実際にそれらを解決した、および解決しそうな先進的な取り組み・概念の捉え方・考えの整理などがモデルとして現れ、モデルの中でより成果をあげたものが新たな時代の規範的モデルとして扱われることになる。  
このような規範的モデルの潮流の中で、古くからあり課題を生んでいる方を **「レガシー」** 、新たな課題を解決する方を **「モダン」** として扱うことがしばしばある。そして、多くの「レガシー」の課題点を踏まえたうえで、現代の状況によりマッチした「モダン」の方がより現代の「良い」の感覚に近いとされる。

ただし、「モダン」は良いものである可能性は高いが、先進的がゆえに、世に広まってからすぐに欠点やさらなる課題、隠れていたモデル適用の前提条件が明らかになることもある。  
一方で「レガシー」なモデルが含む要素がすべて悪かというと、そうとも言い切れない。  
むしろモダンなモデルが受けてきた批判をすでに多く受けているため、特定の前提が一致するならむしろモダンなモデルよりも扱いやすいケースも少なくないし、基盤となる思想や観点を変えずに子細なシステム要件などの状況を加味して、「最先端のモダンなモデルは知っているが、あえてレガシーに寄せる」という選択肢を取るシステムも存在する。

それに加え、実際のシステム全般では、モダンな実装や設計、開発手法のモデルがシステムに取り入れられるより、規範的モデルがメンタルモデルとして人に広がる方が絶対的に早いという特徴もある。  
マイクロサービスアーキテクチャが効果的だ、ハイドレーションだ……などなど様々な新しいモデルが多々出てきているが、「モダン」なモデルが出現したあとのすべてのシステムがそういった「モダン」であり、誰も彼もがモダンなモデルに従って今時点の最高のシステムを作っているかというと、もちろんまったくそんなことはない。

レガシーとモダンの違いは、アプリケーションの設計思想や作り方を根本的に変えるものも多い。「モダンな良いモデルを学んだ！さあ実践だ！」という開発者の勢いだけで、レガシーなモデルのもとに作られたシステムに取り入れられるものではない。  
金と時間と戦略、そして、システムをモダンなものに変えるに至るビジネス上の明確な理由とが必要になる。

---

{{< figure src="/study-group-text/images/article/series-the-obvious-of-web-dev-media-02-02.png" width="640" title="図 2-2. 2022年におけるウェブサイトの各JavaScriptライブラリ利用率" caption=" [W3C Techs / 『Usage statistics of JavaScript libraries for websites』](https://internet.watch.impress.co.jp/docs/column/nettech/1107574.html)より引用。Webサイトの「レガシー」を支え、「モダン」では使われない方針が取られるjQueryも、まだまだサイトを支えるライブラリとして現役である。（メンテナンスされていない過去のサイトも含める調査なので、一概に今も使われているとは言えないが、この数値は無視することはできない）">}}

---

ここから言えることは一つ、 **単に最新のモデルを学ぶことは、特定のシステム開発に関わるすべての人の業務や作業の前提知識が揃うという目的に繋がらない可能性がある** ということだ。

正直言って、利用しているモデルがモダンかレガシーかはシステムが成功するか否かに直結するわけではない。使っているものがモダンであろうがレガシーの塊であろうが、成功するものは成功するだろう。

しかし、現代のシステム開発は、集団や組織内だけで完結するようなものでなく、世界レベルで相互関連する複雑系だ。たった一つのシステムを構成する要素が変化しただけで多重の連鎖が発生し、世界のシステム連携体制がガラッと変わり、今まで成功し続けてきたはずの自分たちのモデルが一瞬のうちにまったく成功しなくなる、という現象が起きることも大いにあり得る。  
そして、レガシーであればあるほど、そんな破壊的な変更に対応するためのコストは膨れ上がってくる。システム開発の世界では、瞬間の成功のためにアプリケーションやそれを支えるモデルがモダンである必要はないが、成功し続けるためにはモダンに追従し続ける必要があるのだ。

極端な思考実験をしてみよう。「開発用コードの保存時のストレージ利用量を1バイトでも減らすために、変数名は単一文字とするのが良い」「変数は一つだけを利用して再代入して使いまわした方がいい」ということが良いプラクティスとして認知されているWeb開発の現場があったとして（念のため言っておくが、もちろん現代ではこれらはバッドプラクティス以前の問題だ）、その現場にソースコードのバージョンコントロールシステムの使い方や概念から話して導入するのに、どれだけの時間と説得が必要だろうか？様々なモダンな技術を取り入れている組織に、開発スピードで勝ることができるだろうか？

上記は極端すぎる例（存在するかもしれないが、信じたくはない）だが、自分たちの「あたりまえ」の劣化基準を自分たちよりも広範の集団に求めないと、自分たちのレガシーの具合を判断できず、いつか来る突然死の存在すら知覚できなくなってしまう。  
よって、僕のスタンスとしては、 **絶対にアプリケーションや考え方をモダンにする必要性はないが、システムやチームの「あたりまえ」がどれくらいモダンの「あたりまえ」と離れていて、どれくらいリスクがあるかを把握するため、「一般的にモダンと扱われるもの」を「あたりまえ」を作るときの規範的モデルとした方が良い** というものとなる。

---

では、今のひとまずの「一般的なモダン」の楔をどこに打てば良いのだろうか。どの地点を対象にしてあたりまえと考えるのだろうか。

この点はかなりの争論を呼ぶところではあるが、ひとまず、僕の定義に従ってもらいたい。  
この文において、「一般的なモダン」は「僕自身が様々な視点を元にそう思ったもの」である。

……信用ならないのも仕方ないが、人間の中に絶対公平な歴史の観測者というのはいない。誰が語ったとしてもその人の視点は混ざるし、なんらかのバイアスがかかることは避けられない。  
だが、二つほど信用に足る根拠を用意してある。一つは定量的な調査、もう一つは定性的な観測結果だ。

先に定量的な調査について話そう。  
開発技術においてある程度普及したと考えられる知識体系は、しばしば認知度調査や普及の程度を見るような調査が行われている。たとえば*JavaScript*においては、[State of JavaScript](https://stateofjs.com/ja-JP/)と呼ばれる、開発者の新機能やライブラリへの調査が行われているし、もっと広い範囲で言えば、[Stackoverflowにおける開発者全体の傾向調査](https://survey.stackoverflow.co/)なんかもある。これらの調査を加味した上で選定した。

具体的には「どこかの時点で、おおよそWeb開発に関わる人間の65～70％ほどが知っている・少なくとも名前だけは聞いたことがあると思われる知識」であることを基準にした。ただし、これらの調査のアンケート対象は直接コードを書いて開発を行うような人間が多く、プログラミング言語関連の調査はさらにその言語について興味を持っている人が多いことは忘れてはならない。関連技術についての知識が豊富な人が多くなってしまい、どうしてもシステム開発に関わる人全般を母数としたものとは異なる結果となっているだろう。そのため、 **「各年の調査において、触ったことがある・仕事で使っている・少なくとも、名前を聞いたことがあるといった人間がある時点で85％を超える技術」** が妥当であるとして選定を行った。

定性的な観測結果は、僕の視点の内訳だ。  
まず僕が2023年におけるWeb開発技術の「モダン」として認識しているものを提示しておこう。  
2023年現在、Web開発技術のモダンなモデルとして扱われるものは二つあると思っている。

一つは、 **世界があらゆるWebのレガシーを捨てるという決意をした2015年以降のこと** 。  
もう一つは、**変化に対応するためのあらゆる具体例や細かなソリューション、そして、今まではなかった新たな痛みや課題が様々なアプリケーションや媒体に現れ始めた2018年前後からそれ以降のこと**だ。  
これら二つのモダンは、どちらも現実・ビジネスシーンの素早い変化に対応するという目的が共通しており、この共通点をもってまとめて一つのモダン傾向と扱われることが多い。[^7]

[^7]: "モダンアプリケーションとは素早いイノベーションによって競争的差別化を作り出す⼿段となるもの" [AWS Summit Online 2021 『コンテナ・サーバーレスを使えばモダンアプリケーションになりますか︖』](https://d1.awsstatic.com/events/jp/2021/summit-online/AWS-27_AWS_Summit_Online_2021_MAD01.pdf) p.12 濱 真⼀

一つ目のモダンへの大きな転機は、 **ECMAScript 2015のリリース**と、**Windows 10のリリース、およびそれに伴うWindowsの標準ブラウザの置き換え** 、そして、**コンテナ技術の普及のはじまり**だ。

これらの出来事は主にJavaScriptに影響するものだ。ECMAScript 2015はJavaScriptの仕様面での大きな変更、標準ブラウザの置き換えは、すなわち独自のブラウザ実装およびJavaScript実装を積み上げてきたInternet Explorerの実質的な非推奨化となっている。JavaScript自体が当時Webのプラットフォームとして大きな存在感があったということもあるが、それに加えてシステム開発に対して目に見えない大きなインパクトもあった。

当時、Flashの最後の砦だったInternet Explorerの事実的廃止が決まり、JavaScriptはWebの動的コンテンツを支える唯一の巨大基盤になっていた。しかし、古くからある仕様と新しい仕様の氾濫による混乱や、様々なブラウザ実装の差異などもあり、実装においても設計においても共通して利用できるような、いわゆる標準と言えるものをどこに合わせていいのかわからない混乱期にあった。

このような混乱期は2015年以前から数年にもわたって続いていたが、ついに一定基準の標準がリリースされたこと、加えて、このあたりから変化やバージョンアップのサイクルが数年単位から1年～2年ごとの定期的なアップデート体制へと変化していったこと、そして、ECMAScript 2015に合わせて、ES Modulesと呼ばれるフロントエンドのモジュール管理仕様の整備が行われたことなどは、システム開発の世界に大きく影響を与えたように思える。  
現実の変化の速さに対応するために、Webに限らない様々なツールやライブラリが変化・アップデートのスピードを上げ始めた。また、もはや非推奨となる技術のサポートを独自に続けていた技術でさえ、明らかにサポートを切り捨て始めたのもこの時期だと認識している。

Dockerに代表されるコンテナ仮想化技術が一部の研究的利用から製品投入へのプロセスを経て、一般的な普及・利用パターンの整備が進んだのもこのころになる。  
コンテナによって、今までアプリケーションレベルの範囲のみを開発範囲としていく開発者の仕事の進め方が、もっと広範、いわゆるインフラと呼ばれるレイヤーも含めたものを対象としていくような空気が漂い始めた。  
それに加え、フロントサイドではAngularやReactやVueを代表とした宣言的UIの普及、npm, Webpackを中心としたフロントエンドビルドツールの発展など、とにかくこの時期の前後にWebに起きた変化とその普及は多岐にわたる。

2015年ごろの技術の変化に伴う構造や考え方などは、2023年現在に至るまでのWeb開発技術のベースラインを完全に変えた。特に2018年までに培われた実践例の蓄積と改善は、もはやレガシーとモダンの差を隔絶といっていいほど大きく広げた。よって、この段階を一つの「モダン」が成立した時期と考えてよいだろう。[^8]

[^8]: 2010年初期ごろからRuby on Railsが流行し、フロントエンドの不満点が溜まっていき、それがこのころ爆発した、という話も聞くが、筆者がRailsの方面にあまり詳しくないので本文内では触れないこととした。[このへん](https://blog.unasuke.com/2020/i-have-to-learn-those-things-in-the-future/)や[このへん](https://zenn.dev/mizchi/articles/d33a4174cca886)を参照。

二つ目のモダンに関しては、技術がけん引したというよりは、むしろプロセスや考え方の転換だと言える。こちらのキーワードは **DevOps**、すなわち、開発と運用の協調と実質的な統合にある。  
また、こちらの方は第一のモダンのようなわかりやすい転機があるわけではなく、ゆっくりと浸透するように広がってきたものだ。強いて言えば、[『Site Reliability Engineering: How Google Runs Production Systems』](https://www.amazon.co.jp/dp/4873117917)、通称SRE本の出版が一つの転機だろうか。

DevOpsという言葉自体は、第一のモダンの発展の時期よりも前に出てきた概念ではあるが、第一のモダンの発展により、理論から実現へと大きく歩を進めた。開発と運用という、いわばシステムを作る部門と動かす部門と業務が分かれた分業化を行うことよりも、統合されたプロセスによる迅速で確実なリリースを進める、というものだ。[^9]  
また、SREはGoogleが提唱した一つのDevOpsの実践プロセスや方法論で、しばしば「DevOpsは抽象クラスのようなもので、SREはDevOpsを実行するためのGoogle製の実装」とも言われる。

[^9]: DevOpsについて一言で表すのは難しいため、かなり曖昧に表現した。考え方やツールやプラクティスがあまりにも多すぎるので、今回はこの分野には詳しく触れない。詳細は各自で調べてほしい。DevOpsに関わる本は多くあるが、特に開発者が理解を進める際に有用な本として、本文にあげた『サイトリライアビリティエンジニアリング ―Googleの信頼性を支えるエンジニアリングチーム』だけでなく、[『LeanとDevOpsの科学 テクノロジーの戦略的活用が組織変革を加速する』（原著『Accelerate』）](https://www.amazon.co.jp/dp/4295004901)を特に推奨する。現在Googleが定期的にDevOpsについて調査報告しているState of DevOps Reportの調査チーム（というか、Nicole Forsgrenを中心としたDORA社）が行った調査やその結果をまとめた本になっている。

第一のモダンの発展時期に出てきた様々な技術は、システムを作ることのコストを大幅に下げた。しかし、同時に作ったものを動かし続けることの痛みと難しさもそれと同時に広く認識されることとなった。開発部署が既存タスクのコスト減により、より幅広いシステムの業務に関わるようになり、今まで運用部署に放り投げてきた業務責任が、プロセスの責任範囲を広げた開発部署にまで及ぶようになった。同時に運用部署も、設計初期から関わらなければ運用そのものが成り立たないという現実が明らかになってきたのだ。

その中で着目されてきたのがDevOpsおよびSREというモデルだ。2018年ごろまで、DevOpsは開発と運用の統合・新たな職務や作業プロセスや概念を統合するモデルとして存在してきてはいたが、実際にDevOpsが解決しそうな直面の課題や現実的な悩みとしての浸透、および、GoogleによるSRE本の発売、そして、[DORAによるState of DevOps Report](https://dora.dev/)によるDevOpsの生産性向上効果の可視化により、多くのシステム開発関係者に浸透することとなった。[^10]

[^10]: DevとOpsの責任範囲が異なることによる分断とそれに伴うアプリケーションの停滞、また、それらを解消するためのDevOpsという概念は、2018年以前、もっと言うなら2010年代初期ごろにはすでに存在したし、それにともなうコミュニティや、実例やプラクティスなどを紹介する本もあった（[Gene Kimの『A Novel About IT, DevOps, and Helping Your Business Win』](https://www.amazon.co.jp/dp/0988262592)が代表。というか、このDevOpsはGene Kimの歴史と言っても過言じゃないかもしれない）。が、2015年ごろまでの日本ではあくまで「エンジニアが勝手に良いぞと言い始めた、それっぽい理想論の集合体」くらいに扱われていたように見ている。ここから爆発的に普及したきっかけは、やはりそれらのプラクティス効果の可視化が始まった2018年ごろからであったとして扱っている。また、あくまで開発側から見る歴史であるため、運用視点から見ると爆発的に広がったと思われる時期や、きっかけなどが違うかもしれない。再三ではあるものの、ここでは、あくまで僕がそうとらえているというつもりで見ていただきたい。

---

{{< figure src="/study-group-text/images/article/series-the-obvious-of-web-dev-media-02-03.png" width="640" title="図 2-3. DevOpsが生産性へ与えるインパクト" caption="[Takuto Wada / 『組織に自動テストを書く文化を根付かせる戦略（2022秋版）』](https://speakerdeck.com/twada/building-automated-test-culture-2022-autumn-edition?slide=27)より引用。強烈なインパクトのある数字だが、スライドを続けて読むとさらにインパクトが大きくなる。">}}

---

現代のモダンなWeb開発技術として位置づけられているものは、概ねこの2つのモダンを前提としているという認識だ。  
この2つはどちらも重要な潮流ではあるが、本文で扱うものは前者のモダンとしているもの、つまり、2015年ごろから浸透した技術体系から、DevOpsなどの開発と運用との協働を扱うものを除いたものとする。

理由は簡単で、2018年からの運用のモダンは、2015年からの開発のモダンの内容を大いに含むからだ。  
特にCI/CD[^11]の達成はソースコードのコミットから自動テストとビルドを行う必要があり、現代でこれらを行う際に、2015年以前のツールや考え方を利用すると、逆にコストが膨れ上がることとなる。

[^11]: *Continuous Integration* ・ *Continuous Deployment* の略称。日本語ではそれぞれ、「継続的インテグレーション」「継続的デプロイメント」とされる。様々な手法を用いて、アプリケーションのリリースの頻度を高める考え方・プラクティス・自動化手法そのもののこと。

もちろん、ここでは扱わないとはいえ、どちらのモダンも大切なのは間違いない。  
規範的モデルとして採用できる要素があるならば、どんどん取り入れていこう。

## ここでは扱わないもの

モダンなWeb開発技術として一部扱わないものがあることを前述したが、ここでは他にも扱わないものがある。  
近年ではしばしば **「ドメイン」** もしくは **「ビジネスドメイン」** という名称で扱われるものだ。

エンジニアリングにおける知識は、大まかにわけると「ドメイン」と「テクノロジー」の領域がある。  
ドメインは[Eric Evansの『Domain-Driven Design』(2003年出版)](https://www.amazon.co.jp/dp/0321125215)から来た単語で、ソフトウェアやアプリケーションが解決する業務対象を指す単語だ。

ドメインは、「無限の人的リソースと時間があれば、テクノロジーがなくとも業務達成可能となる知識」と考えてもいいだろう。

例えば、データ分析の仕事を考えてみよう。統計学の知識（ドメイン）がわかっていればデータ表からヒストグラムの作成と標準偏差を紙に書き、人に渡すことで、テクノロジーやシステムがなくとも業務達成は可能となる。しかし、そのためにデータを一つ一つ抜き出し、間違いがないように計算を行うことは現実的ではない。100万件のデータを扱うのに50年かかるようでは現代ならずいつであっても遅すぎる。  
テクノロジーは、これを有限のリソースと現実的な時間に納めるための技術となる。

もっと言えば、「特定ドメインにおいてのみ使われるテクノロジー」もある。  
例えば、地理空間情報を扱うシステムでは **GeoJSON** というフォーマットが登場する。これはJSONではあるが、構造やメンバー名などが固定されているというフォーマットだ。

このような、あるドメインにのみ利用されるような知識は、確かに一部の業界では基本的な知識として扱われるだろう。  
だが、これは「ドメイン」と見なし、扱わないこととする。

理由としては二つある。  
まず、「一般的なモダン」として定義した上記条件「各年の調査において、触ったことがある・仕事で使っている・少なくとも、名前を聞いたことがあるといった人間がある時点で85％を超える技術」に該当しないからだ。

二つ目の理由としては、このような複数領域が重なっている知識を扱うには、そもそもテクノロジーを知っておかないといけないからだ。  
上記のGeoJSONは、そもそもJSONの拡張フォーマットなので、JSONというテクノロジー領域の適切な扱いがわかってないと、適切に扱えることなどない。

{{< figure src="/study-group-text/images/article/series-the-obvious-of-web-dev-media-02-03.png" width="640" title="図 2-4. 本シリーズで扱う領域イメージ" >}}

- どのように？：「HTTPとはなんでしょう？」という、Google検索をすれば五秒くらいで出そうな初歩的な内容から歩んでいく。ただし、内容については詳細に触れず、業務において意識する点を中心に出し、詳しい点は書籍などで各自で深堀できるよう関連書籍を紹介する形態をとる。
  - 人によってはもう知っている、つまらないというものになるかもしれない。そういった人は、「知らなかった」という人をサポートするような補足や解説に回ったり、教える資料の内容の修正を行ってほしい。(GitHubでプルリク送って)