# azure-onedrive-file-picker
網頁串接 OneDrive 檔案選取 , 讓用戶在檔案上傳的時候可以選擇 OneDrive 裡的檔案.

本專案是由 Azure 提供 SSO 範例檔,再自行加入 onedrive.js 
原專案說明可以參考 Origin.README.md 

## 註冊服務
- 首先你必須有 azure portal 的帳號
- 使用 azure 帳號登入 azre portal 進入 active directory 服務 → 應用程式註冊 → 新增註冊
    - 支援的帳戶類型選擇 →組織&個人
    - URL選擇 → 單頁應用程式 SPA
    - 註冊成功後, 你應該會有識別碼( 如下)
    > 應用程式 (用戶端) 識別碼:
    > 
    > 
    > ………..-……..-……..-……..-……..……..……..cfea
    > 
    > 物件識別碼:
    > 
    > ………..-……..-……..-……..-……..……..……..919
    > 
    > 目錄 (租用戶) 識別碼:
    > 
    > ………..-……..-……..-……..-……..……..……..d34
    > 
- 請將服務加入檔案讀取權限  active directory 服務 → 應用程式註冊 → 點擊你剛才建立的應用程式 → API權限 → 新增權限
    - 選擇 Microsoft Graph
    - 選擇 委派的權限
    - 搜尋 files → 找到 [Files.Read](http://Files.Read) 這個權限並加入到API

## 運行本專案

1. Open authConfig.js 調整 clientId 內容
2. Open authConfig.js 調整 redirectUri 位置
3. 回到專案, 使用 vscode 開起, 輸入 ```npn install``` , ```npn start```

## 注意事項

看起來 azure 帳號分為 "組織型" 與 "個人型" 
 - 組織型 : 例如公司買一堆帳號發給員工,帳號的owner是"組織" , 並不是員工個人.
 - 個人型 : 例如我用私人帳號購買了azure帳號.

如果用戶的 azure 帳號是屬於"組織型" , 使用API串接必須是 Microsoft 的合作夥伴.
差別在哪? 以下說明
 - 我在 trello 上傳檔案時, 使用公司 azure 帳號串接 onedrive , 運作正常.
 - 我在 cymmas 上傳檔案時, 使用公司 azure 帳號串接 onedrive , 運作NG  ( 因為 cymmas 不是 Microsoft 的合作夥伴 )

