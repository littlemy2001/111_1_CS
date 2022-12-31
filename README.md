# 111_1_CS 實習課筆記
# W1  
# Git&Linux的簡介
* Git
  * 免費、開源的專案管理工具
  * 記錄版本更動情形
  * 分散式系統
* Linux
  * 免費、開源的作業系統
  * 提供基本功能，如鍵盤輸入、螢幕輸出
  * 輕量系統，用於處理巨量資料
  * 常用於雲端部署
# W2
# Linux 背景知識與實作
* Linux 背景知識
  * Linux
    * 一種自由開放原始碼的類Unix作業系統
    * 廣泛運用於伺服器和嵌入式系統中
  * 發展與線上升級
    * 版本會分為：
      1. 開發中版本為奇數：2.5.x
      2. 穩定版本為偶數：2.6.x4
    * 可透過線上升級
  * 使用者與群組
    * 身份分類：user (owner)/group/others
    * 身分類別：系統管理員： root和一般帳號
  * 指令圖(取自講義)
    * <img width="398" alt="image" src="https://user-images.githubusercontent.com/113632844/210129333-4abeef1a-7a88-4a56-b6bb-3445dba9c940.png">
    * <img width="400" alt="image" src="https://user-images.githubusercontent.com/113632844/210129336-9151b2e4-9830-4da0-8c41-3eb55a17aa8d.png">
# W3
# Linux 背景介紹與實作
* Linux 背景介紹
  * 壓縮檔案
    * 壓縮時的考慮因素：壓縮率、壓縮時間、所需記憶體空間、相容性(解壓縮程式的普遍性)
    * 壓縮格式的選擇：
      1. gzip：需要在記憶體很小的機器（如<128MB）上解壓縮時，或很簡單、沒有什麼工具可用的機器解壓縮時
      2. xz：需要節省網路頻寬、縮短下載所需要的時間時
      3. tar.xz：需要有最好的壓縮率時
    * Linux指令：壓縮檔案、檔案搜尋、檔案&文字相關(詳見講義)
  * 資料傳輸
    * 圖表(取自講義)
      * <img width="621" alt="image" src="https://user-images.githubusercontent.com/113632844/210131287-162426de-7e8c-4645-a452-4c84b242bf02.png">
    * Port：埠號是由 16 個位元所組成的號碼，0 ~ 255 為保留號碼，256 ~ 65535 則可自行設定。
    * TCP/IP：提供了點對點的連結機制，**將資料如何封裝、定址、傳輸、路由以及在目的地如何接收，都加以標準化**。
# W4
# 正則表達式與Linux 文字處理工具
* 正則表達式
  * .：代替所有可能的字元（字母、數字或符號）
  * ?：比對或不比對前一個字串
  * 星號：比對前一個字串零次或是多次
  * -：EX：product[A-K] → productA、productB、productC...
  * +：至少要與前一個字比對一次或以上
  * |：或者
  * ^：比對前開頭
  * $：錢字符號則是比對結尾
  * \：恢復成一般字元
  * ()：把想找的相關字詞放入括號內，可依照括號裡的字元排序找到可能的結果
  * []：任意比對字串內的每個項目
* Linux 文字處理工具
  * grep：從資料或檔案中，使用關鍵字或正規表達法(Regex)找出想要的內容，如：grep [option] filename
  * grep參數與其他文字處理工具就看講義
# W5
# awk 指令與sed 指令
* awk 文字分析工具：用在對文字和資料進行分析處理、檔案逐行的讀入
  * <img width="469" alt="image" src="https://user-images.githubusercontent.com/113632844/210132961-29cc722f-7979-4b27-b11b-7c3ea172daa3.png">
  
    第一步執行BEGIN 語句
  
    第二步從檔案或標準輸入讀取一行，然後再執行pattern語句，逐行掃描檔案到檔案全部被讀取
    
    第三步執行END語句
  * awk record & field：對Linux來說，每一行讀進來皆為新的一行，因此為$0
  * awk 語法的常用引數：
    * -F 指定分隔符(可是字串或正規表達法)，預設是空白(space)
    * -f 從指令碼檔案(awk script)中讀取awk命令
    * -v var=value賦值變數，將外部變數遞給awk
  * awk 參數：
    * $0：當前record（橫行）
    * $1~$n：當前record的第 N 個欄位
    * FS：比對前一個字串零次或是多次
    * RS：輸入record（列、橫行）分割符，預設換行符
    * NF：欄位個數
    * NR：record 數，就是行號，預設從 1 開始
  * awk 算術運算子、關係運算子、邏輯運算子、正則運算子
  
    <img width="211" alt="image" src="https://user-images.githubusercontent.com/113632844/210133704-08617af4-31ea-4b07-b613-625b12ca0137.png">
    <img width="217" alt="image" src="https://user-images.githubusercontent.com/113632844/210133710-c3c23bc5-2634-40c7-8d99-77854ec940b1.png">
    <img width="215" alt="image" src="https://user-images.githubusercontent.com/113632844/210133719-984c5a1b-f966-474d-a477-f8116b8f9345.png">
    <img width="246" alt="image" src="https://user-images.githubusercontent.com/113632844/210133726-e7609ff7-a17f-4adc-832d-05507c48a944.png">
* sed文字分析工具：字串取代、複製、刪除
  * Sed語法 – 常用選項、常用指令、常用旗幟
  
    <img width="354" alt="image" src="https://user-images.githubusercontent.com/113632844/210134041-cff6d458-3237-4ab9-acba-1f1f14ea278b.png">
    <img width="403" alt="image" src="https://user-images.githubusercontent.com/113632844/210134050-b371f056-b84b-435a-8cec-345b4be52f02.png">
    <img width="162" alt="image" src="https://user-images.githubusercontent.com/113632844/210134085-ddfc8a17-0409-4bd1-8208-df3746dc8900.png">
  * Grep, Awk, Sed的比較
    * grep：文字搜尋工具
    * awk：文字分析工具
    * sed：線上編輯器
# W6、W7
# Git
  * Git的特色
    * 儲存檔案重要資訊，如:編輯者、版本資相關資訊
    * 可藉由repository和共同編輯者分享資料，先進行編輯的人的內容也不會被覆蓋掉
    *Git體積小、速度快
  * Git指令
    * 初始化專案：git init
    * 單一檔案加入索引(暫存區)：git add <檔案名稱>
    * 所有檔案加入索引(暫存區)：git add .
    * 觀看當前狀態：git status
    * 瀏覽歷史紀錄：git log 
  * 使用 SSH 金鑰與 GitHub 連線和Git的使用方法(看講義操作)
# Git Flow 
  
* 主要目的：規範多元協作可能出現的衝突，主要有5個分支
  * Master分支：主要是用來放穩定、隨時可上線的版本，只能從別的分支合併過來。
  * Develop和Feature分支：Develop是所有開發的基礎分支，在新增功能的時會從這個分支切出去 Feature分支，功能完成後，再合併回來這個分支。
  * Hotfix分支：當發生緊急問題的時會從Master分支開一個Hotfix分支出來進行修復，修復完成之後，會合併回Master和另一份到Develop分支。
  * Release分支：當認為Develop分支成熟時，會合併到Release分支，在這邊進行上線前的最後測試。測試完成後，Release 分支會同時合併到Master、Develop分支上。
