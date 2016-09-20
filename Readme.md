ATLAS_PUMP
----------

###概要###

このプロジェクトは、Terasic社(<http://www.terasic.com/tw>)のFPGAボード DE0-Nano-SoC で 
PUMP_AXI4(<http://github.com/ikwzm/PUMP_AXI4>)と
LED_AXI(<http://github.com/ikwzm/LED_AXI>)を実装し動作を確認するするためのものです.

###開発環境###

FPGAのビットイメージは以下の開発環境で合成出来ることを確認しています.

* Altera Quartus Prime 15.1 Lite Edition
* Altera SoC Embedded Design Suite 15.1

###インストール###

####1. クリーンなプロジェクトからFPGAのビットイメージを生成する場合.####

#####1.1. githubからリポジトリをダウンロードする.#####

```
shell> git clone git://github.com/ikwzm/ATLAS_PUMP.git ATLAS_PUMP
shell> cd ATLAS_PUMP
shell> git checkout master
```

出来れば何もないところから始めると良い。

#####1.2. githubからサブモジュール(PUMP_AXI4とLED_AXI)をダウンロードする.#####

```
shell> git submodule init
shell> git submodule update
```

#####1.3. 論理合成、配置配線をする.#####

ここでは Altera EDS の Command Shell を使います。
./project の下に Makefile を用意しています。make を使って論理合成と配置配線を行います。

```
shell> cd project
shell> make sof
```

#####1.4. ビットストリームファイルを生成する.#####

1.3 で紹介した Makefile を使って make します。

```
shell> make rbf
```

#####1.5. preloader を生成する.#####

1.3 で紹介した Makefile を使って make します。

```
shell> make preloader
```

#####1.6. u-boot を生成する.#####

1.3 で紹介した Makefile を使って make します。

```
shell> make uboot
```

###ライセンス###

1.3 で紹介した Makefile は Altera から提供されているものです。

