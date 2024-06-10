# esp32-class4-markdown-project
Final markdown report

## 基本設置

1. 開啟電腦終端機(cmd)
    ```sh
    pip install esptool
    ```
2. 克隆 ESP-IDF 倉庫：
    ```sh
    git clone --recursive https://github.com/espressif/esp-idf.git
    ```
3. 切換到 esp-idf 目錄：
    ```sh
    cd esp-idf
    ```
4. 安裝 ESP-IDF：
    ```sh
    install
    ```
5. 配置環境變量：
    ```sh
    export
    ```
6. 切換到範例目錄：
    ```sh
    cd examples\get-started\hello_world
    ```
7. 設置目標為 ESP32-S3：
    ```sh
    idf.py set-target esp32s3
    ```
8. 打開配置菜單：
    ```sh
    idf.py menuconfig
    ```
9. 到 Serial flasher config -> 進去 Flash size(點鍵盤右鍵) -> 改成 4MB：
    ```sh
    idf.py fullclean
    ```
10. 清除編譯資料：
    ```sh
    idf.py build
    ```
11. 清除 ESP32S3 板子上的資料：
    ```sh
    esptool.py --chip esp32s3 -p COM6 erase_flash
    ```
12. 編譯並燒入資料到板子上：
    ```sh
    idf.py -p COM6 -b 460800 flash
    ```
13. 顯示在終端上：
    ```sh
    idf.py monitor
    ```
14. 成功出現 hello word

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

5. 清除 esp32 flash：
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
    <img width="600" alt="image" src="https://github.com/leo0525/esp32-class4-picture/blob/main/motion_1.png">

## 注意事項

- 請確保你已安裝並配置好 ESP-IDF 開發環境。
- 在使用 `idf.py` 和 `esptool.py` 命令之前，請確認你的設備已經正確連接到電腦並且端口設置正確。

## 支援

如有任何問題，請參考 [ESP-IDF 官網](https://docs.espressif.com/projects/esp-idf/en/latest/esp32/index.html) 或聯絡相關技術支持。
