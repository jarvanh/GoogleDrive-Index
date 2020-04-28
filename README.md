Google Drive Index
====  
基于 [Cloudflare Workers](https://workers.cloudflare.com/) 和 [Google Drive](https://www.google.com/drive/) 的功能，部署在Cloudflare Workers，实现以目录形式展示Google Drive中的文件。

`index.js` 包含 Workers 所需的代码。

## 部署
1. 在本地安装 rclone   
2. 按照 https://rclone.org/drive/ 流程进行授权
3. 执行 rclone config file 查看 rclone.conf 路径。找到root_folder_id和refresh_token记录下来  
4. 编辑 index.js  并填入 root 和 refresh_token  
5. 复制代码 到 Cloudflare Workers 部署


## 文件夹密码：
在Google Drive 文件中放置 `.password` 文件来设置密码。

密码文件只能保护该文件不被列举，不能保护该文件夹的子文件夹不被列举。也不保护文件夹下文件不被下载。

程序文件中 `root_pass` 只为根目录密码，优先于 `.password` 文件  
