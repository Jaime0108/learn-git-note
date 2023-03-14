

# 常用命令

### Linux的命令

+ 编辑文件

  ```
  vim 1.txt
  
  按i键 变成 INSERT 模式
  
  编辑完成 ESC > shift+: > wq+Enter
  ```

+ 查看文件

  ```
  cat 1.txt
  ```





### 设置用户签名

> 用以区分不同开发人员的标识   可以在任意目录中设置

```java
git config --global user.name 'Jaime'
git config --global user.email '1006788336@qq.com'    
```

+ 执行命令生成的文件

  ![](D:\project\GIT\images\执行设置用户签名命令生成的文件.png)

+ 文件的具体内容信息

  ![](D:\project\GIT\images\文件记录的用户信息.png)





### 初始化本地仓库（git init）

> 在项目的文件夹下

```javascript
git init
```

+ 初始化

  ![](D:\project\GIT\images\初始化git目录命令.png)

+ 初始化的结果

  ![](D:\project\GIT\images\初始化的结果.png)







### GIT的工作流程

+ 本地仓库 & 远程仓库工作流程图

  ![](D:\project\GIT\images\git本地仓库&远程仓库的工作流程.png)

##### 查看当前目录状态（git status）

+  查看当前目录状态

  ```javascript
  git status
  ```

  ![](D:\project\GIT\images\查看当前目录git管理状态.png)

##### 添加当前目录所有文件到暂存区（git add .）

+ 添加当前目录所有文件到暂存区

  ```javascript
  git add .
  ```

  ![](D:\project\GIT\images\把当前目录下所有文件都添加到暂存区.png)

+ 把文件添加到暂存区后新的状态

  ![](D:\project\GIT\images\把文件添加到暂存区后新的状态.png)

##### 提交到本地仓库（git commit -m ‘描述’）

+ 提交到本地仓库

  ```javascript
  git commit -m '描述'
  ```

  ![](D:\project\GIT\images\保存到本地仓库.png)

+ 这里有个坑 git commit 不添加 -m '描述'有可能会出现这种情况或者直接报错

  ![](D:\project\GIT\images\在commit时不添加描述可能会发生的情况.png)

##### 查看本地仓库提交历史记录（git log）

+ 查看本地仓库提交历史记录

  ```
  git log
  ```

  ![](D:\project\GIT\images\查看提交本地仓库记录.png)

+ 查看所有的版本

  > 使用git log 只能查看当前指针所在的版本之前的版本

  ```
  git reflog
  ```

##### 版本回退（git reset --hard HEAD^）

+ 版本回退

  ```
  git reset --hard HEAD^
  
  git reset --hard HEAD^^
  
  git reset --hard HEAD~2
  
  git reset --hard 指定前6位commit
  
  git revert
  ```

+ 新建1.txt文件

  ![](D:\project\GIT\images\新建1.txt文件.png)

+ 1.txt文件完成了1功能

  ![](D:\project\GIT\images\项目完成1功能.png)

+ 完成1功能后提交到本地仓库

  ![](D:\project\GIT\images\完成1功能提交到本地仓库.png)

+ 项目完成2功能

  ![](D:\project\GIT\images\项目完成2功能.png)

+ 完成2功能提交到本地仓库

  ![](D:\project\GIT\images\完成2功能提交到本地仓库.png)

+ 项目完成3功能

  ![](D:\project\GIT\images\项目完成3功能.png)

+ 完成3功能提交到本地仓库

  ![](D:\project\GIT\images\完成3功能提交到本地仓库.png)

+ 版本回退

  ![](D:\project\GIT\images\版本回退.png)

+ 版本回退后git的结果

  ![](D:\project\GIT\images\回退版本git的结果.png)

+ 版本回退后1.txt文件的结果

  ![](D:\project\GIT\images\回退版本1.txt文件的结果.png)



##### 回退到指定的版本(git reset --hard 指定前6位commit)

+ 使用reflog查看所有的记录

  ![](D:\project\GIT\images\使用reflog查看所有的操作记录.png)

+ 使用git reset --hard 指定前6位commit 回退到指定的版本

  ```
  git reset --hard 指定前6位commit
  ```

##### 软回退（git reset --soft HEAD^）

+ git reset --hard的这种方式是直接让本地仓库的内容回到工作区

+ 这样会直接修改本地工作区的代码

+ 使用软回退让本地仓库的代码回到暂存区，不会修改本地工作区代码

+ 就类似与撤销一条提交信息,重新commit

  ```
  git reset --soft HEAD^
  ```

##### revert撤销

+ 和reset的区别 工作区的代码的变化是一样的
+ reset的指针是直接移动，revert是会新生成一条记录 



##### 查看分支（git branch）

+ 查看分支

  ```javascript
  git branch
  ```

  ![](D:\project\GIT\images\使用git branch查看分支.png)



##### 创建分支（git branch 新分支名称）

+ 创建分支

  ```
  git branch jaime
  ```

  ![](D:\project\GIT\images\创建分支并查看分支.png)



##### 切换分支（git checkout 分支名称）

+ 切换分支

  ```
  git checkout jaime
  ```

  ![](D:\project\GIT\images\切换分支并查看当前分支.png)

+ 在新分支上创建新的文件

  ![](D:\project\GIT\images\在jaime分支上创建新的文件.png)

+ 在切回master分支对比之前必须提交到本地仓库

  ![](D:\project\GIT\images\在切换分支回到master之前必须提交.png)

+ 在jaime分支查看日志

  ![](D:\project\GIT\images\在jaime分支上查看日志.png)

+ 切回master分支

  ![](D:\project\GIT\images\切回master分支.png)

  ![](D:\project\GIT\images\切回master分支后jaime分支下的jaime文件消失了.png)



##### 合并分支（git merge 分支名称）

+ 合并分支

  > 合并分支要切换到 你想要合并到的那条分支

  ```javascript
  git merge 要合并的分支的名称
  ```

  ![](D:\project\GIT\images\合并分支,出现了合并失败的状况.png)

  > 这里出现了合并失败的情况，后面处理

  ![](D:\project\GIT\images\合并后master分支也有jaime分支的内容了.png)



##### 合并冲突

> 合并冲突产生的原因 两个分支都同时修改同一个文件， 并且要合并

+ 合并冲突

  ![](D:\project\GIT\images\master分支下utils文件的内容.png)

  ![](D:\project\GIT\images\jaime分支下有同名的文件utils也有修改.png)

  ![](D:\project\GIT\images\在master分支下merge jaime分支 有两个文件冲突了.png)

  ![](D:\project\GIT\images\utils文件的冲突情况.png)

  ![](D:\project\GIT\images\手动解决utils文件的冲突，并重新commit.png)
  

##### 删除分支（git branch -b 分支名称）

+ 删除分支

  ```
  git branch -d 指定分支名
  ```

  ![](D:\project\GIT\images\删除分支.png)





# 远程仓库

##### 查看远程仓库

+ 查看远程仓库

  >remote 是远程的意思

  ```
  git remote -v
  ```



##### 添加（连接）远程仓库

+ 添加远程仓库

  > 可以添加多个远程仓库的地址

  ```
  git remote add origin（远程仓库的别名） 远程仓库地址
  ```

  ![](D:\project\GIT\images\添加远程仓库地址.png)

##### 移除远程仓库（连接）

+ 移除远程仓库

  ```
  git remote remove origin
  ```



##### 推送到远程仓库

+ 推送到远程仓库

  ```
  git push origin master:master
  
  简写：git push origin master
  ```
