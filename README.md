# なぜなに STUN 

本書は、"なぜなに Torrent"の姉妹本です。
"なぜなに Torrent"と同様に、実際にSTUN Server と STUN Client を実装して得た知見やノウハウを元に、アレコレP2Pについて解説してきます。

[TODO] ミニマムスペックはできたので紹介する
https://github.com/kyorohiro/tetorica


# [1] はじめに

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






# [2] STUNとは

### インターネット上の端末はIPアドレスを持っている
インターネットに繋がっている端末には、すべてIPアドレスが振られています。このIPアドレスをもとに、相手の端末に接続する事ができます。

GoogleのWebページは、"www.google.jp"というアドレスをもっていますね。GoogleのWebページにアクセスすると、ブラウザーの上のほうに表示されています。

```
$nslookup www.google.jp
Non-authoritative answer:
Name:	www.google.jp
Address: 216.58.197.3
```

この、"216.58.197.3"というIPアドレスを、ブラウザーに入力してみてください。
GoogleのWebページが表示されるはずです。

インターネットの凄いところは、このIPアドレスさえわかれば、世界中のコンピュータに接続できるという事です。
もちろん、私たち利用者のコンピュータにも接続ができます。


### ほとんどのユーザーは、利用している時だけIPが配布されている

　しかし、さまざまな、経緯から、IPアドレスはサーバー側にしか所持していません。もちろん、ネットワークゲームをハードに利用するために、プロバイダーとIPアドレスを所持する契約をしている人や、IPアドレスを豊富に所持しているプロバイダーを利用しているユーザーは、IPを持っています。

良く持ちいられる話としては、現在、もっとも利用されているIPv4が、枯渇しているのが理由です。
IPv4は、2の32乗=43億のIPアドレスしか管理できません。
一見、大きな数字ですが、地球の人口はすでに、70億をこえていまから、一人にひとつのIPを割り振る事ができない状態な訳です。

　このような背景から、他の端末からアクセスされる端末には、固定のIPアドレスを割り振りますが、他の端末からアクセスされる事が発生しにくい端末には、利用する時だけIPを割り当てるという事が行われています。


### P2P接続は考慮されていない場合がほとんど。
 　利用時に割り振られている、IPアドレスを相
 





### 




### STUN を利用して、これらの状態を知る事ができる。








# [3] ルータが隠蔽している世界

### インターネット上のコンピュータは、IPアドレスでつながっている
xxx

### コンピュータは知らない
xx

# [4] TCPよりもUDPが適当

### 通信相手は、IPアドレスを知っている
xxx
### UDPなら通信相手から聞ける
xxx

# [5] NAT越えの方法
### IPを、公開する

### IPと、Portを返してもらう

### Aの場合
xxx

### Bの場合

xxx

# [6] STUNで、どの方法でNAT越えができるか確認する

### ようは、前もってNat越えできるか確認しておくということ

xxx



# [7] 実装編
## Attibute
xx

## Header
xx

## HMAC
xx


# [8] あとがき

xxx


# [9] 次回

なぜなに UPnP Portmap
なぜなに TURN










