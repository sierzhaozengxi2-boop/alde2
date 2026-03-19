# node-cf-worker-vless-xu

`node-cf-worker-vless-xu` 是一个将 `_worker.js` 部署在 Cloudflare Worker 上，`index.js` 部署在 Node.js 环境中的项目。

- `_worker.js` 仅保留核心部分。
- `index.js` 可以运行在 Node.js 环境中（记得复制一份 `package.json`），还可以作为 `_worker.js` 的 `/proxyip=wss://`，直连需要 `uuid`，`proxyip` 不需要验证（属于公益性质）。（proxyip都不要带 https://）

---

## 🌟 极简版

> **_worker.js_**  
> - **100 行**  
> - **3500 字节**  
> - **功能**: 只保留直连和 `/proxyip=`

> **_index.js_**  
> - **57 行**  
> - **1966 字节**  
> - **功能**: 只保留直连

---

## 用法参考

## vless-ws-tls
### 不要配置信息，vless是关键词，会被检测到

<div align="center">
	<a href="https://nless-generate.abc15018045126.dpdns.org/" target="_blank" style="font-size:1.2em;font-weight:bold;">
		🚀 <b>节点生成</b>
	</a>
	<br>
	<a href="https://stock.hostmonit.com/CloudFlareYes" target="_blank" style="font-size:1.1em;">
		🌐 <b>优选IP</b>
	</a>
</div>

<div align="center">
	<b>用法说明</b>
	<ul style="text-align:left;max-width:500px;margin:auto;">
		<li><b>节点生成：</b>点击上方链接，自动生成 VLESS 节点配置，适用于本项目。</li>
		<li><b>优选IP：</b>点击上方链接，获取 Cloudflare 可用优选 IP，提升连接速度和稳定性。</li>
		<li>将生成的节点配置和优选 IP 替换到下方示例中的 <code>&lt;hidden-domain&gt;</code> 或 <code>&lt;hidden-node-domain&gt;</code> 部分即可。</li>
	</ul>
</div>


### CF 直连

```
vless://2ea73714-138e-4cc7-8cab-d7caf476d51b@<hidden-domain>:443?encryption=none&security=tls&sni=<hidden-domain>&fp=randomized&allowInsecure=1&type=ws&host=<hidden-domain>&path=%2F#nless1
```

### 使用 `/proxyip`

#### 示例 1: `/proxyip=ProxyIP.US.CMLiussss.net`

```
vless://2ea73714-138e-4cc7-8cab-d7caf476d51b@<hidden-domain>:443?encryption=none&security=tls&sni=<hidden-domain>&fp=randomized&allowInsecure=1&type=ws&host=<hidden-domain>&path=%2Fproxyip%3DProxyIP.US.CMLiussss.net#nless2
```

#### 示例 2: `/proxyip=wss://<hidden-node-domain>.railway.app`

```
vless://2ea73714-138e-4cc7-8cab-d7caf476d51b@<hidden-domain>:443?encryption=none&security=tls&sni=<hidden-domain>&fp=randomized&allowInsecure=1&type=ws&host=<hidden-domain>&path=%2Fproxyip%3Dwss%3A%2F%2F<hidden-node-domain>.railway.app#nless3
```

### Node 示例

```
vless://2ea73714-138e-4cc7-8cab-d7caf476d511@<hidden-node-domain>.railway.app:443?encryption=none&security=tls&sni=<hidden-node-domain>.railway.app&fp=randomized&allowInsecure=1&type=ws&host=<hidden-node-domain>.railway.app&path=%2F#nless-production
```

---


---

## 推荐工具

## 已经测试Cloudflare，node平台railway
### Cloudflare

推荐使用 [Cloudflare Dashboard](https://dash.cloudflare.com/)。

### Node 隧道

可以参考 [eooce/nodejs-argo](https://github.com/eooce/nodejs-argo)。

### 部署平台

#### 三幻神

- [Render](https://render.com)（代理容易封号）
- [Railway](https://railway.app)
- [Fly.io](https://fly.io)（可能需要卡）

#### 古神

- [Replit](https://replit.com)（牢大太牢了）

#### 其它 Node.js 平台（玩具）

- [Cyclic.sh](https://www.cyclic.sh)
- [Qovery](https://www.qovery.com)
- [Koyeb](https://www.koyeb.com)
- [Northflank](https://northflank.com)

#### 函数平台（不行）

- [Vercel](https://vercel.com)
- [Netlify](https://www.netlify.com)

#### 容器平台

- [Heroku](https://www.heroku.com)

---

#### Deno

- [Deno Console](https://console.deno.com/)
- Entrypoint: `deno.tsx` (其它留空)
- 部署方法：
- 1.Fork本项目到自己Github账号下
- 2.访问Deno控制台，先创建一个新项目
- 3.在创建的新项目里，点击右上角创建（New app）按钮
- 4.在左侧连接Github账号，完成授权操作，选择Github账号，选择对应的存储库
- 5.在App Directory下点击Edit app config按钮，找到Entrypoint*选项
- 6.填入`deno.tsx`，关闭，点击Create app，然后部署即可
- 注意：Appname和fork存储库尽量不要使用默认名称，此方法仅做备用使用
- vless://2ea73714-138e-4cc7-8cab-d7caf476d51b@这里填入你的deno地址:443?encryption=none&security=tls&type=ws&host=这里填入你的deno地址&path=%2F#这里填入你想要取名的节点名称
- 粘贴到支持的订阅客户端即可

#### dockerhub
- [Docker Hub](https://hub.docker.com/r/xuwenjiesmith/node-xu)

## 🙏 感谢

### `_worker.js` 感谢

- [zizifn](https://github.com/zizifn/edgetunnel)
- [3Kmfi6HP](https://github.com/6Kmfi6HP/EDtunnel)
- [cm](https://github.com/cmliu/edgetunnel)

### `index.js` 感谢

- [eooce](https://github.com/eooce/nodejs-argo)
- [勇哥](https://github.com/yonggekkk/sb-nodejs)

---

## 🌟 感谢你的 Star

[![Stargazers over time](https://starchart.cc/abc15018045126/node-cf-worker-vless-xu.svg)](https://starchart.cc/abc15018045126/node-cf-worker-vless-xu)
