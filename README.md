# NeoVIm Install



## NeoVim

基本はこれベースで進めていく

https://wonderwall.hatenablog.com/entry/2019/07/28/230000





```
Python providerはPython2とPython3のそれぞれでpynvim（前はneovimという名前だった）パッケージをインストールするとOKになる。
例えば、pyenvとpyenv-virtualenvを使用している場合は以下のようにする。

pyenv install 3.7.4
pyenv install 2.7.16
pyenv virtualenv 3.7.4 neovim3
pyenv virtualenv 2.7.16 neovim2
pyenv shell neovim3
pip install pynvim
pyenv shell neovim2
pip install pynvim
```



## pyenv

pyenv install

```
curl -L https://raw.githubusercontent.com/pyenv/pyenv-installer/master/bin/pyenv-installer | bash
```

bashrc
```
export PYENV_ROOT=$HOME/.pyenv
export PATH=$PYENV_ROOT/bin:$PATH
eval "$(pyenv init -)"
```
pyenv install *** でエラーになるので依存パッケージを入れておく
```
yum install zlib-devel bzip2 bzip2-devel readline-devel sqlite sqlite-devel openssl-devel xz
yum install libffi-devel
```





### pyenv バージョン切り替えの確認

http://sig9.hatenablog.com/entry/2018/12/21/000000

```
[nishijima@localhost ~]$ pyenv versions
* system (set by /home/nishijima/.pyenv/version)
  2.7.16
  3.7.4
[nishijima@localhost ~]$ pyenv shell 3.7.4
[nishijima@localhost ~]$ pyenv versions
  system
  2.7.16
* 3.7.4 (set by PYENV_VERSION environment variable)
```

3.7.4 install

```
[nishijima@localhost ~]$ pyenv install 3.7.4
Downloading Python-3.7.4.tar.xz...
-> https://www.python.org/ftp/python/3.7.4/Python-3.7.4.tar.xz
Installing Python-3.7.4...
Installed Python-3.7.4 to /home/nishijima/.pyenv/versions/3.7.4
```

2.7.17 install

```
[nishijima@localhost ~]$ pyenv install 2.7.16
Downloading Python-2.7.16.tar.xz...
-> https://www.python.org/ftp/python/2.7.16/Python-2.7.16.tar.xz
Installing Python-2.7.16...
Installed Python-2.7.16 to /home/nishijima/.pyenv/versions/2.7.16
```



### pip update

```
pip install --upgrade pip
```



## rbenv

[https://crowrabbit.hatenablog.com/entry/2019/04/06/CentOS7%E3%81%ABrbenv%E3%82%92%E5%B0%8E%E5%85%A5](https://crowrabbit.hatenablog.com/entry/2019/04/06/CentOS7にrbenvを導入)

```
(neovim3) [nishijima@localhost ~]$ echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
(neovim3) [nishijima@localhost ~]$ echo 'eval "$(rbenv init -)"' >> ~/.bashrc
(neovim3) [nishijima@localhost ~]$ source ~/.bashrc
```

```
(neovim3) [nishijima@localhost ~]$ rbenv -v
rbenv 1.1.2-20-g143b2c9
```


上記よりcloneするために必要なURLを取得する。
任意の場所にcloneを実施。
(今回は「~/.rbenv/plugins/[ruby](http://d.hatena.ne.jp/keyword/ruby)-build」へ導入する)

```
$ git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build
```

cloneしたものの中に「install.sh」が存在するので実行してインストールをする。

```
$ sudo ~/.rbenv/plugins/ruby-build/install.sh
```

インストールが完了したら以下のコマンドからインストールできる[ruby](http://d.hatena.ne.jp/keyword/ruby)のバージョンの一覧が確認できるようになっているはず。

```
$ rbenv install -l
```




```
(neovim3) [nishijima@localhost ~]$ rbenv install 2.6.3
Downloading ruby-2.6.3.tar.bz2...
-> https://cache.ruby-lang.org/pub/ruby/2.6/ruby-2.6.3.tar.bz2
Installing ruby-2.6.3...
Installed ruby-2.6.3 to /home/nishijima/.rbenv/versions/2.6.3
(neovim3) [nishijima@localhost ~]$ rbenv global 2.6.3
(neovim3) [nishijima@localhost ~]$ gem install neovim
```



## npm install

```
  curl -sL https://rpm.nodesource.com/setup_10.x | bash -
  yum install nodejs
  node -v
  npm -v
  npm update -g
```



## vim-go

init.vim

```
Plug 'fatih/vim-go'
Plug 'prabirshrestha/async.vim'
Plug 'prabirshrestha/asyncomplete.vim'
Plug 'prabirshrestha/asyncomplete-lsp.vim'
Plug 'prabirshrestha/vim-lsp'
Plug 'mattn/vim-lsp-settings'
Plug 'mattn/vim-goimports'
```

`:PlugInstall`

`:GoInstallBinaries`



### Language Server Install

`:LspInstallServer`





https://goodbyegangster.hatenablog.com/entry/2016/10/04/090734

https://qiita.com/r12tkmt/items/0511f38ed7bd8ce6c022

https://qiita.com/hitochan777/items/941d4422c53978b275f8



https://wonderwall.hatenablog.com/entry/2019/07/28/230000

### NeoVim + vim-go + lsp

https://qiita.com/tobita0000/items/22d314515f009e721740



