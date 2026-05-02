# OPENCLAW HTML Hub

This repository is the public GitHub Pages site for OPENCLAW HTML output.

Public URL: https://bigdondon421.github.io/

## How to publish OPENCLAW HTML

1. Save the OPENCLAW HTML response as an `.html` file.
2. Put the file in this repository.
3. Commit it to the `main` branch.
4. Open it at `https://bigdondon421.github.io/<file-name>.html`.

For the homepage, replace `index.html` and visit https://bigdondon421.github.io/.

## Telegram delivery

After GitHub Pages deploys successfully, the workflow sends the public links for changed `.html` files to Telegram.

Create these repository secrets in GitHub:

- `TELEGRAM_BOT_TOKEN`
- `TELEGRAM_CHAT_ID`

If the secrets are missing, deployment still works and Telegram delivery is skipped.

## OPENCLAW instruction

Use this instruction for morning reports, reviews, recaps, and any future HTML output:

```text
請將本次回覆產生為完整可公開的單一 HTML 檔案，並發布到 GitHub repo：bigdondon421/bigdondon421.github.io 的 main 分支。

檔名規則：
- 晨報：morning-report/YYYY-MM-DD.html
- 複盤：review/YYYY-MM-DD.html
- 其他報告：reports/YYYY-MM-DD-短標題.html

HTML 要求：
- 使用完整文件結構：<!doctype html>、html、head、body。
- CSS、內容、表格、圖表說明全部內嵌，不依賴本機檔案。
- 若使用外部圖片或資源，必須使用公開 HTTPS URL。
- 產出完成後 commit 到 main。
- 發布成功後，以公開網址回傳；GitHub Actions 會自動部署並把連結送到 Telegram。
```
