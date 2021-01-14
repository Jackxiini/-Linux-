### 1
在Server服务器上，进入当前用户根目录下的隐藏目录 .ssh，命令如下：
```
cd ~/.ssh
```
### 2
生成私钥和公钥
```
ssh-keygen -t rsa
```
### 3
加载私钥文件
```
ssh-add id_rsa
```
系统如果提示：Identity added: id_rsa (id_rsa) 就表明加载成功了

如果系统提示：could not open a connection to your authentication agent

```
ssh-agent bash
```
### 4 
把公钥拷贝至Client服务器上
```
scp id_rsa.pub user@10.xx.xx.xx:xxx
```
### 5
ssh登录到Client服务器上，然后在Client服务器上，把公钥的内容追加到authorized_keys文件末尾
```
cat id_rsa.pub >> ~/.ssh/authorized_keys
```
### 完成！
