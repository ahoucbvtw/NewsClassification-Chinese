# NewsClassification-Chinese
This is for Chinese News Classify program. 

It can know witch the input News is for witch classification like Art, Economy, Military, Sport etc...

## Data Pre-process
- Load all the data and change the answer text to number.

  | 計算機(ComputerScience) | 環境(Environment) | 醫藥(Medicine) | 藝術(Art) | 軍事(Military) | 體育(Sport) | 經濟(Economy) | 教育(Education) | 政治(Politics) | 交通(Traffic) |
  |---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|
  | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 |

- Cancel all the Newline, Punctuation and transfer the Chinese sentence to many single words as like English(The English sentence is be combined many of single words).

  Before Pre-process
  
  ![alt text](https://raw.githubusercontent.com/ahoucbvtw/NewsClassification-Chinese/main/Picture/Before%20Pre-process.jpg "Before Pre-process")
  
  After Pre-process
  
  ![alt text](https://raw.githubusercontent.com/ahoucbvtw/NewsClassification-Chinese/main/Picture/After%20Pre-process.jpg "After Pre-process")
  
- CountVectorizer

  Training Data：fit(Show all of labels) / transform(Calculate how many of labels)
  Testing Data：transform(Calculate how many of labels)
  
  *Testing Data should not do fit, because of Training Data was done. The new label can be ignore.*
  
## Train & Verification
  I used **Naive Bayes classifier** to train my news, and as the test data verification, the accuracy can be up to **98%**.
  
  Here is the **Confusion Matrix** below.
  
  ![alt text](https://raw.githubusercontent.com/ahoucbvtw/NewsClassification-Chinese/main/Picture/Confusion%20Matrix.jpg "Confusion Matrix")
  
## Demo
  I find 2021/05/13 Taiwan's two News to demo this classification.
  
  News Link：[比特幣不能買特斯拉了！馬斯克：怕化石燃料挖礦迅增](https://udn.com/news/story/6811/5453859)
  
 ```
輸入新聞內容:

電動車大廠特斯拉（Tesla）執行長馬斯克（Elon Musk）周三（12日）在社群媒體推特上宣布，因為擔心「迅速增加使用化石燃料」 進行比特幣挖礦活動，已經中止接受以比特幣付款購買特斯拉車款。 馬斯克在聲明中表示，特斯拉不會賣出任何比特幣，該公司打算在挖礦活動轉型使用永續能源時，再用它來進行交易。特斯拉也正在研究，是否有其他加密貨幣，每筆交易使用的能源小於比特幣的1%。 特斯拉股價12日下跌4%至589.89美元，上述消息傳出後，盤後再挫低逾1%報580.64美元。 比特幣價格也應聲重挫，一度跌至52,466.99美元，24小時內跌幅約7%。
  
所有類型文章的預測機率: 
[3.20305327e-05 6.51736264e-17 2.73262070e-29 3.75207845e-35 2.96539890e-03 1.48280831e-32 9.97002570e-01 9.19311298e-42 2.50598928e-34 1.46837505e-10]
 
 使用者輸入:  
 ['電動車 大廠 特斯拉 （ Tesla ） 執行長 馬斯克 （ Elon Musk ） 周三 （ 12 日 ） 在 社群 媒體 推特上 宣布 ， 因為 擔心 「 迅速 增加 使用 化石 燃料 」 進行 比特 幣 挖礦 活動 ， 已經 中止 接受 以 比特 幣 付款 購買 特斯拉 車款 。 馬斯克 在 聲明 中 表示 ， 特斯拉 不會 賣出 任何 比特 幣 ， 該 公司 打算 在 挖礦 活動 轉型 使用 永續 能源 時 ， 再用 它 來 進行 交易 。 特斯拉 也 正在 研究 ， 是否 有 其他 加密 貨幣 ， 每筆 交易 使用 的 能源 小於 比特 幣的 1% 。 特斯拉 股價 12 日 下跌 4% 至 589.89 美元 ， 上述 消息 傳出 後 ， 盤後再 挫低 逾 1% 報 580.64 美元 。 比特 幣 價格 也 應聲 重挫 ， 一度 跌至 52 , 466.99 美元 ， 24 小時 內 跌幅 約 7% 。]
 
計算機 的預測機率: 0.0
環境 的預測機率: 0.0
醫藥 的預測機率: 0.0
藝術 的預測機率: 0.0
軍事 的預測機率: 0.0
體育 的預測機率: 0.0
經濟 的預測機率: 1.0
教育 的預測機率: 0.0
政治 的預測機率: 0.0
交通 的預測機率: 0.0

預測結果此文章類型為『經濟』最高！！
 ```
 
News Link：[# 本土新增13例 獅子會再增9例 多與出入萬華地區相關](https://health.udn.com/health/story/120950/5454912)

 ```
輸入新聞內容:

國內新增本土個案13例，新北獅子會群聚新增9例個案，四例與台北市萬華區茶藝館群聚相關。指揮中心指揮官陳時中表示，今天新增的案例基本上都和萬華進出有關係。 陳時中表示，案1245、案1246、案1248、案1250、案1251、案1253及案1255至案1257等9人，為7男2女，年齡介於30多歲至80多歲，其中4人無症狀，5人曾有症狀，發病日介於5月6日至5月11日。9人因曾與案1203於同餐廳用餐，匡列為接觸者並進行採檢，於今日確診；截至目前案1203相關群聚共計20人確診。 案1247、案1252及案1254為40多歲女性、30多歲女性及50多歲女性，分別於臺北市萬華區3家不同之茶藝館工作，3人於5月8日至5月10日間陸續出現症狀，並曾至診所就醫，後續分別於5月11日、5月12日至醫院採檢，於今日確診。 另外，案1249為60多歲男性，5月5日出現乾咳、打噴嚏情形，5月7日出現發燒、肌肉痠痛、喉嚨痛及頭痛症狀，5月10日至診所就醫；個案因持續發燒，5月12日至醫院就醫採檢，於今日確診。衛生單位初步調查，個案會定期於臺北市萬華區活動，研判個案與萬華區茶藝館群聚有地緣相關性；已初步掌握個案接觸者3人，列居家隔離並安排採檢。截至目前萬華茶藝館相關群聚共計7人確診。 陳時中進一步表示，案1203群聚相關個案中，有部分個案曾至臺北市萬華區茶藝館活動；另萬華區茶藝館群聚相關個案中，有個案曾至宜蘭縣礁溪鄉信義路「巨城電玩」遊藝場及宜蘭市新民路「大地球」遊藝場活動，因該2家遊藝場為羅東「銀河百家樂」遊藝場之分店，衛生單位將持續深入調查，以釐清該三起群聚事件的關聯性。 陳時中提醒，個案於可傳染期間曾有公共場所活動史，請曾於附件所列時間及場所活動的民眾，進行14天自我健康監測，如有疑似症狀，儘速戴口罩至指定社區採檢院所就醫，不得搭乘大眾運輸，就醫時請主動告知活動史、接觸史等資訊。 截至目前國內有1256例確診，分別為1068例境外移入，135例本土病例，36例敦睦艦隊、2例航空器感染、1例不明及14例調查中；另案530移除為空號。確診個案中12人死亡、、142人住院隔離中。

所有類型文章的預測機率: 
[3.41103953e-30 3.76793699e-15 1.00000000e+00 6.54538881e-34 1.18613628e-27 2.63895171e-31 9.27300284e-23 4.41759554e-37 1.61851238e-68 2.63694256e-21]

使用者輸入: 
['國內 新增 本土 個案 13 例 ， 新北 獅子會 群聚 新增 9 例 個案 ， 四例 與 台北市 萬華區 茶藝館 群聚 相關 。 指揮中心 指揮官 陳 時 中 表示 ， 今天 新增 的 案例 基本上 都 和 萬華 進出 有 關係 。 陳 時 中 表示 ， 案 1245 、 案 1246 、 案 1248 、 案 1250 、 案 1251 、 案 1253 及案 1255 至案 1257 等 9 人 ， 為 7 男 2 女 ， 年齡 介於 30 多歲 至 80 多歲 ， 其中 4 人 無症狀 ， 5 人 曾 有 症狀 ， 發病 日 介於 5 月 6 日至 5 月 11 日 。 9 人因 曾 與 案 1203 於 同 餐廳 用餐 ， 匡列 為 接觸 者並 進行 採檢 ， 於今 日 確診 ； 截至 目前 案 1203 相關 群聚 共計 20 人 確診 。 案 1247 、 案 1252 及案 1254 為 40 多歲 女性 、 30 多歲 女性 及 50 多歲 女性 ， 分別 於 臺北市 萬華區 3 家 不同 之 茶藝館 工作 ， 3 人 於 5 月 8 日至 5 月 10 日間 陸續 出現 症狀 ， 並曾 至 診所 就醫 ， 後續 分別 於 5 月 11 日 、 5 月 12 日至 醫院 採檢 ， 於今 日 確診 。 另外 ， 案 1249 為 60 多歲 男性 ， 5 月 5 日 出現 乾咳 、 打噴嚏 情形 ， 5 月 7 日 出現 發燒 、 肌肉 痠痛 、 喉嚨痛 及 頭痛 症狀 ， 5 月 10 日至 診所 就醫 ； 個案 因 持續 發燒 ， 5 月 12 日至 醫院 就醫 採檢 ， 於今 日 確診 。 衛生 單位 初步 調查 ， 個案 會 定期 於 臺北市 萬華區 活動 ， 研判 個案 與 萬華區 茶藝館 群聚 有 地緣 相關性 ； 已 初步 掌握 個案 接觸 者 3 人 ， 列 居家 隔離 並 安排 採檢 。 截至 目前 萬華 茶藝館 相關 群聚 共計 7 人 確診 。 陳 時 中 進一步 表示 ， 案 1203 群聚 相關 個案 中 ， 有 部分 個案 曾 至 臺北市 萬華區 茶藝館 活動 ； 另 萬華區 茶藝館 群聚 相關 個案 中 ， 有 個案 曾 至 宜蘭縣 礁溪 鄉 信義路 「 巨城 電玩 」 遊藝場 及 宜蘭市 新民路 「 大 地球 」 遊藝場 活動 ， 因該 2 家 遊藝場 為 羅東 「 銀河 百家樂 」 遊藝場 之 分店 ， 衛生 單位 將 持續 深入調查 ， 以 釐清 該 三起 群聚 事件 的 關聯性 。 陳 時 中 提醒 ， 個案 於 可 傳染 期間 曾 有 公共場所 活動 史 ， 請 曾 於 附件 所 列 時間 及 場所 活動 的 民眾 ， 進行 14 天 自我 健康 監測 ， 如 有 疑似 症狀 ， 儘速 戴 口罩 至 指定 社區 採檢 院所 就醫 ， 不得 搭乘 大眾 運輸 ， 就醫 時請 主動 告知 活動 史 、 接觸 史 等 資訊 。 截至 目前 國內 有 1256 例 確診 ， 分別 為 1068 例 境外 移入 ， 135 例 本土 病例 ， 36 例 敦睦 艦隊 、 2 例 航空器 感染 、 1 例 不明 及 14 例 調查 中 ； 另案 530 移除 為 空號 。 確診 個案 中 12 人 死亡 、 、 142 人 住院 隔離 中 。'] 

計算機 的預測機率: 0.0 
環境 的預測機率: 0.0 
醫藥 的預測機率: 1.0 
藝術 的預測機率: 0.0 
軍事 的預測機率: 0.0 
體育 的預測機率: 0.0 
經濟 的預測機率: 0.0 
教育 的預測機率: 0.0 
政治 的預測機率: 0.0 
交通 的預測機率: 0.0 

預測結果此文章類型為『醫藥』最高！！
