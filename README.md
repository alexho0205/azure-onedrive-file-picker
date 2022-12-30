# azure-onedrive-file-picker
網頁串接 OneDrive 檔案選取 , 讓用戶在檔案上傳的時候可以選擇 OneDrive 裡的檔案.

本專案是由 Azure 提供 SSO 範例檔,再自行加入 onedrive.js 
原專案說明可以參考 Origin.README.md 

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

