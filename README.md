# GitHub 代下载服务
[![G.widora.cn 互粉群](https://pub.idqqimg.com/wpa/images/group.png "G.widora.cn 互粉群")](https://shang.qq.com/wpa/qunwpa?idkey=f65cb90612db81ef9bee771440adb40c004933a18b7c0466a279486936aedc79)
![question_goes_to_qq-9496898-red](https://img.shields.io/badge/question_goes_to_qq-9496898-red)
[![based_on-workerMan-blue](https://img.shields.io/badge/based_on-workerMan-blue)](https://www.workerman.net/)
[![demo-g.widora.cn-yellowgreen](https://img.shields.io/badge/demo-g.widora.cn-yellowgreen)](https://g.widora.cn)

**注：本程序为简单实现，因纯属业余时间编写，开发比较仓促，欢迎完善。请遵循法律法规，不要用来做违法的事情。**

本程序基于 [workerMan](https://www.workerman.net/) 编写

如有问题，可联系本人qq：9496898

如果您也搭建了此服务，我们可以互粉一下友情链接，组合成一个阵营。如感兴趣，请加入互粉群（链接请看[开头的badge](#user-content-github-代下载服务)）。

# 自部署教程
1. staticweb目录下，您需要为站点进行nginx配置
2. GatewayWorker下start_gateway中配置wss所需要的证书
```php
$context = array(
     'ssl' => array( // 请使用绝对路径
         'local_cert' =>'/xxxxx.pem', // 也可以是crt文件
         'local_pk' => 'xxxxxx.key',
         'verify_peer' => false,
         // 'allow_self_signed' => true, // 如果是自签名证书需要开启此选项
     )
);
```
3. 启动GatewayWorker
```bash
cd path/to/GatewayWorker 
php start.php start
```
4. start_sync中可根据您的服务器配置来设置进程数
     * task进程数可以根据需要多开一些，默认为10
```php
$task_worker->count = 10;
```

另外，部署到香港、韩国、日本等非大陆的服务器的事情就不用我说了吧。推荐使用：[Vultr](https://www.vultr.com/?ref=8428612)日本服务器

# TODO
因本人平常工作繁忙，欢迎爱好者帮忙搭建Docker容器，请联系本人放出仓库地址
