注意：I鍵上的ot已經改為第二韻母
現時I鍵上的ot和oet都是第二韻母。
如果一個鍵沒有編排第二韻母，那麼用第一聲母或第二聲母的鍵都可以輸入聲母。
鍵位圖未更新，以本文字説明為準。

關於38鍵和40鍵：
本方案使用40鍵的鍵盤佈局，但實際編碼只用到38鍵，逗號和句點不參與編碼。

簡要説明：
1. 本輸入方案用到粵拼的碼表jyutping.dict.yaml
   同時也用到明月拼音作反查之用
   請確保用户文件夾下有相關文件（可以從東風破或稱懶人包獲得）
2. opencc文件夾內的文件必須放到用户文件夾下的opencc子文件夾
3. 如使用同文，jyutsoeng.trime.custom.yaml並不能直接使用。
   打開後可見裏面包含三個鍵盤，需要把你想用的鍵盤複製到主題文件中。
4. symbolsy.yaml重新定義了符號的輸入方式（以y鍵引導符號輸入，詳見後文的説明），
   必須同時放入用户文件夾，否則本方案不能正常工作。

詳細操作步驟：
1. 先確定自己的rime文件夾（用户文件夾）的位置。
   Android下通常是/sdcard/rime，並可在同文的設置界面看到。
   rime文件夾內應該有default.yaml, trime.yaml等文件。
   電腦端取決於具體平台。如仍有疑問，請到羣裏諮詢，或參閲github上相關説明。
2. 粵語雙拼使用的是粵拼的碼表，所以請保證rime文件夾下有jyutping.dict.yaml
   如沒有此文件，請到羣裏或到github.com/rime/plum下載。
   同時反查要用到明月拼音，所以請同樣從上述網址下載luna_pinyin.dict.yaml和luma_pinyin.schema.yaml
3. 解壓之後，將jyutsoeng.schema.yaml放入rime文件夾，opencc文件夾下的東西放到rime文件夾下的opencc子文件夾。
4. 如果需要使用粵語雙拼的助記鍵盤，將jyutsoeng.trime.custom.yaml的內容複製到自己所用的主題文件的用戶配置文件最後，並保存。
   如果需要使用中文字助記鍵盤，還需將jyutsoeng.custom.yaml放入。
   例如使用的是同文風主題，則需將jyutsoeng.trime.custom.yaml的內容貼到tongwenfeng.custom.yaml的最後。
   使用默認主題的話請貼到trime.custom.yaml最後。
   如果不使用助記鍵盤佈局，或使用的是電腦端，則不需執行這一步。
5.  在rime的設置中啓用粵語雙拼，並重新部署。即可使用。
6.  電腦端的選重鍵默認是大寫字母，可以自行在jyutsoeng.schema.yaml中配置。

鍵位圖說明：每個鍵上藍色字表示的是第一聲母和第一韻母。
紅色字表示的是第二聲母和第二韻母。
含有第二韻母的字必須用對應的第二聲母的鍵搭配輸入。
例如L鍵的第一韻母是eng，第二韻母是oeng。
那麼輸入seng的方法是SL，而soeng則需用對應的第二聲母爲s的鍵輸入，也就是0L
如果一個第二韻母在多個鍵上出現，則可用其中任意一個鍵來輸入。
例如上面的soeng也可以用0S來輸入。

中文字助記鍵盤説明：
左撘左，右撘右，中間搭兩邊。
即位於左邊的韻母只能跟位於左邊或中間的聲母搭配，
　位於右邊的韻母只能跟位於右邊或中間的聲母搭配，
　位於中間的韻母可以跟任意聲母搭配。

另提供左搭右，右搭左，中間搭兩邊的鍵盤。搭配規則同理。

零聲母字的輸入方法：
以aa, e, o, u爲韻腹的字都有兩種輸入方法。
可以用首字母加韻尾輸入，也可以用首字母加上整個韻母的鍵輸入。
例如aak對應的鍵是8，那麼零聲母的aak可以用AK或者A8輸入。
以a爲韻腹的字只能用第二種方法輸入。例如零聲母的ak應用A7輸入。
零聲母的aa, e, o本身通過重複打該鍵兩次輸入。
即用AA輸入aa，用EE輸入e，用OO輸入o
類似地，用VV輸入ng（五）這個音節，用MM輸入m（唔）這個音節。

符號的輸入方法：
y鍵是符號輸入的引導鍵，例如yfh可輸入多種符號，ysb可以輸入上標等。
拼音縮寫以粵拼為準。例如星座名應輸入yszm而非yxzm
收錄的符號集與系統自帶的symbols.yaml相同。

容錯碼：
由於按照原始的編排規則最多可以表示34*38=1292個音節，大於粵語中實際存在的音節數。
故嚴格按照上面的規則會有大量空碼。
為了充分利用這些空碼，部分音節可以用其他的方法輸入，這些碼可以認為是容錯碼。
容錯碼與基本碼之間有一定的對應規律，但難以詳述。
可在具體使用過程中熟悉，不需記憶。
總之本方案可以保證按照碼位圖和上面的規則輸入一定能打出想要的音節，
但可能會有其他方法也能錄入同樣的音節。
（關於34：本方案實際編碼字符為38個，但其中i, y, ;, /四個鍵不作首碼）

容錯碼係為有效利用編碼空間而設，並非模糊音，
為鼓勵粵語的標準發音，本方案不提供n/l，ng/零聲母等
常見模糊音或懶音，如有需要請自行添加。

本作品的所有部分均係按CC-BY-NC-SA 4.0協議授權，轉載、部分轉載或二次創作需符合相關條款規定。
