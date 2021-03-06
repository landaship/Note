# linux 常用命令

# 1.查看系统内核版本：（内存管理、进程调度等跟机器硬件交互）

终端命令：

```
cat /proc/version
```
linux内核版本：

```
Linux version 2.6.32-431.el6.x86_64 (mockbuild@c6b8.bsys.dev.centos.org) 
gcc 版本：(gcc version 4.4.7 20120313 
red hat 版本：(Red Hat 4.4.7-4) (GCC) ) 
#1 SMP Fri Nov 22 03:15:09 UTC 2013
```

# 2.系统版本：（图形操作界面，人机交互）
终端命令：cat /etc/redhat-release
输出：CentOS release 6.5 (Final)

# 3.vim查找文字，查找下一个按N
:/8080

# 4.远程登录linux命令
ssh 用户名@ip
ssh root@192.168.1.63

# 5.linux 查找文件
find / -name ‘smtp_settings.rb'

# 6.linux目录作用
var ：日志、备份等，/var/opt/gitlab/backups
opt：额外的配置文件，一般是不需要去修改的， /opt/gitlab/embedded/service/gitlab-rails/config/gitlab.yml
etc：配置文件存放，一般存放软件的启动配置文件，/etc/gitlab/gitlab.rb

# 7.用mac 端远程ssh linux服务器，终端显示乱码的问题
## 7.1.在终端下输入
vim ~/.zshrc
## 7.2.在文件内容末端添加：
export LC_ALL=en_US.UTF-8  
export LANG=en_US.UTF-8
接着重启一下终端，或者输入source ~/.zshrc使设置生效。

# 8.查看端口是否被占用

 lsof -i:8080
 
 # 9.查看磁盘还有多大
 df -hl
 
 df -h 查看每个根路径分区的大小
 
 
# 9.如何用终端下载 文件
 wget -O CodeReview https://download.jetbrains.8686c.com/upsource/upsource-2017.1.1922.zip
 
 
# 10.设置屏幕是否锁定

```swift
if (self.appIdleTimerDisabled || self.mediaModuleIdleTimerDisabled) {
    //不自动锁屏
   [UIApplication sharedApplication].idleTimerDisabled = YES;****
} else {
    //自动锁屏
   [UIApplication sharedApplication].idleTimerDisabled = NO;
}
```

## 11.两台linux 文件拷贝（参考https://blog.csdn.net/qq_30968657/article/details/72912070）
scp root@192.168.90.155:/root/testCp.txt root@192.168.1.67:/root
规则：
主机登录名字@ip：文件路径  空格 目标主机登录名字@ip：存放路径

## 12.删除某个文件以外的全部文件

```
# shopt -s extglob      （打开extglob模式）
# rm -fr !(file1)
 
如果是多个要排除的，可以这样：
# rm -rf !(file1|file2) 
```

# 13.系统莫名其妙的出现各种命令找不到
可能是因为系统环境变量没有了

```
#vi /etc/profile
```
让环境变量立即生效需要执行如下命令：  

```
#source /etc/profile 
```
添加了如下java运行环境

```
# For JDK 1.6.0_45
export JAVA_HOME=/usr/local/java/jdk1.6.0_45/
export JRE_HOME=/usr/local/java/jdk1.6.0_45/jre
export PATH=$JAVA_HOME/bin:$JRE_HOME/bin:$PATH
export CLASSPATH=.:$JAVA_HOME/lib.dt.jar:$JAVA_HOME/lib/tools.jar:$JAVA_HOME/lib:$JRE_HOME/lib
```

# 14.查找linux 大型文件
搜索 /u01/app/oracle/oradata/prod/ 下，超过500M大小的文件

```
find /u01/app/oracle/oradata/prod/  -type f -size +500M
```


