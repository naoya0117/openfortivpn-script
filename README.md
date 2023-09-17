# openfortivpn-script

## 使い方
- ファイルの権限を変える(パスワードベタ塗りなので自分以外の読み取り権限を外す)
```
git clone https://github.com/naoya0117/openfortivpn-script.git
cd openfortivpn-script
chmod a+x ./vpn
chmoe go-r ./vpn
```
- sudoパスワード,接続確認用のサーバ,vpn名(何でも良い)変数を編集
```
vim ./vpn
```
- openfortivpnの設定
```
vim /etc/openfortivpn/config
```
- 実行
```
./vpn [up|down]
```


## メモ
- このスクリプトでは、--pppd-accept-remoteを使用している。最近のppp(2.5.0.以上)のエラーを解決するために使うオプションで
--ipcp-accept-remoteをつけてpppdを実行するものらしい。openfortivpn --pppd-accept-remoteの代わりに以下を追記するとオプションなしで
実行できる。openfortiguiやその他のクライアントのエラーはこの操作で解決することがある。
```
$ vim /etc/ppp/options

ipcp-remote-accept
```





