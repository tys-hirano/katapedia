# IntelliJ IDEA

## ショートカット

### 表示系

現在の単語をハイライト: Ctrl+Shift+F7

### テスト系

- テストクラスを作成する Ctrl+Shift+t
- テストメソッドを作成する	Alt+Insert テスト・メソッド
- 特定のテストを実行する	テストメソッド内でCtrl+Shift+R
- テストコード→プロダクトコードへ移動する	テストクラス内でalt+Shift+T
- テストコードで呼び出しているメソッドへ移動する	メソッドにカーソルをあわせてCtrl+alt+B
- 最後に実行したテストの再実行	(どこでも)Ctrl+R


## Tips

### Proxyに阻まれてGradleが使えない

環境変数、GRADLE_HOMEを設定して、~/.gradle/gradle.properties に
```
systemProp.http.proxyHost=ip
systemProp.http.proxyPort=port
systemProp.http.nonProxyHosts=192.168.1.*|192.168.2.*|localhost
systemProp.https.proxyHost=ip
systemProp.https.proxyPort=port
systemProp.https.nonProxyHosts=192.168.1.*|192.168.2.*|localhost
```
を追加する

Gradle VM optionsに`-Dhttp.proxyHost=ip -Dhttp.proxyPort=port -Dhttps.proxyHost=ip -Dhttps.proxyPort=port`ではうまくいかなかった

https://stackoverflow.com/questions/37704239/intellij-http-proxy-works-but-fails-at-gradle-dependencies


### ブレークポイントで止まらない

Gradleが別プログラム（intellijの管轄外）として動いていたことが原因。intellij管轄（個別でテストを実行する等）とすれば止まるようになる


### Linuxで日本語入力できない

export GTK_IM_MODULE=fcitx

export QT_IM_MODULE=fcitx

export XMODIFIERS="@im=fcitx"

を追加する
