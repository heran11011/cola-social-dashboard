# ColaOS 数据看板部署包

这个目录是给 GitHub Pages 用的公开预览包。

只上传本目录里的文件：

- `index.html`
- `.nojekyll`
- `README.md`，可选

不要上传这些内容：

- `.env`
- `data/`
- `data/cola_monitor.sqlite`
- `scripts/`
- `web/dashboard.html`
- 整个项目根目录

## GitHub Pages 发布步骤

1. 在 GitHub 新建一个仓库，例如 `cola-social-dashboard`。
2. 只把 `deploy/` 目录里的文件上传到仓库根目录。
3. 进入仓库 `Settings` -> `Pages`。
4. `Source` 选择 `Deploy from a branch`。
5. `Branch` 选择 `main`，目录选择 `/root`。
6. 保存后等待 1-2 分钟，访问 GitHub 给出的 Pages 链接。

每次本地数据更新后，先运行：

```bash
source .venv/bin/activate
python scripts/run_pipeline.py
```

然后重新上传 `deploy/index.html`。

注意：GitHub Pages 页面本质上是在线网页。即使只是发给团队看，也要按公开页面处理，不要放 API Key、数据库、原始接口响应或内部调试页。
