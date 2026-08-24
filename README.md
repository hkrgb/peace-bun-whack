# 平安包打地鼠

長洲太平清醮主題的 16:9 HTML 小遊戲。玩家在限時內拍中平安包可得 40 分，誤拍蛋撻會扣 20 分。結算後按「回到故事」，以 `postMessage` 把實際分數帶回視覺小說。

## 設定

可在 `config.json` 修改遊戲時間、目標分數、每種包的分數、出現速度及停留時間。

完成時送出：

```js
window.parent.postMessage({ complete: true, score }, '*');
```

遊戲背景及透明平安包由 OpenAI 內置圖像生成工具製作；參考圖只用作美術方向。蛋撻以分層 CSS 繪製，避免外部圖片依賴。

## 管理後台

`admin.html` 使用 Firebase Google Authentication，只允許 `info@rgb-workshop.com`。後台可修改所有前台文字、難度、遊戲時間、目標分數、平安包加分、蛋撻扣分及出現率，設定發佈到 Firestore 後由前台直接讀取。
