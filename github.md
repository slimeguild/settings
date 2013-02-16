### github 使い方

せっかくgithubを使っているので100%使いこなすための運用方法を考えて行きたいと思います。

#### slimeguildアカウント

- Organizationに変更する　=> 誰もslimeguildアカウントで作業しないで、自分のアカウントで操作できるようになる

- privateレポジトリ　=> 今は受託用のものもpublicなレポジトリにしているが冷静に考えてそれはまずいのでprivateにする。終了した案件は削除する。


#### fork & pull request

できればすべてのコミットは別の人のレビューを経てからmergeするようにしたい

- (理由1)１つのプロジェクトを複数人でやる場合、どうしても他の人がメインで作った箇所を修正する場合があるが、その場合は絶対にその人の確認を経たほうが良い

- (理由2) コードレビューによって知識を平準化できる、他人の確認が生じることへの心理的効果



######流れ

- slimeguild/xx.gitという空のレポジトリを作成

- slimeguild/xx.gitをforkする。t-kot/xx.git

- slimeguild/xx.gitからcloneしてlocalのレポジトリを作る。localのレポジトリではforkしたt-kot/xx.gitをforkなど適当な名前で登録(git remote add fork …./t-kot/xx.git)

- localのレポジトリはmasterにいるはずなので、まずdevelopブランチを切って作業する。developからさらにフィーチャーブランチ(feature/hogehoge)を作成して作業

- 作業が済んだらそのままそのブランチをforkのほうにpushする(git push feature/hogehoge)

- これによってforkしたほうに新しくfeature/hogehogeブランチが作成される。このブランチで、slimeguildのほうのdevelopに対してpull requestを送る

- レビューを経て、修正があったら手元のfeature/hogehogeで修正し、そのまま同様にforkのfeature/hogehogeにpushする(pull requestが自動的に更新される)

- 承認ののち、developにmergeする。

- 以上を一つの単位として、次の作業(feature/fuga)をする場合はlocalのdevelopでpullして更新を取り込んでから、feature/fugaを切る。


以上が素案なのですが、やってみてうまく変えて行きたいと思います！

(文責: 琴畑)







