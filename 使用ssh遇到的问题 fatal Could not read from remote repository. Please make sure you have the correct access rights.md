## 使用ssh遇到的问题 **fatal: Could not read from remote repository. Please make sure you have the correct access rights**

## 你的SSH key没有添加到github帐号设置中

前期初期化仓库

add文件到暂存区，commit文件到仓库区时一切正常

然后

Git push 的时候出现了问题 报了这个错

 **fatal: Could not read from remote repository. Please make sure you have the correct access rights**

**原因：**

### 你的SSH key没有添加到github帐号设置中

解决的方法是 查看本地~/.ssh目录下是否有**id_rsa      id_rsa.pub**这两个文件

id_rsa 是私钥

id_rsa.pub是公钥

cat 一下公钥的内容

然后打开github->Settings->SSHandGPGKeys

new SSH Keys

将公钥复制到这里面

然后 git push git@github.com:xpdygl/reggie.git   (自己的ssh地址)

就可以正常提交文件到远程仓库了。