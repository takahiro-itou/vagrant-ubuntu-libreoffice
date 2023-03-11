# Vagrantfile for Ubuntu 20.04 (focal64)

## 使い方

###  ダウンロード

```
git  clone git@gitlab.com:takahiro-itou/vagrant-ubuntu-libreoffice.git
cd   vagrant-ubuntu-libreoffice
```

###  準備

プロビジョニングにより、以下のデータが仮想マシンに転送される。
- ホームディレクトリに ~/VagrantConfig/ ディレクトリがあれば転送される
    - 暫定的に、現バージョンでは上記ディレクトリがなければエラーになる
- このレポジトリの data ディレクトリの内容が転送される

###  起動

```
cd   vagrant
time vagrant destroy -f ; time vagrant up ; echo $?
```

##  通信関連

###   リポジトリ

- 内部に hg のレポジトリを立てる

```
ssh  hgvagrant
hg  init  ~/<RepoName>
exit
```

- 仮想マシン内外からアクセス

```
hg clone  ssh://hgvagrant/<RepoName>
```

.ssh/config の設定が正しくない場合はユーザー名 hg の指定が必要になる

```
hg  clone  ssh://hg@hgvagrant/<RepoName>
```
