# PWA (Progressive Web Apps)

webapp 用户体验差(不能离线访问)，用户粘型低（无法保存入口）, pwa 就是为了解决这一系列问题，让 webapp 具有快速 可靠 安全等特点

PWA 一系列技术

- Web App Manifes
- Service Worker
- Push Api & Notification Api
- App Shell & App Skeleton
- ...

## Web App Manifes

将网站添加到桌面 更类似 native 的体验

```html
<link rel="manifest" href="/manifest.json" />
<link rel="apple-touch-icon" href="/icon.png" />
<!-- 添加到主屏后的标题 和 short_name一致 -->
<meta name="apple-mobile-web-app-title" content="标题" />
<!-- 隐藏safari地址栏 standalone模式下默认隐藏 -->
<meta name="apple-mobile-web-app-capable" content="yes" />
<!-- 设置状态栏颜色 -->
<meta
  name="apple-mobile-web-app-status-bar-style"
  content="black-translucent"
/>
```

```js

{
    "name": "PWA效果展示",
    "short_name": "PWA",
    "display": "standalone",
    "start_url": "/",
    "icons": [{
        "src": "/icon.png",
        "sizes": "144x144",
        "type": "image/png"
    }],
    "background_color": "#aaa",
    "theme_color": "#aaa"
}

```

## Service Worker
Service Worker 特点
- 不能访问/操作Dom
- 会自动休眠，不会随浏览器关闭所失效（必须手动卸载）
- 会离线缓存 内容开发者可控
- 必须在https或者localhost下使用
- 所有的api都基于promise
