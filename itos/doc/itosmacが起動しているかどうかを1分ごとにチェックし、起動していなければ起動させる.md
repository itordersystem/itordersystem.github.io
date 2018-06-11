
# itos macが起動しているかどうかを1分ごとにチェックし、起動していなければ起動させる方法

※macOS 10.13.4にて確認

## チェックを登録

アプリケーションフォルダにITOSをコピーしておく。
一度起動し、起動許可を与えておく。

ターミナルを立ち上げる。

export EDITOR=/usr/bin/vim  (最初の1度だけ入力)

crontab -e で編集。以下を入力、保存。

```
*/1  *  *  *  * if [ $(ps -ax |grep ITOS.app |grep -v grep |wc -l) -eq 0 ]; then open -a /Applications/ITOS.app ;fi
```

crontab -l で今　動作しているcronを確認


## チェックを解除
ターミナルを立ち上げる

crontab -r で削除

crontab -l で今　動作しているcronを確認
