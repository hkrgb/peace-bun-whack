# 平安包打地鼠

長洲太平清醮主題的 16:9 HTML 小遊戲。玩家在限時內拍中冒出的平安包：普通包 20 分、金色包 50 分，達到目標後以 `postMessage` 把實際分數帶回視覺小說。

## 設定

可在 `config.json` 修改遊戲時間、目標分數、每種包的分數、出現速度及停留時間。

完成時送出：

```js
window.parent.postMessage({ complete: true, score }, '*');
```

遊戲背景由 OpenAI 內置圖像生成工具製作；參考圖只用作美術方向。
