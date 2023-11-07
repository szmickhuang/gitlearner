### 小试牛刀

1. 生成ssh key以便能login github.com，提交文件
```bash shell
ssh=keygen -t rsa -C "<我指定的emailbox>"
```
在 ~/.ssh/ 目录里， id_rsa文件内是私钥内容，id_rsa.pub文件内是公钥内容。
把公钥内容添加到github的账户 SSH Key 内。

测试密钥有效性：
```bash shell
ssh -T git@github.com
```

出现以下结果为成功：
```bash shell
Hi xxxxxxx<我指定的用户名>! You've successfully authenticated, but GitHub does not provide shell access.
```

2. 在github上创建一个新的repository

3. 在客户机的shell中，自己指定的位置（一般自建directory），clone repository
```bash shell
git clone git@github.com:<github用户名>/<repository name>.git
cd <repository name>
```
此时，已把github上<github用户名>/<repository name>里面的所有内容clone到本地目录中。

4. 一般操作（这里假设我们所有操作都是在本地<repository name>目录里）
假设我们在目录里编辑了一个文件名为 hello_world 的shell文件。

    - 查看状态：
    ```bash shell
    git status
    ```

    - 提交文件（比如前面查看状态已知hello_world文件为 Untracked 状态。
    ```bash shell
    git add hello_world
    ```
    git add命令，可把hello_world加入到暂存区<font color=red>（注意，没实际提交，只是在暂存区）。</font>

    ```bash shell
    git commit -m "<commit log message>"
    ```
    git commit命令，把所有已经加入到暂存区的文件，提交到git库。<font color=red>（注意，这里还没有提交到github.com上，仅仅是本地git库）</font>

    ```bash shell
    git log
    ```
    git log命令，可以查看提交日志。

    - push本地git库中的文件到github上，与github上的库同步
    ```bash shell
    git push
    ```
    git push后，github上的库会根据本地git库的内容更新。
