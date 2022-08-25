## 直播購物說明書

> 上半部寫給客戶，下半部寫給技術人員

### 藍圖

整個大的直播購物系統，是由幾個小的系統組合而成，小的系統例如購物車、直播下單、尋找潛在客戶系統等等。

### 購物車
* 為什麼要導入購物車，不直接使用 Google 表單完成？  
  Google 表單的主要問題有二：一是無法動態生成內容，比如小計、加總。二是過於彈性，沒有會計對帳背景的人，設計出來的表單，會造成日後對帳非常困難，可以說是近乎不可能。
* 為什麼購物車要自己寫，不直接使用別人的？  
  1. 因為將來還有新需求，這個時期不是自己寫的，將來無法擴充，或是擴充程度有限，或是價格高昂，都不理想。
  2. 這個系統以後要對外賣其他業者，到時仍要考慮壓低成本，初期租用只能暫時解決問題，無法盈利。

### 直播下單
喊+1就可以訂單成立，背後原理是代入會員資料，讓整個訂購流程更加流暢，增加有效訂單數字。

### 尋找潛在客戶
要找到有興趣的客戶，找對1個、2個客戶，勝過找錯100個、1000個。仔細思想怎麼突破，不一定是用技術解決問題。

----

> 下半部寫給技術人員參考，若非技術人員可以讀到這邊結束，下面沒有其他內容了。

### 購物車筆記

```python
ecom/
  cart.html    # 2 購物車
  detail.html  # 1-2 單項商品，可以下單選細項
  list.html    # 1-1 查看商品列表
  payment.html # 3 訂單成立，轉帳資訊
```

### API
#### 商品
<details>
 <summary>GET /products/&lt;product_id&gt; 查看商品</summary>
 ...this is hidden, collapsable content...
</details>
<details>
 <summary>POST /products/add 新增商品</summary>
 ...this is hidden, collapsable content...
</details>


#### 訂單
<details>
 <summary>GET /orders/&lt;order_id&gt; 查看訂單</summary>
 ...this is hidden, collapsable content...
</details>
<details>
 <summary>POST /orders/add 新增訂單</summary>
 
  <pre>[
  {
    "orderId": "10001",
    "orderDetail": [
      {
        "productId": 1003,
        "productAmount": 3
      },
      {
        "productId": 1004,
        "productAmount": 2
      }
    ],
    "memberInfo": {},
    "paymentInfo": {},
    "shippingInfo": {},
    "createdAt": "2022-08-25 11:00:03",
    "updatedAt": "2022-08-25 11:00:03"
  }
]</pre>
</details>

### 購物車存在 localStorage
```js
window.localStorage.getItem('ami')
window.localStorage.setItem('ami', amiString)
```
