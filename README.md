# ISS 追蹤通知程式 🛰️

這是一個自動追蹤國際太空站（ISS）位置的 Python 程式。當 ISS 經過您所在位置的上空，且當時是夜晚時，程式會自動發送電子郵件通知您觀看。

## 功能特點

- 實時追蹤 ISS 位置
- 自動判斷當地日出日落時間
- 當符合觀測條件時發送電子郵件通知
- 每分鐘自動檢查一次

## 必要條件

- Python 3.x
- 網路連接
- SMTP 郵件伺服器設定

## 使用的 API

- ISS Position API: `http://api.open-notify.org/iss-now.json`
- Sunrise-Sunset API: `https://api.sunrise-sunset.org/json`

## 安裝所需套件

```bash
pip install requests
```

## 使用方式

1. 設定您的位置座標：
   ```python
   MY_LAT = 51.507351  # 您的緯度
   MY_LONG = -0.127758 # 您的經度
   ```

2. 設定您的電子郵件資訊：
   - 填入您的 SMTP 伺服器地址
   - 設定您的電子郵件帳號和密碼

3. 執行程式：
   ```bash
   python iss_tracker.py
   ```

## 運作原理

1. 程式會檢查 ISS 是否在您上空（±5度範圍內）
2. 確認當前是否為夜晚時段
3. 當兩個條件都符合時，發送通知郵件
4. 程式每 60 秒自動檢查一次

## 注意事項

- 請確保已正確設定 SMTP 伺服器資訊
- 建議使用環境變數存放敏感資訊（如電子郵件密碼）
- 程式需要持續運行才能進行監測

## 授權

此程式採用 MIT 授權條款。