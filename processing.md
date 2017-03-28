
### Processing

入門程式設計的好工具 Processing

![](/assets/processing_book.jpg)
Processing 打造一個簡單易用的程式語言，即使不懂程式設計的新手，也能剪剪貼貼、依樣畫葫蘆動手完成有趣的程式。有趣是個重點，使用 Processing 寫程式就是比其他語言更有趣，因為它著重在「繪圖」，讓你天馬行空的創意能夠藉由撰寫程式發揮出來，讓每個人都能發揮與生俱來的創造藝術能力。

Processing 的起源是 Ben Fry 和 Casey Reas 於 2001 年在 MIT 發展，它以視覺化的方式，讓學習者撰寫電腦程式，就像在畫素描一樣，而 Processing 也將程式碼保存在稱為 Sketchbook 的區域。

O'Reilly 最近出版的一本新書「Processing 入門：互動式圖形實作介紹」（中文版），就是由 Ben Fry 及 Casey Reas 親自撰寫，將這套好用的軟體正式介紹給學習者。


![](/assets/Processing_editor.png)

這是 Processing 網站的一段介紹：

Processing is an open source programming language and environment for people who want to create images, animations, and interactions. Initially developed to serve as a software sketchbook and to teach fundamentals of computer programming within a visual context, Processing also has evolved into a tool for generating finished professional work. Today, there are tens of thousands of students, artists, designers, researchers, and hobbyists who use Processing for learning, prototyping, and production.

安裝 Processing 超級簡單，以 Mac OS X 版本來說，只要下載解壓縮後，拖曳到 Dock 即可使用。



打開 Processing 的主程式，在畫面的編輯區就可以開始寫程式。


學習 Processing 不必先搞懂艱澀的邏輯或語法，從 Example 開始入門就對了，開啟選單「File / Examples」，隨意選擇喜歡的範例程式，開始執行。舉例來說，範例內建的 ColorWheel 執行後會出現這張圖形。

![](/assets/Processing_icon.png)

Processing 常見的指令，都與繪圖相關，例如：打開一個寬高各為200的畫布，繪製一個橢圓形，(x, y)座標是(50, 50)，寬度及高度皆為80。

size(200, 200);
ellipse(50, 50, 80, 80);


當我們想要向教導 for-loop 迴圈的概念時，就可以將程式邏輯與圖形結合起來：

size(200, 200);
for (int i = 0; i <= 50; i+= 10) {
  ellipse(50, 50, 80, 80-i);
}


上面的程式執行後，會產生以下的圖形結果。當學習者動手修改常數或變數，或是加上其它的繪圖指令，就會得到不同的結果。這些結果使用我們人類大腦更樂於接收的「視覺化」方式呈現，有更多學習的樂趣，也可幫助思考，畢竟對許多人來說，要把 printf 印出的一大堆文字和程式的邏輯聯想起來，並不是一件容易的事。
![](/assets/processing_sampleapp.png)


別以為 Processing 就只會「繪圖」的語言而已，它最重要的特色就是能打造「互動式圖形程式」，也就是能用視覺化的圖形來回應使用者的操作，例如可以根據滑鼠游標的位置，來產生一連串的動畫效果。

學習 Processing 只要放輕鬆、當做一種玩樂，每寫幾行、修改幾個字，就馬上執行一下看看效果，多觀摩別人寫的有趣程式，充分發揮自己的想像力完成，說不定寫壞、寫錯的程式還能得到意想不到的效果，畢竟學習就是為了好玩（Just for fun）。

利用 Processing 學習電腦程式的風潮遍及全球，也有許多課程將它納入教學大綱、甚至開設專門教導 Processing 的課程。

比起 C、Java... 等大學課程普遍教導的程式語言，其實 Processing 更適合初學者入門；就像過去很多人曾經使用過 LOGO、BASIC 寫程式的經驗，只需要輸入一些指令，按下執行就會立即跑出結果，既簡單又有趣。
![](/assets/processing_testrun.png)
雖然學會 Processing 可能沒辦法讓你順利找到一份寫程式的工作，你可能也沒辦法利用 Processing 開發一個網站；但是對於初學者來說，樂趣其實比其他一切都更加重要；如果學習者沒辦法對寫程式一見鍾情，無法發掘自己的潛能及熱誠，而硬生生被填鴨一堆程式語言、資料結構及演算法的科目，最後可能也不會有熱誠想從事程式設計工作。

