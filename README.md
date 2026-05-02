# OPENCLAW HTML Hub

This repository is the public GitHub Pages site for OPENCLAW HTML output.

Public URL: https://bigdondon421.github.io/

## Responsibility boundary

- V1 is the rule core. It owns judgment, content standards, report logic, naming intent, and any existing OPENCLAW decision rules.
- This repository is only the public delivery layer. It receives final HTML, publishes it through GitHub Pages, and sends the public URL to Telegram through GitHub Actions.
- Do not replace, weaken, or bypass V1 rules with the publishing rules below.
- Do not call Telegram Bot API from OPENCLAW or V1. Telegram delivery is handled only by this repository's GitHub Actions workflow.

## How to publish OPENCLAW HTML

1. Generate the final report according to V1.
2. Convert the final report into one complete public HTML file.
3. Put the HTML file in this repository.
4. Commit it to the `main` branch.
5. GitHub Pages publishes the file automatically.
6. The Telegram workflow sends the public URL through LightChinne automatically.

## File naming

- Morning report: `morning-report/YYYY-MM-DD.html`
- Review / recap: `review/YYYY-MM-DD.html`
- Other reports: `reports/YYYY-MM-DD-short-title.html`

Use the report date in Taiwan time unless V1 explicitly says another timezone is required.

If a file for the same report already exists, update that file only when the new output is a corrected or intended replacement. Otherwise create a distinct filename with a short suffix, for example `reports/YYYY-MM-DD-short-title-v2.html`.

## HTML requirements

- Use a complete HTML document: `<!doctype html>`, `html`, `head`, and `body`.
- Keep CSS embedded in the HTML.
- Do not depend on local files.
- External images or assets must use public HTTPS URLs.
- Do not include private tokens, secrets, cookies, local paths, or non-public credentials.
- The HTML should be directly usable as a static GitHub Pages document.

## Telegram delivery

Repository secrets used by the workflow:

- `TELEGRAM_BOT_TOKEN`
- `TELEGRAM_CHAT_ID`

If the secrets are missing, deployment still works and Telegram delivery is skipped.

## OPENCLAW instruction

Use this instruction for morning reports, reviews, recaps, and future HTML output:

```text
V1 是規則核心。所有內容判斷、報告邏輯、品質標準、風格規範與既有 OPENCLAW 決策規則，都必須先遵守 V1。本段只新增「公開 HTML 發布層」，不得覆蓋、弱化或繞過 V1。

當 V1 完成晨報、複盤、報告或其他需要公開保存的輸出後，請將最終結果轉成完整單一 HTML 檔案，並 commit 到 GitHub repo：bigdondon421/bigdondon421.github.io 的 main 分支。

責任邊界：
- V1：負責內容、判斷、格式品質與核心規則。
- GitHub Pages repo：只負責公開保存 HTML。
- GitHub Actions：只負責部署並透過 LightChinne 把公開網址傳到 Telegram。
- OPENCLAW / V1 不要直接呼叫 Telegram Bot API，不要使用舊 Telegram 發送流程，不要自行傳 Telegram 訊息。

檔名規則：
- 晨報：morning-report/YYYY-MM-DD.html
- 複盤：review/YYYY-MM-DD.html
- 其他報告：reports/YYYY-MM-DD-短標題.html

時間規則：
- 檔名日期預設使用台灣時間。
- 若 V1 對日期或時區有更高優先規則，遵守 V1。

覆寫規則：
- 同一份報告只有在修正錯誤或明確替換時，才覆寫原 HTML。
- 若是新增版本或不同內容，使用新檔名，例如 reports/YYYY-MM-DD-短標題-v2.html。

HTML 要求：
- 必須是完整文件，包含 <!doctype html>、html、head、body。
- CSS 內嵌在 HTML 裡。
- 不依賴本機檔案。
- 圖片或外部資源只能使用公開 HTTPS URL。
- 不得包含 token、secret、cookie、本機路徑或任何非公開憑證。

發布完成後，回傳公開網址即可，例如：
https://bigdondon421.github.io/morning-report/YYYY-MM-DD.html

只要 HTML commit 到 main，GitHub Actions 會自動部署，並透過 LightChinne 把公開連結傳到 Telegram。
```
