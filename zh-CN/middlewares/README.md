---
root: true
name: 中间件模块
sort: 0
---

# 中间件模块

中间件模块允许您轻易地对模块的进行接入与解除到您的 Macaron 应用中。

现在已经有许多 [中间件模块](https://github.com/macaron-contrib) 来简化您的工作：

- [binding](https://github.com/macaron-contrib/binding) - 请求数据绑定和校验
- [i18n](https://github.com/macaron-contrib/i18n) - 应用的国际化与本地化
- [cache](https://github.com/macaron-contrib/cache) - Cache 管理器
- [session](https://github.com/macaron-contrib/session) - Session 管理器
- [csrf](https://github.com/macaron-contrib/csrf) - 生成和管理 CSRF 令牌
- [captcha](https://github.com/macaron-contrib/captcha) - 验证码服务
- [pongo2](https://github.com/macaron-contrib/pongo2) - Pongo2 模板引擎支持
- [toolbox](https://github.com/macaron-contrib/toolbox) - 健康检查、性能调试和路由统计等服务
- [switcher](https://github.com/macaron-contrib/switcher) - 多站点支持
- [renders](https://github.com/macaron-contrib/renders) - 类 Beego 模板引擎（Macaron 已有内置模板引擎，此为可选）

### 注册中间件的最佳顺序

有些中间件会依赖其它中间件，以下为最佳的注册顺序列表：

1. `macaron.Logger()`
2. `macaron.Recovery()`
3. `macaron.Gziper()`
4. `macaron.Static()`
5. `macaron.Renderer()`/`pongo2.Pongoer()`
6. `i18n.I18n()`
7. `cache.Cacher()`
8. `captcha.Captchaer()`
9. `session.Sessioner()`
10. `csrf.Csrfer()`
11. `toolbox.Toolboxer()`