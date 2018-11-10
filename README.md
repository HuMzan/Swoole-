我是用宝塔面板和自己编译swoole，原始环境PHP7.1 + swoole4.2.7+queryListV4+mysql5.8+redis
有两个进程池组
index.PHP主要负责爬取所有小说信息和把目录章节丢到redis队列，并做好分表，保存封面图片，cli环境php index.php start 开启运行

task.php负责把章节队列取出，请求，把内容放到json文件入库，cli环境php task.php start 开启运行

进程不要开太多，会给目标网站带来负担，项目主要是学习为主。

在要关闭程序是最好用 kill -15 主进程ID 来让在工作的进程，运行完再退出

（PS:）原先还想用sphinx搜索引擎，解决搜索过于慢的问题，但我这个是小说爬虫，不合适；也不怎么会，所以主要就是项目的结构和需要的技术为主要目标
