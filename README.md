抓取股價分鐘資料並存入 InfluxDB 資料庫
-----------------
從 Google Finance 上抓取台灣上市公司股價資料，並且存入 InfluxDB 資料庫中


init_influxdb.ipynb：初始化InfluxDB股價資料庫
-------------------
本程式會由抓取全台灣911家上市公司的分鐘資料作為 InfluxDB 資料庫的初始資料，執行過一次之後日後的資料更新請執行 update_influxdb.ipynb檔，上市公司的名單資料存在 tw_stocks.pkl 檔中，由 grap_taiwan_stock_list.ipynb 檔案抓取，其中資料來源是由 台灣證券交易所 取得資料上市公司資料。


update_influxdb.ipynb：更新InfluxDB股價資料庫
--------------------
請先執行過 init_influxdb.ipynb 檔，本程式預設是抓取分鐘頻率的資料，而 Google Finance 只保留最近15天的分鐘資料，因此要累積資料的話需要至少每15天更新一次資料庫。