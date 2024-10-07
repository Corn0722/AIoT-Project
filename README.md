# 智慧物聯網實作與應用 - 智慧藥盒

## 動機
隨著醫療科技進步，老年人平均壽命提高，用藥管理成為一項重要課題。本研究提出一款智慧藥盒，結合自動提醒、安全機制和家庭監控，以提升老年人的用藥依從性和安全性。
期望從藥物方面解決老年人忘記服藥、用藥不當以及家庭照顧困難之問題。

## 四大功能
 - 藥物安全
   - 結合磁力鎖的藥盒設計，確保藥物的安全與完整性。
 - 智能提醒
   - 整合準確的用藥提示與直觀的APP互動界面，提高使用便利性。
 - 遠程監控
   - 家庭成員可實時監控老年人的用藥情況，及時發現異常。
 - 全面健康管理
   - 系統將藥物管理、用藥指導和健康數據分析融為一體，提供全方位的健康服務。

## 使用步驟
1. 用戶透過手機應用程式設定吃藥時間。
2. 在設定的時間到達時，ESP32會使蜂鳴器響一聲及打開相應的LED提醒用戶，並將相應藥格的電磁鎖解鎖。
3. 用戶打開藥盒取藥。
4. 磁簧開關偵測到藥盒被打開，ESP32會記錄並回傳打開的時間。
5. 如果十五分鐘後該藥格仍未被打開，ESP32會觸發蜂鳴器。
6. 如果蜂鳴器響超過十五分鐘且用戶仍未打開該藥格，則ESP32會將蜂鳴器關閉，並發送警告訊息至使用者或其家屬的line。
7. 若於下次吃藥前仍未打開藥格吃藥，會回傳「未吃藥」；若於蜂鳴器停止後至下次吃藥前有打開藥格吃藥，則會回傳「未準時吃藥」。
8. 用戶可以隨時透過手機應用程式查看吃藥的統計數據。
<img width="50%" src="https://github.com/user-attachments/assets/9d19111f-2572-456e-92a2-55453b43281b"/>

## 系統架構圖
<img width="50%" src="https://github.com/user-attachments/assets/991e6aa1-8454-4716-8040-03c222419579"/>

### App介面與實際藥盒：
<img width="30%" src="https://github.com/user-attachments/assets/716d3aa4-99ba-4810-b0b7-744ee0467324"/>
<img width="25%" src="https://github.com/user-attachments/assets/2cc2f2f2-1399-485e-a51c-ee52136696e2"/>

<img width="50%" src="https://github.com/user-attachments/assets/2e0d42a5-8afc-436c-8891-5dc76477a295"/>

## 資料庫架構
 - data_and_time_settings : 此次吃藥時間(起始日期、結束日期、幾點要吃)
 - record : 打開藥盒時間、該次吃藥狀態(準時、未準時、未吃)
 - information : 記錄吃藥資訊(為何吃藥、吃甚麼藥、長期or短期)

## 開發工具
 - 前端：Flutter
 - 後端：Firebase
 - 硬體：Arduino ESP32

## 作者
 - 沈之晅
 - 郭奕里
 - 梁珉毓([@Corn0722](https://github.com/Corn0722))
 - 張芸婕
