
[官方手册](https://docs.yoctoproject.org/brief-yoctoprojectqs/index.html)  

## 搭建yocto环境

```shell
mkdir yocto
cd yocto
git clone git://git.yoctoproject.org/poky -b poky_codename
```
### 1. git clone  
	从上面可以看到`**git clone**`的时候使用的是git协议拉取的code，可能部分开发者的环境受限制无法使用git协议， 这时候请使用https协议替换
```shell
	git clone https://git.yoctoproject.org/poky -b poky_codename
```
但是因为yocto有不少recipes也使用了git协议，这时候我们需要通过git来修改
```shell
	git config --global url.https://.insteadOf git://
```
### 2. poky_codename
	codename是指定poky的不同分支，因各个分支上的配置可能有较大差异，因此我们需要指定一个来进行开发， 我们可以从[这里](https://wiki.yoctoproject.org/wiki/Releases)查到codename的相关信息

## 构建yocto
### 1. setup编译环境
```shell
	source poky/oe-init-build-env
	bitbake core-image-sato
```
	在这里需要注意，每次打开新的终端的时候都需要执行一次，另外尽量把`MACHINE`设置到环境变量，这样可以避免每次打开终端都要设置`MACHINE`的环境变量，当然在这里也有更好的方法在`build/conf/local.conf`中指定默认的MACHINE

