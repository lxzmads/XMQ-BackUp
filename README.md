# XMQ-BackUp
![](https://img.shields.io/packagist/l/doctrine/orm.svg) ![](https://img.shields.io/badge/python-3.5-ff69b4.svg)

小密圈备份，圈子/话题/图片/文件。

> 2017年7月25日，小密圈官方微博以及微信公众号发出公告，由于“技术升级”，改名为“知识星球 ”。我在原作者代码上更改了域名以及api版本信息。

api version v1.10

## Usage
1. 安装 `chromedriver`
> 仅用于自动登录，如果你愿意自己抓包，则不需要安装
  * `brew install chromedriver`
  * 或前往[官网](http://www.seleniumhq.org/download/)/[镜像](http://npm.taobao.org/mirrors/chromedriver/)下载
    * 将包含可执行文件的目录添加至环境变量
    * 或设置`settings.py/CHROME_DRIVER_PATH`为完整执行路径
2. 安装 `XMQ-BackUp`
```bash
git clone git@github.com:Lodour/XMQ-BackUp.git
cd XMQ-BackUp
mv xmq/settings.exammple.py xmq/settings.py
virtualenv env -p python3.5
source ./env/bin/activate
pip install -r requirements.txt
```

3. 运行
  * `scrapy crawl backup`
  * 手动指定`token`及`User-Agent`
    * 浏览器端登录后抓包获取`request headers`中的`authorization`和`User-Agent`字段
    * 在`xmq/settings.py`末尾将其设置为`XMQ_ACCESS_TOKEN`和`XMQ_USER_AGENT`
  
## Note
  * `phantomjs`渲染所得到的`access_token`不合法，所以换成了`chromedriver`
  * `virtualenv`下使用`scrapy`有问题的请参照[这里](https://segmentfault.com/q/1010000010805727/a-1020000010807816)
  * 如果你的浏览器版本有更新，是需要重新设置UA的。
  * 欢迎交流
