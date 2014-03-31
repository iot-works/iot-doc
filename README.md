##安装pandoc##
这是一个痛苦而又复杂的过程，当然也可以直接下载[Pandoc][0]
[0]:http://code.google.com/p/pandoc/downloads/list

###安装ghc###
port安装ghc

     sudo port install ghc

homebrew安装ghc

    brew install ghc

###编译cabal###

Common Architecture for Building Applications and Libraries2

Cabal是Haskell用于构建应用程序和库的公共架构。

简单的来说它是haskell的包管理，和上面的port、brew 命令类似。

下载地址[http://haskell.org/cabal/][1]

[1]:http://haskell.org/cabal/

解压后

    ghc --make Setup.hs
    ./Setup configure
    ./Setup build 
    sudo ./Setup install

###安装cabal###

安装之前我们需要更新

    cabal update

安装pandoc

    cabal install pandoc

添加到PATH

     export PATH=/Users/fdhuang/.cabal/bin:$PATH

#markdown 转doc#

    pandoc iot.md -o iot.docx

#markdown 转pdf#
这里只针对于安装了mactex

##安装mactex##

下载地址:

[http://mirror.ctan.org/systems/mac/mactex/mactex-basic.pkg][2]

[2]:http://mirror.ctan.org/systems/mac/mactex/mactex-basic.pkg


##markdown转pdf##

不含中文时

     pandoc doc.pandoc doc.pdf   

含有中文时的简单作法

     pandoc --latex-engine=xelatex iot.md -o iot.pdf -V mainfont="SimSun"

