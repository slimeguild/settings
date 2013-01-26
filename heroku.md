### heroku 設定およびアカウント追加
###### herokuコマンドのインストール 

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

##### ~/.ssh/configの編集
	Host heroku.slimeguild
		HostName heroku.com
		IdentityFile ~/slimeguild_rsa.pub
		IdentitiesOnly yes


ここで生成された鍵のうち.pub(公開鍵)をherokuにログインして設定画面から追加する。


その他、必要なことがあればこちらから。
http://journal.sooey.com/162



	
