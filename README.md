# Lab3 5GC信令交換分析
## 實驗要求
此次實驗會提供兩個`.pcapng`檔案，分別是錄製好的open5gs和ueransim的檔案，請將檔案放入wireshark分析和找出答案，並回答以下問題，若題目要求也請給予適當解釋與截圖

``` c=0
目前已知
UE(網卡 uesimtun0)使用指令`ping -I uesimtun0 8.8.8.8`向google請求封包並給予回應，
N11介面的tcp.port == 7777
Uu介面的udp.port == 4997
uesimtun0 ip == 10.45.0.5
```
## 實驗環境示意圖
![Screenshot 2025-11-10 at 11.39.37 AM](https://hackmd.io/_uploads/H1x9ACRJbg.png)

## 實驗題目
### A. IP addr
請找出以下要求的IP addr
- UE
- gNB
- AMF/UPF(N2/N3) interface
- UPF(N6) Interface

### B. Uu介面
1. 請找出UE總共向 google.com 封包，請問來回總共要求了幾筆？
2. 請問在ping的封包中，UE傳送的data(value)是什麼？請給與解釋並截圖
3. 在封包分析中，可以觀察到從UE傳出的封包，隨後再由8.8.8.8回傳封包，請說明這兩個封包方向的意義與它們之間的關係。

### C. N1/N2介面
1. 找到N1/N2介面的截圖，並回答各自使用的通訊協定是什麼？
2. 請說明IMSI與MCC,MNC,MSIN的關係。
3. 請選擇N1或N2介面找出UE的IMSI，並解釋為什麼選擇該介面，並附上截圖證明。

### D. N11介面（AMF <-> SMF）
1. 請透過已知的N11介面的`tcp.port == 7777`找到AMF <-> SMF的封包並截圖
2. 請選擇任意一個封包，並點選右鍵選則decode as...，將TCP port最右邊的current改成http2![Screenshot 2025-11-10 at 1.08.26 PM](https://hackmd.io/_uploads/SkDLmgJgZx.png)
3. 請找出N11中的IMSI，並觀察是否與N1/N2介面中的一致（需付截圖）？[使用follow功能]
4. 請找出SMF設定UE的UEAggregateMaximumBitRate是多少Kbs（需付截圖）?[使用follow功能]
5. 請問為什麼需要使用follow功能？

### E. N3介面
1. 請找出N3介面的截圖，並回答N3介面使用的通訊協定。
2. 請問在N3介面中，來回總共有幾筆ping的封包？請找到參數證明並截圖。
3. 請問N3與Uu介面中的ping封包數是否相同？請解釋並附上截圖證明。
4. 請問ping的value是什麼？請給與解釋並截圖。


### F. 加分題
1. 請問N1,N2,N11可不可以看到User傳送的value(Data)?為什麼？
2. 如果封包從UE傳送至 google.com，請問外層與內層的source與destination IP分別是多少(需付截圖）？
6. 為什麼需要分內層與外層？







