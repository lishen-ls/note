[toc]

# git 命令

## git 基本安装配置

1. 安装 略
2. 配置用户名与 email
   ```
   git config --global user.name "lishen"
   git config --global user.email "lishen_ls@outlook.com"
   ```

## 创建 git 版本库以及简单使用

1. 初始化 git 版本库
   ```
   git init
   ```
2. 添加文件
   ```
   git add xxx.txt
   ```
   > 可一次性添加多个文件`git add file1 file2 file3`
3. 提交文件到仓库
   ```
   git commit -m "test"
   ```
   > -m 是本次提交的说明
4. 查看暂存区和工作区状态
   ```
   git status
   ```