由於 Processing 是開放源碼的軟體，在很多人的支持下，很快就出現各種教學、範例或應用。我認為有一項相當重要的延伸，也就是 Processing.js，它是將 Processing 移植到瀏覽器中執行。

Processing 的 2D/3D 繪圖需要 PostScript、OpenGL 等相關軟體，原始的 Processing 需要下載安裝到電腦中，利用 Java 才能執行。但是近年 Web 及瀏覽器技術的快速發展，HTML5 帶來的 Canvas 及 WebGL、搭配速度飛快的 JavaScript，在大能的 jQuery 創始者 John Resig 原力催化下，誕生 Processing.js 這個可以在瀏覽器中執行的 Processing 相容版本。

執行 Processing.js 需要瀏覽器支援，除了 IE 以外的大多數新版瀏覽器，幾乎都能順利執行 Processing.js，只要測試一下開啟這個網頁，如果能看到範例執行成功的圖形，就代表瀏覽器可以支援 Processing.js。



雖然 Processing.js 支援大多的 Processing 語法及功能，但畢竟瀏覽器是個相對受限制的環境，並非所有 Processing 程式都能被移植到 Processing.js。但是對於教學來說，它的功能已經相當足夠。

Processing.js 帶來很多新的應用可能性，例如 sketchpad 就是以 Processing.js 為基礎的線上編輯器，用瀏覽器打開網頁就能直接寫程式，而執行結果也會立即顯示在網頁上，包含互動式效果也能支援。

這個連結是我用 sketchpad 產生的頁面（畫面如下），程式碼來自 Processing 的 Arm 範例，使用瀏覽器就可以直接觀看、執行這個程式。



使用瀏覽器就能撰寫、執行 Processing 程式，方便學習者互相交流分享與觀摩，由於 Processing 視覺化的特性，讓程式在分享的同時，除了程式碼還會附帶有趣的圖形。這是其它使用者透過 sketchpad 建立的程式，使用相簿的方式展示。



不久前 codecademy 打造了一個只要瀏覽器就能上網學寫程式的平台，有全球超過百萬位學習者上線使用；若使用 Processing 設計教材將會相當有趣，可以一步步教會初學者自己寫程式，並且動手「玩」自己做出來的程式，還能將成果分享給別人。這種帶有藝術創作性質的成果，讓學程式設計也能做出平易近人的作品。

除了瀏覽器，iPhone / iPad 也有專屬的 Processing App，雖然拿手機或平板電腦寫程式有點累；但 Processing 程式簡單易寫，而且通常都是小片段，搭配藍牙鍵盤，或許就能用等公車或喝咖啡的時間學寫程式。



最後，我想再稍微介紹一下 Processing 的胞兄弟「Arduino」。

Arduino 與 Processing 的理想十分接近，如果說 Processing 讓「設計軟體」變得有趣，那 Arduino 就是讓「設計硬體」變得平易近人。

Arduino 是開放式硬體平台，它就像積木一樣，不懂電子的麻瓜，也可以將價格便宜、組合容易的各種電子零件組裝起來，搭配各種感測器（如：溫度、光線、顏色、距離等）、裝置（如：馬達、伺服機等），創造出有趣的應用。

把 Arduino 與 Processing 結合起來，正是 Casey Reas 與 Ben Fry 在書末介紹給讀者的內容。在過去，如果想要打造一個軟硬體整合的裝置，將環境光源與溫濕度變化繪製成 3D 動態影像，多數人可能會覺得這相當科幻，而理工背景的人雖然覺得做得到、但可能太麻煩，但 Arduino + Processing 激盪出的火花，讓這些將科技帶入生活的創意應用，變成像積木玩具般既容易又有趣。

以下是取自 YouTube 的一段 Arduino + Processing 影片，希望讓你也能有「動手玩科技、解放創造力」的想法。
