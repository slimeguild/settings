### heroku 設定およびアカウント追加
##### herokuコマンドのインストール 

	sudo gem isntall heroku

##### pluginのインストール

	heroku plugins:install git://github.com/ddollar/heroku-accounts.git
	
##### アカウントの追加

	heroku accounts:add slimeguild
	#=> Emailはslimeguild@gmail.com
	#=> パスワードは例のパスワード
	done!
	
##### slimeguild herokuアカウント用の鍵生成
	ssh-keygen
	
	# Enter file in which to save the key
	/Users/name/.ssh/id_rsa => /Users/name/.ssh/slimeguild_rsa
	
	chmod 600 ~/.ssh/slimeguild_rsa.pub

##### ~/.ssh/configの編集
	Host heroku.slimeguild
		HostName heroku.com
		IdentityFile ~/.ssh/slimeguild_rsa
		IdentitiesOnly yes


##### プロジェクトでslimeguildのアカウントを使う
	cd /PATH/TO/PROJECT
	heroku accounts:set slimeguild

##### 公開鍵の登録
	heroku keys:add ~/.ssh/slimeguild_rsa.pub

##### エラー対処法
###### Your key with is not authorized to...と怒られた場合
	ssh-add ~/.ssh/slimeguild_rsa

	もしくは/PATH/TO/PROJECT/.git/configを確認
	[remote "heroku"]
        url = git@heroku.slimeguild:xxxx.git
        
        ※slimeguildになっていることが重要

その他、必要なことがあればこちらから。
http://journal.sooey.com/162



	
