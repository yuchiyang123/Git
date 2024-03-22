1.安裝 Git
如果尚未安裝 Git，你需要先下載並安裝它。你可以在Git官方網站找到適合你操作系統的安裝程序。安裝完成後，你可以在終端（或命令提示字元）中使用 Git 命令。

2. 設置使用者名稱和電子郵件
在開始使用 Git 之前，你需要設置使用者名稱和電子郵件地址，這些信息將用於你的 Git 提交記錄。在終端中運行以下命令：


git config --global user.name "Your Name"
git config --global user.email "youremail@example.com"

3. 初始化新倉庫
如果你想要使用 Git 來管理一個新項目，你需要在該項目的目錄中初始化一個 Git 倉庫。在終端中移動到你的項目目錄，然後運行以下命令：

cd C:/AppServ/www

git init

4. 將檔案添加到倉庫
一旦你初始化了 Git 倉庫，你就可以將你的檔案添加到倉庫中，這樣 Git 就可以跟蹤這些檔案的更改。運行以下命令：

git add <filename>

在使用 git add 命令時，如果檔案位於當前目錄下，你只需要指定檔名即可，不需要填寫完整的檔案路徑。但是如果檔案不在當前目錄下，你需要填寫相對路徑或絕對路徑。

假設你要將 example.txt 加入到 Git 的跟蹤清單中：


git add example.txt

這樣就會將 example.txt 加入到 Git 的暫存區中，準備進行下一步的提交。

如果 example.txt 位於某個子目錄下，你可以使用相對路徑：


git add path/to/example.txt

或者如果你在不同目錄下，你也可以使用絕對路徑：


git add /path/to/example.txt

如果你要將整個資料夾上傳到 Git 倉庫中，你可以使用 git add 命令來將資料夾及其中的所有檔案添加到暫存區中。可以使用以下命令：

git add 0621/

如果你不在 C:\AppServ\www 目錄下，你可以使用絕對路徑來指定 0621 資料夾的位置：

git add C:/AppServ/www/0621/

5.提交這些更改到本地儲存庫：

git commit -m "Add 0621 folder"

6.使用以下命令將你的本地儲存庫與剛剛在 GitHub 上創建的倉庫關聯起來（假設你的 GitHub 用戶名為 username，你創建的倉庫名為 repository）：

git remote add origin https://github.com/username/repository.git

7.將你的本地提交推送（push）到 GitHub 上的倉庫中：

git push -u origin master

-u 是指定分支 如果第一次push有加 之後就可以省略-u origin master 直接git push

8.之後要上傳就是

git add 0621/

git commit -m "你的說明"

git push -u origin master

*常用

git clone: 從遠端倉庫克隆一個本地副本。

-- git clone <遠端倉庫的 URL> <目錄名稱>

git pull: 從遠端倉庫拉取並合併最新的更改。

-- git pull直接就可以合併更新專案了...正常來說只要push過就會自動建立跟蹤分支（tracked branch）
如果沒有的話改成 git pull origin <branch> 

git checkout: 切換分支或恢復文件。

-- git checkout <branch_name> 切換分支(前提是那個分支有存在)
-- git checkout -b <new_branch_name> 建立一個新的分支 然後會切換到新的分支
-- git checkout -- <file> 還原上一個檔案的commit(這個沒有很熟**)

git merge: 將一個分支的更改合併到當前分支。

-- git merge master 合併分支 合併的意義是連同舊的分支 所有的紀錄會傳到新的分支 
且舊的分支也不會消失 但在做之前要記得切換到新的分支 這個merge後面要寫的是舊的分支(**切換請看git checkout)

git branch: 顯示、創建或刪除分支。

-- git branch 可以看到這個git的所有分支 以及現在在啥分支
-- git branch -r 確認遠端的分支是啥
-- git branch -a 看本地和遠端的分支(這蠻重要的)

git status: 顯示當前工作目錄的狀態。

-- git status 看現在那些文件被修改過，那些在暫存區，還有未被提交的
status是看到cmd開啟之後的工作內容 不是歷史紀錄(**延伸閱讀git log)
ex.
  Changes not staged for commit:
  	(use "git add <file>..." to update what will be committed) 
  	(use "git restore <file>..." to discard changes in working directory)
        	modified:   .vs/Luck Simulator/v17/.suo

git log: 顯示提交日誌。

-- git log 這個git的歷史紀錄
-- git log --graph 圖形化顯示提交的紀錄和顯示分支合併的情況

git diff: 顯示未提交更改的差異。

-- git diff --staged 顯示你add提交到暫存區的資料跟本地git資料庫進行比對
差異會顯示在下面(但是好像純用git diff啥都不會出現??可能是我錯的emm..)

git reset: 撤銷提交，並移動 HEAD 指針。

(*****請謹慎使用*****)
-- git reset HEAD <file> 取消指定文件到暫存區的修改
-- git reset --soft HEAD~1 取消最後一次的提交 但工作目錄不會受影響
-- git reset --hard HEAD~1 取消最後一次的提交 "並且工作目錄下的文件會消失"
(*****請謹慎使用*****)


git stash: 暫存未完成的更改，以便稍後恢復。
git fetch: 從遠端倉庫下載物件和引用。
git remote: 管理遠端倉庫。
git tag: 標記特定的提交。


