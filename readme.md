ubuntu编译安装python_Ubuntu 编译安装Python3.6

weixin_39918961 2020-12-20 09:30:19  150  收藏
文章标签： ubuntu编译安装python
版权

你是做IT的料吗？来挑战一下
50+专题演讲、现场代码PK、黑客马拉松，14大沉浸式应用场景……不说了，报名要紧
Ubuntu 编译安装Python3.6

安装环境 Ubuntu 16.04 amd64

最好不要卸载系统自带的Python，可能会导致系统错误，因为系统中的好多软件都依赖Python

安装依赖#安装编译套件

sudo apt install build-essential checkinstall

#安装其他依赖

sudo apt install libreadline-gplv2-dev libncursesw5-dev libssl-dev libsqlite3-dev tk-dev libgdbm-dev libc6-dev libbz2-dev

下载源码并编译

Python下载地址https://www.python.org/downloads/ 选择自己需要的版本下载,我下载的是3.6.6版本prefix:指定安装目录;enable-optimizations：启用优化选项(LTO，PGO等)，启用编译很慢;# 下载源码

wget https://www.python.org/ftp/python/3.6.6/Python-3.6.6.tgz

# 解压

tar -zxvf Python-3.6.6.tgz

# 进入目录

cd Python-3.6.6/

#编译安装

./configure --prefix=/usr/local/python3.6 --enable-optimizations

make -j4 && make -j4 install

建立软连接# 备份原有Python命令的软连接

mv -f /usr/bin/python /usr/bin/python.bak

# 建立新的Python链接

ln -sf /usr/local/python3.6/bin/python3.6 /usr/bin/python

ln -sf /usr/local/python3.6/bin/python3.6 /usr/bin/python3

# 备份原有pip命令的软连接

mv -f /usr/bin/pip /usr/bin/pip.bak

# 建立新的pip链接

ln -sf /usr/local/python3.6/bin/pip3 /usr/bin/pip

ln -sf /usr/local/python3.6/bin/pip3 /usr/bin/pip3

输入python -V 出现Python 3.6.6表示安装成功

本文由 HanYibo 创作，采用 知识共享署名4.0 国际许可协议进行许可

本站文章除注明转载/出处外，均为本站原创或翻译，转载前请务必署名

最后编辑时间为: Jul 30, 2018 at 09:25 pm
————————————————
版权声明：本文为CSDN博主「weixin_39918961」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/weixin_39918961/article/details/111721460
