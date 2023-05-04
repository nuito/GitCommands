## Gitコマンド
- ローカルリポジトリを作る
  - git init
- ファイルの状態を確認
  - git status
- ファイルをステージングエリアに登録する
  - git add [option] [file]
    - . カレントディレクトリ内及びサブフォルダ内すべて
    - -A 変更があったもの
- ステージングエリアへの登録を取り消す  
  - git restore --staged [file] 
- ファイルをコミットする
  - git commit -m "コメント"
  - git commit
    - エディタが開くのでコメントを入力（入力がなかったらコミットは破棄される）
    - 1行目タイトル、2行目空白、3行目以降に詳細を記述
- コミット履歴を確認する
  - git log [option]
    - -p 差分付きで表示

- ワークツリーとステージングエリアの差分を確認
  - git diff [branch]
    - ブランチ(ex:master)を入力するとブランチとの比較が可能

- ディレクトリを削除する
  - git rm -r [dir]
- ファイルを削除する
  - git rm [file]

- ブランチを作成する
  - git branch [ブランチ名]
- 使用中のブランチを確認する
  - git branch
    - *が付いているものが今使っているブランチ
- ブランチを切り替える
  - git switch [ブランチ名]
    - ブランチ名の前に-Cをオプションでつけると、新規作成後切り替えることが可能

### GitHubとの連携
- 新規リポジトリにプッシュする
  - git remote add origin git@github.com:[アカウント]/[リポジトリ].git
  - git push origin master
    - origin と master はそのときどきで違うことも。
- リモートリポジトリからローカルリポジトリにクローンする
  - git clone git@github.com:[リポジトリ].git
- リモートリポジトリの設定を確認
  - git remote -v

- 変更をリモートリポジトリに反映する
  - git push [リモートリポジトリ名] [ブランチ名]
    - リモートリポジトリ名は、特に変更していなければorigin

- リモートからローカルに反映
  - git pull [リモートリポジトリ名] [ブランチ名]
    - ※プルする前に、ブランチを正しく切り替えておくこと。
## Git 覚え書き
- Gitで管理しないファイルを設定する
  - .gitignoreファイルを作成し、中にファイル名やディレクトリ名を記入する
    - *.log
    - dirpath/filename.ext
    - dirpath/

## GitHub
- SSH-Keyを生成する
  - ssh-keygen -t ed25519 -C "メールアドレス"
    - いろいろと生成の方法はあるが、とりあえずこれでいいとはず。
    - この後、GitHubで公開鍵を貼り付けたりする
  - ssh -T git@github.com
    - 上記コマンドで鍵設定の確認
- よそのリポジトリを自分のアカウントに複製する
  - 複製したいリポジトリを開いてフォークする


## bash shellコマンド
- ファイルを作成
  - touch [file]
- カレントディレクトリを表示
  - pwd
- ファイルリストを表示
  - ls [option] [dir]
    - -a 隠しファイルを含めて表示
- クリップボードにファイルの中身をコピー
  - clip < filename.ext
- カレントディレクトリをVSCodeで開く
  - code .