檢查當前版本
git --version

檢視設定檔
git config --list

設定git姓名跟email
git config --global user.name "your name"
git config --global user.email "your email"

文字編輯器
:q 離開

cd 移動目錄
cd.. 移動到上一層目錄
ls -al 檢視資料夾

把該資料夾被git控管 生成.git檔案
git init

檢視現在資料夾git狀態
git status

新增檔案被git控管 
把該檔案改變成暫存區
git add <檔名.副檔名>
git add <*.副檔名>
git add --all 一次把全部檔案移動到暫存區

commit檔案改變成本機儲存區
-m是參數 留訊息
git commit -m "message"
一次把檔案移動到本機儲存區
git commit -am "message"
git commit -a -m "message"
必須要給git控管的檔案才能下此指令\
修改最近一次commit訊息
git commit -amend -m "new massage"
=====================
甚麼時候commit
1.沒有一定
2.依個人習慣功能性或時間來決定
3.至少一天會一次

======================
為什麼會做動兩次
1.類似程式碼倉庫管理
2.逐筆確認
3.codereview


==========================
檢視commit紀錄
git log
git log --oneline 精簡模式
文字編輯器
:q 離開

==========================
修改後檔案在工作區內 還沒加到暫存區 
會還原成異動前狀態
*會改變程式碼
git restore <檔名>

修改後檔案已加入暫存區 
改變成工作區狀態 
可以再確認是否要刪除或重新加到暫存區
git restore --staged <檔名>

解除git控管該檔案
git rm --cached <檔名>
通常不想被git控管記錄在.gitigonre來處理

檢視工作區異動比較
git diff
檢視暫存區異動比較
git diff --staged
檢視commit異動比較
git diff <資訊碼> <資訊碼>
檢視每一行程式碼紀錄
git blame <檔名>

移動你的commit版本到該指定版本 回到工作區
git reset HEAD^
git reset HEAD~
git reset <資訊碼>
移動你的commit版本到該指定版本 回到暫存區
git reset <版本> --soft

移動你的commit版本到該指定版本 
*會改變程式碼
git reset <版本> --hard

檢視commit歷史紀錄
git reflog


====================================
分支

檢視目前分支狀態
git branch 
創建分支 會複製現在分支下的所有內容
git branch <new branch name>
移動分支
git checkout <branch name>
git switch <branch name>

合併分支
git merge <branch name>

marge confilct
git不會幫你決定 需要自行修改程式碼
>>>>>> ====== <<<<<< 自行移除
確認好程式碼再重新
git add > git commit

刪除分支
git branch -d <branch name>

創建並移動分支
git checkout -b <branch name>
git switch -c <branch name>

修改分支名
git branch -M <new branch name>
git branch -m <old branch name> <new branch name>

設定遠端儲存區url
git remote add <別名> <remote-url>

貼上
shift + insert

檢視遠端remote url
git remote -v
