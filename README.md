# esp32-class4-markdown-project
Final markdown report
# Motion Detection 使用指南

此指南將幫助你在 ESP32-S3 上進行 motion detection 的設置和運行。

## 步驟

1. 切換到目標目錄：
    ```sh
    cd C:\Users\leo\esp-idf\examples\get-started\esp-who\examples\motion_detection\lcd
    ```

2. 設置目標為 ESP32-S3：
    ```sh
    idf.py set-target esp32s3
    ```

3. 清除編譯資料：
    ```sh
    idf.py fullclean
    ```

4. 編譯：
    ```sh
    idf.py build
    ```

5. 清除esp32 flash：
    ```sh
    esptool.py --chip esp32s3 -p COM6 erase_flash
    ```

6. 燒錄：
    ```sh
    idf.py -p COM6 -b 460800 flash
    ```

7. 打開監視器：
    ```sh
    idf.py monitor
    ```

8. 測試 motion detection：
    在鏡頭前揮動手，視窗會顯示 `motion_detection`。

## 注意事項

- 請確保你已安裝並配置好 ESP-IDF 開發環境。
- 在使用 `idf.py` 和 `esptool.py` 命令之前，請確認你的設備已經正確連接到電腦並且端口設置正確。

## 支援

如有任何問題，請參考 [ESP-IDF 官網](https://docs.espressif.com/projects/esp-idf/en/latest/esp32/index.html) 或聯絡相關技術支持。
