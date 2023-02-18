<h4 align="center">此为PushPlus渠道推送的测试版，可通过PushPlus API向微信推送续期结果。</h4>

<h4 align="center">通过Cloudflare Workers自动续期Freenom域名(.cf .ga .gq .ml .tk)。</h4>

<p align="center">
  <a href="https://github.com/PencilNavigator/Freenom-Workers/blob/main/README.md">English README</a>
  •
  <a href="https://github.com/PencilNavigator/Freenom-Workers/issues">Issues</a>
  •
  <a href="https://github.com/PencilNavigator/Freenom-Workers/Wiki">Wiki</a>
  •
  <a href="https://github.com/PencilNavigator/Freenom-Workers/discussions" target="_blank">Discussions</a>
</p>
<p align="center">
 喜欢这个项目？给颗Star吧！
</p>

感谢[xiaoxiyao](https://github.com/xiaoxiyao)！


## 部署

1. 打开你的 [Cloudflare管理面板](https://dash.cloudflare.com)

2. 在账号主页左侧侧边栏选择Workers

3. 在Workers页面，选择创建服务，设置好服务名称，选择HTTP处理程序。

4. 在刚刚创建的Workers界面，选择“快速编辑”。

5. 在编辑界面，粘贴[worker_pushplus.js](https://github.com/PencilNavigator/freenom-workers/blob/wechatpush/worker_pushplus.js)内代码，点击保存。

6. 返回刚刚创建的Workers页面，选择“设置”，再选择“变量”。

7. 在变量页面，添加以下变量和变量值：
	- SECRET_USERNAME变量，填入Freenom用户名
	- SECRET_PASSWORD变量，填入Freenom密码

	（可选）勾选两个变量的“加密”选项（可极大程度降低Freenom用户名和密码泄露的概率）。

8. 返回创建的Workers页面，选择“触发器”。

9. 在触发器界面，选择添加Cron触发器。在“添加Cron触发器”界面，设置触发器，保存。推荐执行时间为一天一次。

10. 在同一界面的路由选项中禁用默认路由（通常为 服务名.子域名.workers.dev）。

11. （可选）启用[pushplus](https://www.pushplus.plus/)推送，续期成功或者失败会自动推送消息到微信，启用方法：
	- 添加PUSHPLUS_TOKEN变量，填入pushplus的token。可选择勾选变量的“加密”选项（可极大程度降低Token泄露的概率）。


## 测试

（快速编辑-预览 访问）在快速编辑界面中的“预览”访问已部署的Workers。顺利的话，你将看到你账户内所有域名的剩余日期。
_请注意，通过预览访问不会触发续期任务，仅用于测试是否可以获取账户内所有域名的剩余日期。_

（触发Cron）进入“快速编辑”，选择“设定时间”，再选择“触发计划的事件”。查看下方Console是否有输出域名剩余日期。（如有可续期的域名，会输出是否续期成功。）

## 效果展示
![图片](https://user-images.githubusercontent.com/85282140/207813815-99af2574-910d-40d1-908c-5f18de1a5648.png)

（2022/12/15测试）

## 已知问题

请访问该[Wiki](https://github.com/PencilNavigator/freenom-workers/wiki/Known-Issues)页面。

## 待实现的功能

请访问该[Wiki](https://github.com/PencilNavigator/freenom-workers/wiki/Planned-Enhancement)页面。

## 类似项目
https://github.com/luolongfei/freenom (PHP)

https://github.com/Oreomeow/freenom-py (Python)


## LICENSE
目前没有决定好用什么LICENSE.

<img title="mona-loading" alt="mona-loading" src="https://github.githubassets.com/images/mona-loading-dark.gif" width="100">
