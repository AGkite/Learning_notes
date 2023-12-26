# 设置代理

```text
Git 添加代理：
git config --global http.proxy http://127.0.0.1:7890
git config --global https.proxy http://127.0.0.1:7890
Git 删除代理：
git config --global --unset http.proxy
git config --global --unset https.proxy
------------------------------------------------------------------------------------------------
Npm 添加代理：
npm config set proxy="http://127.0.0.1:7890"
npm config set https-proxy="http://127.0.0.1:7890"
Npm 删除代理：
npm config delete proxy 
npm config delete https-proxy
------------------------------------------------------------------------------------------------
Yarn 添加代理：
yarn config set proxy http://127.0.0.1:7890
yarn config set https-proxy http://127.0.0.1:7890
Yarn 删除代理：
yarn config delete proxy
yarn config delete https-proxy
------------------------------------------------------------------------------------------------

Registry 设置
# 淘宝源
npm config set registry https://registry.npmmirror.com
yarn config set registry https://registry.npmmirror.com

# npm源
npm config set registry https://registry.npmjs.org/
yarn config set registry https://registry.npmjs.org/
------------------------------------------------------------------------------------------------
Python Pip
# 设置代理
pip config set global.proxy http://127.0.0.1:7890
# 设置源
pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
# 删除代理
pip config unset global.proxy
```