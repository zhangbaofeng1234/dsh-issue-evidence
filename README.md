# dsh-issue-evidence

Screenshots and raw probe output for [anywhere-labs/dsh-desktop#1293](https://github.com/anywhere-labs/dsh-desktop/issues/1293)
—— 桌面端 Markdown 正文本地图片不渲染（`dsh-app://app/` 基址），Web 面同一文档正常。

All material here is a **synthetic reproduction**: a neutral placeholder image generated with Pillow and a two-line
Markdown file. No project or client content is included. Left-side session lists are cropped out.

| File | What it shows |
|---|---|
| `web-image-loaded.png` | Web surface (`http://127.0.0.1:19387/`): the referenced local PNG renders, `naturalWidth = 1200`, `/sidebar/file?…` → **200** |
| `desktop-alt-degraded.png` | Desktop window (`dsh-app://app/`): the same reference renders as **alt text** (`local-image-probe`), **no image node**, **zero requests** |
| `raw-demo-evidence.json` | Raw DOM probe output for both surfaces (baseURI, alt span count, image nodes, request list) |
| `raw-demo-desktop.json` | Desktop-only probe output |
| `raw-evidence.txt`, `raw-web.txt` | Earlier probes against a real 2779-line document (desktop: 24 alt spans / 0 requests; Web: 24/24 loaded, `naturalWidth` 3360–3400) |

Reproduced on: DSH Desktop shell `@deepseek-ai/dsh-desktop` 0.2.0-rc.2, Electron 44.0.0, Windows 11 (10.0.26200),
client plugins `dsh-client-ui-sidebar-documentpreview` / `dsh-client-ui-primitives` 0.2.0-rc.2.
Raw paths in the logs are from the reproduction machine and are already sanitised of credentials.
