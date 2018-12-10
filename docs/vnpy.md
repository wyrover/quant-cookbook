## 更新 ubuntu

```
sudo apt-get upgrade
```

锁住文件后

```
sudo rm /var/lib/dpkg/lock
sudo dpkg --configure -a
sudo apt update
```

重新执行

```
sudo apt-get update
sudo apt-get upgrade
```

安装 conda

创建虚拟环境

```
conda create --name vpny python=2.7
```

```
sudo apt-get install mongodb
sudo apt-get install libboost-all-dev
sudo apt-get install cmake
sudo apt-get install git
sudo apt-get install libsnappy-dev
 pip install snappy
```
