# 6.828安装环境

因为本机是m1芯片的mac，arm架构的安装虚拟机再模拟qemu环境坑有些多，正好阿里云学生机可以免费申请2.5个月的，
于是干脆直接申请了一个阿里云服务器，网速也是杠杠的。

云服务器环境如下：
- Ubuntu20.04 x86
- Python2.7
# 步骤

## 安装依赖与Python2.7

```
# 安装编译⼯具
sudo apt install -y build-essential gdb
# 安装 32-bit 库
sudo apt install gcc-multilib

sudo apt-get install python2.7

# 其他的一些依赖
apt-get install build-essential zlib1g-dev pkg-config libglib2.0-dev binutils-dev libboost-all-dev autoconf libtool libssl-dev libpixman-1-dev libpython-dev pythonpip python-capstone virtualenv

```
## 安装qemu

qemu是⼀个模拟x86-64硬件的模拟器
可以通过动态的二进制转换，模拟CPU，并且提供一组设备模型，使它能够运行多种未修改的客户机OS。
通过动态的二进制转换，模拟CPU，并且提供一组设备模型，使它能够运行多种未修改的客户机OS，QEMU支持仿真各种体系结构

```
git clone http://web.mit.edu/ccutler/www/qemu.git -b 6.828-2.3.0

```

## 配置qemu

```
cd qemu
sudo ./configure --disable-kvm --target-list="i386-softmmu x86_64-softmmu" --
python=python2.7
```

之后运行`make`, `make install`


