

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





### 初始化本地仓库

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

##### 查看当前目录状态

+  查看当前目录状态

  ```javascript
  git status
  ```

  ![](D:\project\GIT\images\查看当前目录git管理状态.png)

##### 添加当前目录所有文件到暂存区

+ 添加当前目录所有文件到暂存区

  ```javascript
  git add .
  ```

  ![](D:\project\GIT\images\把当前目录下所有文件都添加到暂存区.png)

+ 把文件添加到暂存区后新的状态

  ![](D:\project\GIT\images\把文件添加到暂存区后新的状态.png)

##### 提交到本地仓库

+ 提交到本地仓库

  ```javascript
  git commit -m '描述'
  ```

  ![](D:\project\GIT\images\保存到本地仓库.png)

+ 这里有个坑 git commit 不添加 -m '描述'有可能会出现这种情况或者直接报错

  ![](D:\project\GIT\images\在commit时不添加描述可能会发生的情况.png)

##### 查看本地仓库提交历史记录

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

##### 版本回退

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



##### 回退到指定的版本

+ 使用reflog查看所有的记录

  ![](D:\project\GIT\images\使用reflog查看所有的操作记录.png)

+ 使用git reset --hard 指定前6位commit 回退到指定的版本

  ```
  git reset --hard 指定前6位commit
  ```

##### 软回退

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



##### 查看分支

+ 查看分支

  ```javascript
  git branch
  ```

  ![](D:\project\GIT\images\使用git branch查看分支.png)

+ 创建分支

  ```
  git branch jaime
  ```


