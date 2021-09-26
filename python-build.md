# Pythonbuild方法

## 手順1

必要なライブラリをインストール

```
$ sudo apt update
$ sudo apt install build-essential libbz2-dev libdb-dev \
  libreadline-dev libffi-dev libgdbm-dev liblzma-dev \
  libncursesw5-dev libsqlite3-dev libssl-dev \
  zlib1g-dev uuid-dev tk-dev
```

## 手順2

ソースコードのダウンロード

```
wget https://python.org/downloads/release/python-...
```

解凍

```
$ tar xJf Python-x.x.x.tar.xz
```

## 手順3

ビルド

```
$ cd Python-3.x.x
$ ./configure
$ make
$ sudo make install
```

## その他の使える者たち

### ディレクトリを指定してインストール

デフォルトでは、Pythonは `/usr/local/` 以下にインストールされます。

`/usr/local` 以外のディレクトリにインストールする場合は、configure に --prefix オプションを指定します。

例えば、管理者権限のない環境などで、ホームディレクトリにPythonをインストールする場合は、次のように指定します。

```
$ cd Python3.x.y
$ ./configure --prefix=/home/user/.local/python
$ make
$ make install
```

### 複数バージョンのインストール

`make install` コマンドは、Pythonのバージョンを指定して実行する python3.x コマンドと、最後にインストールしたPythonを実行する python3 コマンドの２つをインストールします。

複数バージョンのPythonを同時に利用する場合は、python3 コマンドで実行したいバージョンのPythonだけを `make install` でインストールし、それ以外のバージョンは

```
$ sudo make altinstall
```

でインストールします。

`make altinstall` でインストールした場合、python3.x コマンドはインストールされますが、python3 コマンドはインストールされません。

これにより、python3 コマンドでは主に使用するバージョンのPythonを起動し、それ以外のバージョンのPythonは python3.7 のように、バージョンを指定して実行できるようになります。


### pipのインストール
