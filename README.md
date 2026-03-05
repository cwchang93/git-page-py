# Iris 資料分析（Python 初學者專案）

這是一個適合初學者的 Python 資料分析範例，使用 `pandas`、`numpy`、`matplotlib` 進行 Iris 資料集分析，並可部署到 GitHub Pages。

## 專案結構

- `data/`：可選的本機資料檔案資料夾
- `notebooks/analysis.ipynb`：Jupyter Notebook 分析檔
- `site/index.html`：簡易首頁
- `site/analysis.html`：由 Notebook 轉出的 HTML 分析報告
- `.github/workflows/deploy.yml`：GitHub Pages 自動部署流程
- `requirements.txt`：Python 相依套件清單

## Notebook 內容

- 載入資料集（Iris）
- 基本探索式資料分析（EDA）
- 直方圖視覺化
- 依物種進行 `groupby` 分析
- 最後結論整理

## 本機執行方式

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter nbconvert --to html notebooks/analysis.ipynb --output analysis.html --output-dir site
```

完成後，用瀏覽器開啟 `site/index.html`。

## GitHub Pages 部署

每次推送到 `main` 分支時，GitHub Actions 會自動：

1. 安裝相依套件
2. 將 Notebook 轉換為 HTML
3. 上傳 `site/` 資料夾作為 Pages artifact
4. 部署到 GitHub Pages
