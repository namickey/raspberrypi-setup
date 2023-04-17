# raspberrypi-setup

## 本体 + アルファ

* Raspberry Pi4 8GB
* SSD + SATA6⇔USB変換ケーブル　※SDカードは使用しない
* USB typeC 電源タップ
* microHDMI⇔HDMIケーブル　※直接操作するため
* ディスプレイ　※直接操作するため
* キーボード　※直接操作するため
* マウス　※直接操作するため
* ノートPC　※VNCクライアント側

## インストール

以下、ツールを使ってRaspberry Pi OS(32-bit)をインストールする  
SDカードではなくて、SSDにもインストール可能  

Raspberry Pi Imager  
https://www.raspberrypi.com/software/  

初回のOS起動後には、ユーザとパスワード、ロケーション、無線LANの設定などを行う。  


## 本体 + 金属ケース = 無線LANの不調

全体を覆う形の金属ケースをつけると、無線LANが接続できなくなった。  
冷却方法については個別に小さなヒートシンクを使用する。  


## 英語化

ディレクトリ名を英語へ変更する
```bash
LC_ALL=C xdg-user-dirs-update --force
```

## 日本語入力

日本語入力
```bash
sudo apt install fcitx-mozc
```
## ntp

Raspberry Pi NTPサーバーとの時刻同期
https://tarufu.info/raspberry-pi-ntp/

## ssh

公開鍵生成
```
ssh-keygen -t rsa -b 4096
```

SSHの有効化  
https://qiita.com/c60evaporator/items/ebe9c6e8a445fed859dc#ssh%E3%82%92%E5%85%AC%E9%96%8B%E9%8D%B5%E8%AA%8D%E8%A8%BC%E3%81%AB%E5%A4%89%E6%9B%B4  

SSHを公開鍵認証に変更  
https://qiita.com/c60evaporator/items/ebe9c6e8a445fed859dc#ssh%E3%82%92%E5%85%AC%E9%96%8B%E9%8D%B5%E8%AA%8D%E8%A8%BC%E3%81%AB%E5%A4%89%E6%9B%B4  

各種SSH設定の変更  
https://qiita.com/c60evaporator/items/ebe9c6e8a445fed859dc#%E5%90%84%E7%A8%AEssh%E8%A8%AD%E5%AE%9A%E3%81%AE%E5%A4%89%E6%9B%B4  


## VNC

VNCでRaspberry Piにリモートデスクトップ接続 (Windows/Mac/Linux対応)  
https://www.indoorcorgielec.com/resources/raspberry-pi/raspberry-pi-vnc/  

ヘッドレス解像度の設定  
https://invisiblepotato.com/raspberrypi05/  

## sshトンネル + VNC-Client

以下コマンドで作成したSSHトンネルを使って、localhost:5901に向けてVNC接続する。

```bash
ssh -L 5901:localhost:5900 <userid>@<ipaddress> -N
```

## firewall

SSHを使用するため22番ポートだけ公開する。  
VNCの5900ポートは使用しないので開けない。SSHトンネルを使ってVNCを行う。  

```bash
sudo apt install gufw
```

