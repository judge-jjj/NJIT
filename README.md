# 南京工程学院江宁校区三维云校园

两份 Shapezo GLB 按各自的 ENU 经纬度原点合并为 `campus-merged.glb`。网页直接加载该文件显示原始建筑网格及纹理，不再叠加手绘建筑、操场、道路或湖泊。Three.js 和总平面参考图已内置在 `index.html` 中，无 CDN、地图接口或其他外部运行时依赖。

## 文件

- `index.html`：完整静态查看器，约 5.8 MB。
- `campus-merged.glb`：完整合并模型，约 43.9 MB。必须与 `index.html` 同目录上传。
- `README.md`：本说明。
- `.gitignore`：忽略本地临时文件。

## 本地查看

推荐在本目录运行 `python -m http.server 8000`，然后打开 `http://localhost:8000/`。如果直接双击 `index.html`，浏览器通常不允许 `file://` 网页自动读取旁边的 GLB；点击页面上的“选择本地 GLB”，选取 `campus-merged.glb` 即可。

鼠标左键旋转、滚轮缩放、右键平移；手机上单指旋转、双指缩放和平移。侧栏可搜索地标并移动镜头。原始地表默认显示，树木实例和塔架默认关闭；可在侧栏底部切换。这些几何均完整保留在 GLB 中。

## 部署到 GitHub Pages

1. 把上述四个文件放在仓库根目录。`campus-merged.glb` 小于 GitHub 单文件 100 MB 限制，不需要 Git LFS。
2. 打开仓库 **Settings → Pages**，将 **Build and deployment** 设为 **Deploy from a branch**，选择 `main` / `(root)` 并保存。
3. 等待 Pages 完成发布，访问页面给出的 `https://用户名.github.io/仓库名/` 地址。

首次访问需要下载约 44 MB 模型，移动网络可能较慢。

## 数据说明

两块模型按源文件 ENU 原点和经纬度进行米制平移，未改变原始几何。总平面图地标是视觉参照，位置为近似配准，不适用于导航、测绘或规划审批。原始模型本身的覆盖范围和细节有限，地表拼接边缘仍可见一条浅色接缝；这不是网页额外生成的道路或建筑。
