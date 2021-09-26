FROM ubuntu:20.04

MAINTAINER satoshi.ito.dev@gmail.com

# 初期導入コマンド
RUN apt-get update && \
  apt-get upgrade -y && \
  apt-get install -y \
  sudo \
  curl \
  wget \
  apt-transport-https \
  gnupg \
  ca-certificates \
  language-pack-ja \
  gcc \
  build-essential \
  git \
  vim

# 日本語環境
RUN update-locale LANG=ja_JP.UTF-8
ENV LANG="ja_JP.UTF-8" \ 
    LANGUAGE="ja_JP:ja" \ 
    LC_ALL="ja_JP.UTF-8" \ 
    LC_ALL="ja_JP.UTF-8" \ 
    TZ="JST-9" \ 
    TERM="xterm"

# ユーザーIDの設定
ARG UID=1000
# ユーザー名の設定
ARG username=satoshi
# workディレクトリの作成
ARG wkdir=/home/work
# passwordの設定
ARG userpass=satoshi

# グループの作成
#RUN groupadd -g sudo

# ユーザーを作成
RUN useradd -m -u ${UID} -g sudo satoshi && \
    echo ${username}:${userpass} | chpasswd

# ユーザーを指定
USER satoshi
# 作業用ディレクトリの設定
WORKDIR /home/satoshi

