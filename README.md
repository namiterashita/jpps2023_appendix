# Appendix: 女性団体の活動は福祉予算に影響を及ぼすのか：韓国・地方自治体の抗議イベントデータを用いた実証分析

『公共政策研究』(23):139-155

Do Women's Organizations' Activities Affect Welfare Budgets?: Empirical Analysis Using Protest Event Data from Local Governments in Korea


---

# Author

* [寺下和宏](https://kazuhiroterashita.com/)（京都大学大学院法学研究科特定研究員/日本学術振興会特別研究員PD）

---

# File

[PDF](https://kazuhiroterashita.com/jpps2023_appendix/jpps2023_Appendix.pdf)


---

# Abstract

本稿は、韓国における基礎自治体のパネルデータを用いて、女性団体の活動が自治体の福祉予算に与える影響を明らかにした。先行研究は、女性団体をはじめとする「女性」の利益を代表するアクターが政治過程に参加することで、福祉の拡充がもたらされると論じてきた。この中で、女性団体はアウトサイダーとして、福祉拡充の世論形成に重要な役割を果たしつつ、時に労働団体や左派政党と連携して、政策起業家として福祉政策を主導してきたことが指摘されてきた。その一方で、先行研究では、女性団体と福祉政策の関係についてデータを用いた実証分析がほとんどなされてこなかった。そこで本稿では、韓国の基礎自治体の福祉予算の規定要因を分析し、女性団体の活動が福祉予算にいかなる影響を与えるのかを検討した。その際、機械学習を導入した抗議イベント分析を用いて、韓国語の新聞記事を分類することで、韓国各地の女性団体の活動に関する独自のデータを構築した。差の差法（DID）による分析の結果、女性団体の活動の有無が自治体の福祉予算に影響を与えるとは言えないが、進歩的な女性団体のみが抗議をしている場合か、女性・福祉に関するシグナルを発する抗議のみが観察される場合に、その2-3年後の人口一人当たり福祉予算が増加することが明らかになった。

This paper uses panel data from local governments in Korea to examine the impact of the activities of women's organizations on the welfare budgets of local governments. Previous studies have argued that the participation of women's organizations and other women actors in the political process leads to welfare expansion. In this context, it has been pointed out that women's organizations, as outsiders, have played an important role in shaping public opinion in favor of welfare expansion, while at the same time acting as policy entrepreneurs, sometimes in cooperation with labor organizations and left-wing parties, in leading welfare policy. On the other hand, previous studies have rarely conducted empirical analyses using data on the relationship between women's organizations and welfare policy, and there has been a gap between theory and evidence. Therefore, this paper analyses the determinants of the welfare budgets of local governments in Korea and examines how the activities of women's groups affect welfare budgets. To do so, we constructed unique data on the activities of women's organizations in different regions of Korea by classifying newspaper articles in Korean using protest event analysis with the introduction of machine learning. Using the difference-in-differences (DID) method, we find that the presence or absence of women's organization activities does not affect a local government's welfare budget, but only when either only progressive women's organizations protest or only protests with signals about women and welfare are observed. 2-3 years later, welfare budgets per capita in the population were found to increase.

---

# 抗議イベント分析の詳細

以下では、本稿で用いた抗議イベント分析の詳細について述べる。本稿ではアドボカシー（坂本編 2017）の定義を採用することで、デモや集会といった「抗議」という言葉で連想される典型的なレパートリーだけでなく、政治・社会に影響を及ぼす可能性のある女性団体の多様な抗議のあり方を捉えている。また、対象は、韓国における首都圏で行われた抗議はもちろん、地方で行われたイベントも含めている。期間は、後述するデータベースの制約から1990年1月1日以降2021年12月31日までの32年間としているが、分析に用いたのはこのうち2010年から2020年までの11年間のみである。そして、対象とした団体は女性団体である。
抗議イベント分析に必要な段階は以下の3つである。第1に、ソースとなる新聞記事の検索と収集である。第2に、新聞記事の分類とコーディングである。第3に、データの確認である。以下では、各手順について述べる。

## 新聞記事を収集する
本稿では、抗議イベント分析に用いる新聞記事の検索と抽出を以下のように行った。
まず、利用するデータベースは韓国の主要新聞（全国紙・地方紙・専門紙を含む）の記事が閲覧・利用可能な[BIGKinds](https://www.bigkinds.or.kr/)である。BIGKindsは、日本国内の主要新聞のデータベースと同様に、日時や媒体、キーワード、掲載面などを指定して、収録されている新聞記事の検索を行うことが可能である。他方で、日本で新聞社が独自に提供するサービスとは異なり、掲載新聞の横断検索や基本的なキーワード分析などを無料で提供している点でメリットがある。本稿ではBIGKindsを用いて、新聞記事を検索後、記事データをダウンロードして利用した。
次に、抗議イベント分析が対象とする媒体を検討する。先行研究はさまざまなメディア・カヴァレッジに対応するために、複数の媒体を用いることを推奨してきた。そこで本稿では、BIGKindsに収録された複数の全国紙（4紙）および地方紙（13紙）を用いて分析を行う。具体的には、東亜日報、朝鮮日報、中央日報、ハンギョレ、江原日報、京畿日報、慶南新聞、光州日報、国際新聞、大田日報、毎日新聞、釜山日報、蔚山毎日、全南日報、全北日報、忠清日報、漢拏日報の17紙である 。全国紙は発行部数が多い4大新聞のみを用いている。ただし、このように複数の媒体を用いると、1つのイベントに対する複数の新聞記事・報道の重複が増加する。この重複については、後述する分析のテクニックで除去する。
次に、選定した媒体のうち、必要な記事を検索するための検索語を検討する。検索語は、抗議を示す語（デモ、集会など）と、団体や業界を示す語（女性団体、環境団体など）の2つが考えられるが、本稿では、女性団体の抗議イベントを明らかにすることを目的としているため、団体や業界を示す検索語を用いた。具体的には、以下の通りである。

"女性団体"OR"女性団体"OR"女性運動"OR"女性 運動"OR"女性界"OR"女性人権団体"OR"女性人権 団体"OR"女性主義 団体" OR"フェミニズム 団体"OR"女性主義 運動"OR"フェミニズム 運動"OR"性的少数者団体"OR"性的少数者 団体"OR"性平等 団体"OR"性平等 運動"OR"反性暴力団体"OR"反性暴力 団体" OR"反性暴力運動" OR"反性暴力 運動" OR "女性労働団体"OR"女性労働 団体"OR"女性労働運動" OR"女性労働 運動" OR"女性農民団体" OR"女性農民 団体" OR "女性農民運動" OR"女性農民 運動" OR "韓国女性団体連合"OR"女性団体連合"OR"韓国女性団体協議会"OR"女性団体協議会"OR"YWCA"OR"民友会"OR"女性民友会"OR"女性 民友会"OR"韓国女性民友会"

期間は、BIGKindsの収録記事の始点である1990年1月1日から2021年12月31日までとした。ただし、重複記事と社説、国際面ニュースは除いた。この他「特集」記事が推定結果に影響を及ぼす可能性があるが、本稿の分析では「特集」記事においても抗議イベントが報じられる可能性を考慮し、「特集」記事を含めて分析を行った。この結果、収集した新聞記事は72,855件であった。

## 新聞記事を分類する・ラベリングする
新聞記事を収集したのち、その記事が抗議に関するものであるか、そうでないものであるか、あるいは、その抗議がどのような形式だったのかなどの属性を判断する必要がある。そこで本稿では、新聞記事を分類するために、準教師つき学習モデルであるnewsmap（Watanabe 2018）を用いた。newsmapは本来、新聞報道の場所を推定するために開発された機械学習の手法である。したがって、標準では英語や日本語の国名および地名が種語として登録された辞書が整備されており、この辞書を用いて機械学習のモデリングを行うことで記事を分類・地名を推定している。だが、作者のWatanabe（2018）によれば、分析者が辞書を新たに用意すれば、英語や日本語など以外の言語や、より詳細な地名の分類（例えば、特定国の自治体）だけでなく、組織・団体の分類などの応用も可能である。つまり、分類の基準となる種語を指定さえすれば、教師つき機械学習よりも低いコストで、対象となる分類のモデリングが可能となる。
そこで本稿は、以上のnewsmapの特徴を活かし、新聞記事の分類を行った。まずnewsmapで分類を行うに際して、統計分析ソフトウェアRのquantedaパッケージ（Benoit, Kenneth et al. 2018）を用い、文書を単語に分割するトークン化（tokenization）、不用語・ストップワーズ（stop words）の削除、文書単語行列への変換等の前処理を行った。韓国語の計量テキスト分析にあたって注意すべき点等は、イスジョン・チェドゥヨン（2020）を参考にした。
さらに、4つの辞書を新たに作成し、分類に用いた。具体的には、抗議形式、地名、イデオロギー、抗議の主張（シグナル）である。以下では最も重要となる抗議形式の分類について簡単に述べる。
抗議イベント分析を行うに際し、何を抗議とし、どう分類するのかは、分析者自身によって、分析の目的に応じて、あるいは、理論的な背景から考える必要がある。本稿では、冒頭で述べたアドボカシー概念から抗議形式を特定する。
抗議形式は、アドボカシー概念に応じて、表1の通りに分類した。ただし「その他」に含まれるラベルに分類された記事は、本稿では抗議とみなしていない。いずれも、定義としてはアドボカシー概念に含まれる可能性があるが、新聞報道される場合、団体が行った政治的抗議とは限らないためである。以上の分類結果に応じて、新聞記事が抗議に関するものであるか、そうでないかを判断した。
　以上と同様に、地名、イデオロギー、抗議の主張（シグナル）についても辞書を作成した。イデオロギーと抗議の主張（シグナル）の辞書の詳細については表2, 3のとおりである 。イデオロギーの推定には、韓国の進歩的女性団体連合組織である韓国女性団体連合（女連）と、伝統的保守女性団体の連合組織である韓国女性団体協議会（女協）の加盟団体リストを用いた。
だが、以上のように処理した場合、抗議イベントの重複が問題となる。そこで本稿では、抗議形式、報道日、場所、主張の全てが重複したイベントを削除した。このようにすることで、新聞社間で重複して取り上げられたイベントを概ね除去することができる。以上の処理を行った結果、2010年1月1日から2020年12月31日までの11年の間で、18,078件の記事を抗議イベントとして特定した。

## データの正確性を確認する
　機械学習で分類したデータは、正確性を確認する必要がある。抗議イベント分析についても例外ではない。しかし、抗議イベントには、そもそも正答となるデータが存在しないという大きな問題がある。正答データが存在しない場合、分析者によって正答データを新たに構築する必要があるが、抗議イベントの場合、コストのかからない範囲で、一貫性を保った分類を行う必要がある。
このため、分析者である筆者が、女性団体の抗議イベントの正答データを作成した。以下の概要で行った。まず、分析に用いた新聞記事のうち、ランダムで100件を再抽出した。この再抽出した記事に対し、分析者である筆者が手作業で機械学習と同様のラベリングを行った。その後、筆者が手作業でラベリングしたデータを正答データとし、機械学習でラベリングしたデータの一致度を確認した。結果は表4に示している。結果として、少なくとも筆者の判断で分類したデータとの比較では、高い精度が担保されている。

