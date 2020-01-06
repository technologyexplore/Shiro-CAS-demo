# Shiro-CAS-demo
Apereo CAS单点登录(SSO)

1.什么是单点登录



2. CAS （中央认证服务）

CAS是Central Authentication Service的缩写，中央认证服务，一种独立开放指令协议。CAS 是 Yale 大学发起的一个开源项目，

旨在为 Web 应用系统提供一种可靠的单点登录方法，CAS 在 2004 年 12 月正式成为 JA-SIG 的一个项目。 https://www.apereo.org



3.Ticket和TGC是用来干嘛的？

  ① Ticket:每个web服务器每一次登录完成后的票据，cas颁发给子系统用于cas client认证

  ② TGC:第一个web服务器第一次登录（用户名密码方式）完成后的证明,cas颁发给浏览器存储在cookie。

       在访问其它子系统的时候就用TGC去兑换Ticket而不是用户名密码兑换。

4.单点登出

① CAS服务清除Cookie里的TGC

② CAS服务通过Http/Https的方式给所有通过该TGC登录过的web服务器发送登出请求，清除每个web服务器的httpSession