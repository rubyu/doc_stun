# なぜなにSTUN 

本書は、"なぜなに Torrent"の姉妹本です。
"なぜなに Torrent"と同様に、実際にSTUN Server と STUN Client を実装して得た知見やノウハウを元に、アレコレP2Pについて解説してきます。

[TODO] ミニマムスペックはできたので紹介する
https://github.com/kyorohiro/tetorica


# はじめに

### Webアプリはお金がかかる
私たちは現在、さまざまなWebサービスを利用しています。そのほとんどが無料です。
スマートフォンから地図を開いたり。ソーシャルネットワークを開いたり。Google検索して、Webページを探したり。Youtubeで動画を見たり。

しかし、無料で利用していますが、その運営費は巨額です。
[TODO] AWS GAE mBaaSとかの例を書く


ある一定の規模を越えると、サーバー代がかさみ運営が困難になります。または、サービスの質が落ちます。

緩やかに、増減するようなものでは、やりくりできます。急激に成長するような場合、
破綻してしまいます。


### P2Pで実現してみては?

ひとつの解決方法として、P2Pが有ります。サーバーの負荷を利用者に分担することで、
サーバーへの負荷を減らします。

たとえば、BitTorrent というファイル共有サービスは、利用者が増えるほど、
ファイルが配信される性能は上がります。

BitTorrentでは、ファイルをダウンロードしてもらう人が、データを配信する側に加わることで、
サーバーの配信コストを減らしています。

P2Pにより、このレベルまで最適化が進むと、配信者は企業という体裁を持たなくとも、
個人でもスケール可能なサービスを展開できます。

[TODO スケースするとかは、言い方を変える



### STUN は、重要な役割を担っている

本書では、その中でも STUN について紹介します。STUNはP2Pアプリでも、P2Pを利用してユーザーになんらかのサービスを提供するようなものではありません。P2Pサービスの中の要素技術のひとつです。

有名なところでは、WebRTCという、リアルタイムコミュニケーションアプリを作るためのフレームワークなどで利用されています。たとえば、WebRTCはファイルを交換したり、ビデオチャットをしたり、といった事がサーバーを経由しないで実現する事ができます。

この、サーバーを経由しないで、ネットワーク上でユーザー同士が繋がるには、さまざまな障壁があります。
その障壁を越えるためには、ユーザーの端末の状態や情報を知る必要があります。
この、ユーザーの端末の状態を知るための要素技術がSTUNです。


# サンプルコードはDartを利用しています。

本書では、実際にコードを書いています。このコードには、 Dart を利用する事にしました。Dartは、現時点において、もっとも優れたプログラム言語です。C系、Java系の流れを汲みつつ、関数型的な書き方も柔軟にできます。

C、Java系の流れを組んでいるため、多くの人が読むことができるでしょう。関数型の流れを組んだ、完結なプログラムを書くことができます。

また、多くの環境で動作します。ブラウザー、ChromeOS、 Android、 iOS 、 Mac、Windows、Linux、Raspberry Pi 上で動作します。
きっと、あなたの環境でも動作する事でしょう。


# 試したい方へ

STUNを利用するには、IPアドレスが2つ必要です。　うーん、難しいですね。
VPSを借りるのが良いでしょう。

Serversman (http://dream.jp/vps/)、DigitalOcean(https://www.digitalocean.com/)を利用すると良いでしょう。


### ServersMan@VPSを利用する場合

2016/3/12 現在に試してもので、将来的に保証されるものではあれません。

##### 1. ServersManからStandard Plan を契約する。
###### 1.1. http://dream.jp/vps/
###### 1.2. standard plan を選択 (934円 per 月)
###### 1.3. ubuntu 64bit のOSを選んでください。 
##### 2. ログインする
###### 2.1. $ssh root@<your ip> -p <your port> 
###### 2.1. $ssh root@<your ip> -p <your port> 







