# I-Am-Pad  

[![Latest Release](https://img.shields.io/github/v/release/Xposed-Modules-Repo/com.houvven.impad?style=flat-square&logo=github&label=Release)](https://github.com/Xposed-Modules-Repo/com.houvven.impad/releases/latest)
[![Downloads](https://img.shields.io/github/downloads/Xposed-Modules-Repo/com.houvven.impad/total?style=flat-square&logo=github&label=Downloads)](https://github.com/Xposed-Modules-Repo/com.houvven.impad/releases)
[![Stars](https://img.shields.io/github/stars/Houvven/I-Am-Pad?style=flat-square&logo=github&label=Stars)](https://github.com/Houvven/I-Am-Pad/stargazers)

---

## 支持应用  
- 小红书  
- 微信  
- QQ  
- 钉钉  
- 企业微信  
  - 国航之翼
  - 粤政易

---

## 本 fork 的改动

伪装的平板机型由 **Xiaomi Pad 6 Pro（`23046RP50C`）** 改为 **Xiaomi Pad 9 Pro Max（`M367FC`，玄戒 O3 版，2026-09 发布）**。

改动只作用于模块原本就会改写机型的应用：

- QQ：`Build.MANUFACTURER` / `BRAND` 保持 `Xiaomi`，`MODEL` 改为 `M367FC`；
- 小红书：`getDeviceAccurateModel()` 返回 `M367FC`，并继续把设备类型固定为 `pad`。

微信、钉钉、企业微信的适配逻辑不读取该机型常量，因此不受影响。

`M367FC` 来自公开资料（GSMArena、Gadgets360、Kalvo 等均把该型号对应到 Xiaomi Pad 9 Pro Max）。如果目标应用的服务端机型库尚未收录该机型，平板识别、登录资格或风控表现可能与上游默认的 `23046RP50C` 不同。
