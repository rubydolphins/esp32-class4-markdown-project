# esp32-class4-markdown-project
Final markdown report

# 基本設置和Terminal 範例執行成功(Hello word & motion)

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
    <img width="600" alt="image" src="https://github.com/leo0525/esp32-class4-picture/blob/main/setting_flasher_config.png">
    
 
10. 清除編譯資料
    ```sh
    idf.py fullclean
    ```
11. 建構編譯資料：
    ```sh
    idf.py build
    ```
12. 清除 ESP32S3 板子上的資料：
    ```sh
    esptool.py --chip esp32s3 -p COM6 erase_flash
    ```
13. 編譯並燒入資料到板子上：
    ```sh
    idf.py -p COM6 -b 460800 flash
    ```
14. 顯示在終端上：
    ```sh
    idf.py monitor
    ```
15. 成功出現 hello word :
    
    <img width="600" alt="image" src="https://github.com/leo0525/esp32-class4-picture/blob/main/hellow_result.png">
    
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
    
# 復原範例執行

此指南將幫助你在 ESP32-S3 上進行 復原範例 的設置和運行。

## 步驟

1. 切換到目標目錄：
    ```sh
    cd C:\Users\leo\esp-idf\examples\get-started\esp-who\examples\esp32-s3-eye
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
7. 板子已恢復成原廠狀態，由左上角按鈕切換模式："鏡頭模式"、"人臉偵測模式"..等，如下圖　：
   <img width="600" alt="image" src="https://github.com/leo0525/esp32-class4-picture/blob/main/re_fig.png">
    

# Cat Face Detection & Web 使用指南

此指南將幫助你在 ESP32-S3 上進行貓臉偵測的設置和運行與將結果顯示在Web上。

## 步驟

1. 切換到目標目錄：
    ```sh
    cd C:\Users\User\esp-idf\examples\get-started\esp-who\examples\cat_face_detection\web
    ```

2. 設置目標為 ESP32-S3：
    ```sh
    idf.py set-target esp32s3
    ```

3. 編譯工程：
    ```sh
    idf.py build
    ```

4. 燒錄固件：
    ```sh
    idf.py flash
    ```

5. 打開監視器：
    ```sh
    idf.py monitor
    ```

6. 執行監視器後，會出現以下畫面，將IP複製起來，即可退出監視器 :
   <img width="600" alt="image" src="https://github.com/leo0525/esp32-class4-picture/blob/main/web-1.png">
    
7. 將電腦的 Wi-Fi 連線到名稱為 Cat Face Detection 的網路 :
   <img width="600" alt="image" src="https://github.com/leo0525/esp32-class4-picture/blob/main/web-2.png"> 

8. 在 Google 網址輸入「步驟6」出現的 IP，例如 `192.168.4.1`。

9. 將畫面的 Resolution 設為 VGA，然後點選 `Start Stream`。將 ESP32 板子對準貓臉，就會出現以下畫面，顯示貓臉以及貓臉偵測框　：
   <img width="600" alt="image" src="https://github.com/leo0525/esp32-class4-picture/blob/main/web-3.png"> 



## 注意事項

- 請確保你已安裝並配置好 ESP-IDF 開發環境。
- 在使用 `idf.py` 和 `esptool.py` 命令之前，請確認你的設備已經正確連接到電腦並且端口設置正確。

## 支援

如有任何問題，請參考 [ESP-IDF 官網](https://docs.espressif.com/projects/esp-idf/en/latest/esp32/index.html) 或聯絡相關技術支持。
