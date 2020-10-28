#Postman #Mock-Server


# Mock Server
---

## 建立 Mock Server 流程

1. 新增Collection，並輸入 Collection Name，本範例為 `TryMockServer`

	![截圖 2020-10-28 下午9.29.19.png](https://github.com/Yian8068/PostmanMock/blob/main/截圖%202020-10-28%20下午9.29.19.png)

2. 在左側找到剛建立好的Collection，並點其右側選單 `Mock` > `Add mock`

	![截圖 2020-10-28 下午9.32.59.png](https://github.com/Yian8068/PostmanMock/blob/main/截圖%202020-10-28%20下午9.32.59.png)

3. 輸入相關資訊後，點擊 `Create Mock Server` 

	> 依自己需求勾選下方選項

	![[截圖 2020-10-28 下午9.36.20.png]](https://github.com/Yian8068/PostmanMock/blob/main/截圖%202020-10-28%20下午9.36.20.png)	

	至此，Mock Server 已建立完成

	![[截圖 2020-10-28 下午9.44.50.png]](https://github.com/Yian8068/PostmanMock/blob/main/截圖%202020-10-28%20下午9.44.50.png)	

> 此Mock Server為掛載在Postman伺服器上
> 基本上只要有網路，就可以連得上

---

## 建立Collection共享變數

Mock Server的Url 通常會是一串醜醜的連結，每次複製貼上會很麻煩，只要把它存成共享變數就可以重複使用囉！

1. 滑鼠游標移到剛建好的Mock Server，點擊複製連結的圖示

	![[截圖 2020-10-28 下午9.50.56.png]](https://github.com/Yian8068/PostmanMock/blob/main/截圖%202020-10-28%20下午9.50.56.png)	

2. 點擊Collection右側的選單，選 `Edit`

	![[截圖 2020-10-28 下午10.02.06.png]](https://github.com/Yian8068/PostmanMock/blob/main/截圖%202020-10-28%20下午10.02.06.png)	

3. 切換至 `Variables`，並在下方填入變數

	`VARIABLE` : 變數名稱，之後以 `{{變數名稱}}` 取得Value，此例為 `{{mock-url}}`
	`INITIAL_VALUE`: 變數的初始值，把剛才複製的Mock Server Url貼在這裡
	`CURRENT_VALUE`: 變數目前的值，可以不用動它

	![[截圖 2020-10-28 下午10.03.21.png]](https://github.com/Yian8068/PostmanMock/blob/main/截圖%202020-10-28%20下午10.03.21.png)	

---

## 建立Mock API 流程

1. 對Collection點擊右鍵，點擊 `Add Request`

	![[截圖 2020-10-28 下午10.12.26.png]](https://github.com/Yian8068/PostmanMock/blob/main/截圖%202020-10-28%20下午10.12.26.png)	
	
2. 填入 `Request name` 後，儲存
	可以輸入API的功能名稱、用途(中英文皆可)
	此例為建立取得使用者資訊的API，故為 `get_user_info`
	![[截圖 2020-10-28 下午10.14.33.png]](https://github.com/Yian8068/PostmanMock/blob/main/截圖%202020-10-28%20下午10.14.33.png)	

3. 打開 Request，並填入API相關資訊，依個人需求填寫
	> 如先前所述，共享變數可用大括號取得
	![[截圖 2020-10-28 下午10.18.43.png]](https://github.com/Yian8068/PostmanMock/blob/main/截圖%202020-10-28%20下午10.18.43.png)	
	
	此例為 `{{mock-url}}/user/1` 並使用 `GET` 方式呼叫
	![[截圖 2020-10-28 下午10.22.00.png]](https://github.com/Yian8068/PostmanMock/blob/main/截圖%202020-10-28%20下午10.22.00.png)	
	
4. 接下來建立此API的模擬Response，右側 `Example` >  `Add Example`
	
	![[截圖 2020-10-28 下午10.24.45.png]](https://github.com/Yian8068/PostmanMock/blob/main/截圖%202020-10-28%20下午10.24.45.png)	
	
5. 按需求填寫模擬的Response，填好右上角儲存
	`Name` : Example的名字
	`Url` : 填寫Url Pattern，呼叫Pattern的Url就會回傳下方的Response
	`Body`: 最重要的 Response Body
	`Status`: Http Status Code

	![[截圖 2020-10-28 下午10.29.31.png]](https://github.com/Yian8068/PostmanMock/blob/main/截圖%202020-10-28%20下午10.29.31.png)	

	> 重複步驟4、5，即可建立多筆Example
	> ![[截圖 2020-10-28 下午10.38.17.png]](https://github.com/Yian8068/PostmanMock/blob/main/截圖%202020-10-28%20下午10.38.17.png)	

至此就建立好 Mock的 API Response

## 測試

回到 Request 的頁面，點擊 `Send`

### 成功的Response
![[截圖 2020-10-28 下午10.41.16.png]](https://github.com/Yian8068/PostmanMock/blob/main/截圖%202020-10-28%20下午10.41.16.png)	

### 失敗的Response
![[截圖 2020-10-28 下午10.41.31.png]](https://github.com/Yian8068/PostmanMock/blob/main/截圖%202020-10-28%20下午10.41.31.png)	


## End

Mock Server 教學告一段落
