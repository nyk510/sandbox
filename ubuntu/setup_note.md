# Ubuntuの環境構築

Ubuntu 16.0.3 をインストールしたあとに行ったことを記述する。

## フォントの追加

今回は SourceHanSansJ を導入します。 無料で使える日本語フォントかつとても綺麗。
matplotlib の描画の時に指定するとちょっとおしゃんな感じになってとてもよいです。

システム全体で共有するため `/usr/local/share/fonts` で作業します。

```bash
cd /usr/local/share/fonts
sudo wget https://github.com/adobe-fonts/source-han-sans/raw/release/OTF/SourceHanSansJ.zip
sudo unzip SourceHanSansJ.zip
sudo fc-cache -fv
```

## Themeの変更

デフォルトテーマはちょっとかっこよくないのでカスタマイズしましょう。 
とりあえずいろいろテーマをインストールしてくれるスクリプトを走らせます。

```bash
git clone https://github.com/tliron/install-gnome-themes ~/install-gnome-themes
~/install-gnome-themes/install-gnome-themes
~/install-gnome-themes/install-gnome-themes # 何故か二回叩かないと動かなかった
```

インストールされたテーマは、デフォルトの設定画面からいじれないので設定を行うアプリケーションをインストールします。

```bash
sudo apt-get install unity-tweak-tool
```

### Paper

[https://snwh.org/paper](https://snwh.org/paper)

```bash
sudo add-apt-repository ppa:snwh/pulp
sudo apt-get update
sudo apt-get install paper-icon-theme　paper-cursor-theme paper-gtk-theme
```

### Gogh

「ゴーゴ」って読むのかと思ってましたが、正しくはゴッホ。　ターミナルのスキンを変えられる。100以上のテーマがあるので適当に入れて設定するだけで結構たのしい。

```bash
sudo wget -O /lgogh https://git.io/vQgMr && sudo chmod +x gogh
gogh
```

文字通りわらわらとスキンが出てくるのでインストールしたいテーマの番号を入力しましょう。
