
设置方法：

单击下面的按钮即可在您的 Vercel 帐户上部署 Apprise。还没注册的可以选择github登陆然后绑定手机即可

[![使用 Vercel 进行部署](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/amclubs/apprise_vercel)


部署后，您将获得一个类似 的链接https://testapprise-amclubs-projects.vercel.app/，附加/notify到该链接后，您将获得 Apprise API 服务器的链接：https://testapprise-amclubs-projects.vercel.app/notify

根据Apprise wiki编写发送通知的 URL ，其中有关于如何设置每个通知渠道的详细文档和说明。例如，对于电报，您的 URL 是tgram://botToken/chatId

填写workerConfig.notification配置：

notification: {
  appriseApiServer: "https://testapprise-amclubs-projects.vercel.app/notify",
  recipientUrl: "tgram://botToken/chatId",
  // [Optional] timezone used in notification messages, default to "Etc/GMT"
  timeZone: "Asia/Shanghai",
  // [Optional] grace period in minutes before sending a notification
  // notification will be sent only if the monitor is down for N continuous checks after the initial failure
  // if not specified, notification will be sent immediately
  gracePeriod: 5,
},
