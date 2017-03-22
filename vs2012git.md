Visual Studio 免外掛直接操作 GitHub
 2015-02-01 21:12:25 4708
雖然說 demo 日常在使用的版控是 Visual Studio Online (TFS) ，但是 VSO 是屬於企業使用的 ALM 軟體，所以上面的程式碼並不能直接公開分享，所以對於一些課程或是的文章範例程式還是會放置於時下熱門的 GitHub ，但因為本身平常並不使用 Git 類型的版控所以就很懶得去裝 GitHub for Windows 或是 SourceTree 這類專用軟體，好在 Visual Studio 已經完整支援 Git 指令，不管是本機 Git,GitHub,Bitbucket 只要是 Git 的版控都可以支援，所以這篇文章就是簡單的記錄，如果你剛好也是日常使用非 Git 版控(TFS、SVN)，但有些時候還是要使用 Git 的朋友，一個單純用 Visual Studio 就可以操作 Git 的介紹步驟。

39
SHARES
FacebookGoogle+TwitterMore
當開發人員預期要開發放上 GitHub 的程式時，請先至 GitHub 網站建立 Repository



建立好 Repository 後就可以將專注點回到 Visual Studio 上，先確認 Visual Studio 目前使用的版控系統為 Git

![](/assets/GitHub_VS_01.png)

請開啟 Team Explorer (選單的「檢視」內可以找到）點選「設定」

![](/assets/GitHub_VS_02.png)



選擇 「Git 設定」填上相關資訊

![](/assets/GitHub_VS_03.png)



點選選單，選擇「專案」「連結到 Team 專案」
![](/assets/GitHub_VS_04.png)




選擇「複製」Clone 然後將 GitHub 的 Repository 位置貼上後挑選期望的本機 Git 位置後按下「複製」


完成後雙擊滑鼠左鍵選擇剛剛建立的 GitHub 本機目錄即可連結 Git 專案，預設就是 master 分支，請在此點選「新增」開始建立您的專案

當專案開發到可以簽入的程度後，點擊「變更」



填寫異動描述後按下「認可」即可完成 Commit 的動作



如確定要將這次的 Commit Pull 至 GitHub 請再按下「同步處理」因為是第一次所以需要按「推送」，往後只要按「同步處理」即可



 

Visual Studio 目前已經完整的支援了 Git 指令集，所以只要是 Git 有的功能都是可以達成的，在操作的過程中可能會看到提示安裝「協力廠商 Git 命令提示字元工具」這不是必須的，請參考下方連結，自行決定是否安裝



https://msdn.microsoft.com/zh-tw/library/dd286572%28v=vs.120%29.aspx

 

最後說一下在 Visual Studio 用 Git 的好處，開發人員可以在每個方法、類別等地方的上面看到該方法、類別的修改記錄



甚至可以直接看到修改的是誰，以及直接進行一些操作



但是完整的功能太龐大了，所以如果你有興趣的話可以參考下方的參考連結唷

 