# Notion 圖片比較小工具 v2

## 功能

-   比較畫面不再顯示圖片下方的滑桿；直接拖曳圖片上的分隔線。
-   可選擇 3:4、4:5、9:16、1:1、4:3、16:9 比例。Notion
    區塊可調整寬度，比例會保持不變。
-   可在編輯器選取圖片，直接上傳至自己的 GitHub
    公開儲存庫，並自動填入圖片網址。
-   可設定圖片標籤、提示詞與是否顯示。
-   取得嵌入連結後，在 Notion 輸入 `/embed` 並貼上連結。

## 部署到 GitHub Pages

1.  將 `index.html` 上傳或覆蓋到原本啟用 GitHub Pages 的儲存庫。
2.  等待 GitHub Pages 部署完成。
3.  開啟你的 Pages 網址，進入編輯器並設定圖片與比例。

## 直接從編輯器上傳圖片到 GitHub

此功能會把圖片上傳到你指定的 GitHub
儲存庫，並自動將圖片網址填入比較工具。由於 Notion
需要能公開讀取圖片，存放圖片的儲存庫必須是 **Public（公開）**。

### 第一步：建立或選擇圖片儲存庫

1.  登入 [GitHub](https://github.com/)。
2.  建立新的儲存庫，或選擇你已經有的 **公開（Public）** 儲存庫。
3.  記下儲存庫名稱；稍後只需填名稱，不需要貼上完整網址。

> 如果你已經有專門存放比較圖片的公開儲存庫，可以直接使用，不必另外建立。

### 第二步：建立 Fine-grained Personal Access Token

1.  開啟 GitHub 的 [Fine-grained token
    建立頁面](https://github.com/settings/personal-access-tokens/new)。
2.  在 **Token name** 輸入容易辨識的名稱，例如 `Image Compare Upload`。
3.  **Expiration** 選擇有效期限。建議依實際使用需求設定較短期限，例如 30
    或 90 天；到期後可重新建立。
4.  **Resource owner** 選擇擁有目標儲存庫的 GitHub 帳號或組織。
5.  在 **Repository access** 選擇 **Only select
    repositories**，再從清單中選取要存放圖片的那一個儲存庫。
6.  在 **Repository permissions** 找到 **Contents**，將權限設為 **Read
    and write**。
7.  確認沒有額外開啟不必要的權限。GitHub 自動附加的 **Metadata:
    Read-only** 是正常設定。
8.  按下 **Generate token** 建立 Token，並立即複製保存。GitHub
    通常只會在建立時顯示完整 Token。

**權限設定重點：** - Repository access：**Only select
repositories**，只選擇指定的圖片儲存庫。 - Repository
permissions：**Contents → Read and write**。 -
不需要為了這個上傳功能授予其他不相關權限。

### 第三步：在比較工具中設定上傳資訊

回到已部署的 GitHub Pages 編輯器，在 GitHub 上傳設定欄位填入：

-   **GitHub 帳號／組織**：目標儲存庫的擁有者名稱。
-   **Repository／儲存庫名稱**：只填儲存庫名稱，不要填完整網址。
-   **Branch／分支**：填儲存庫實際使用的分支，例如 `main`。
-   **Folder／資料夾**：可使用工具提供的預設值；若自行指定，確認該路徑可寫入。
-   **Token**：貼上剛建立的 Fine-grained Personal Access Token。

選取要上傳的圖片，按下「上傳選取的圖片」。成功後，工具會把圖片網址自動填入圖片
A／B 欄位。請先確認預覽正常，再複製嵌入連結並貼到 Notion。

### 安全注意

-   **不要把 Token 貼到
    Notion、提示詞、分享連結、公開程式碼或聊天訊息中。** 也不要將 Token
    提供給他人。
-   這個工具會在瀏覽器端使用
    Token；請只在自己信任的工具頁面及裝置上使用。瀏覽器擴充功能或遭竄改的頁面可能接觸到你輸入的
    Token。
-   請將 Token 限定在單一儲存庫，並只授予必要的
    `Contents: Read and write` 權限。不要使用擁有更廣泛權限的 Token
    代替。
-   Token
    只在當前頁面記憶體中使用，不會寫入分享連結，也不會儲存到瀏覽器；頁面重新整理或完成上傳後需重新輸入。
-   若不再需要，或懷疑 Token 外洩，請到 GitHub 的 [Personal access
    tokens
    設定頁](https://github.com/settings/personal-access-tokens)撤銷它。
-   公開儲存庫中的圖片可被任何人讀取；不要上傳公司機密、私人或未授權素材。
-   目前限制單張圖片 10 MB 以下。

### 常見問題

-   **找不到儲存庫：** 確認 Resource owner 正確，且 Repository access
    已選取該儲存庫。
-   **上傳時出現權限錯誤：** 確認 Token 尚未過期，並確認目標儲存庫的
    `Contents` 權限是 `Read and write`。
-   **分支錯誤：** 到 GitHub 儲存庫確認實際分支名稱，再填入工具設定。
-   **圖片上傳成功但 Notion 看不到：**
    確認儲存庫是公開的，且工具預覽中的圖片網址能正常開啟。

## Notion 使用方式

1.  在編輯器設定圖片、標籤、提示詞與顯示比例。
2.  按「複製／取得嵌入連結」。
3.  回到 Notion 輸入 `/embed`，貼上連結。
4.  可拖曳 Notion 區塊邊緣改變顯示寬度；圖片比例保持設定值。

## Notion 內直接編輯的限制

一般 Notion 頁面不能把第三方網頁編輯器直接變成原生 Notion
編輯區塊。這版採用最簡單可靠的流程：在獨立編輯器設定並複製嵌入網址，再貼入
Notion。若要在 Notion 內直接操作，需要另行開發 Notion 整合或自訂應用。
