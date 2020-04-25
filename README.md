# 使用群晖自带的Web功能 五分钟安装自己的导航页
> 你的浏览器首页是什么？一些常用的有广告的导航网站吗？太LOW了，试试`Opage`吧！
> `Opage` 是一个充满极客范儿的客制化上网首页，基于 Material Design & Vue.js。
> 集成搜索，网站，天气，TODO，Faster & Pure

## 功能   

- 搜索：百度 + Google + Bing
- 网站：可自定义网站列表
- 天气：南京 + 4 天预测
- TODO：简单的 Todo 列表
## 关于

**为何叫做 O？**

- **O**在 leet 中即为 0，从**零**开始
- **O**rigin
- All in **O**ne

## 编译使用

首先感谢`Opage`的原作者带来这么好的项目， 完美的符合我的需求， 你能自定义常用的网站导航、添加待办事项、查看城市天气、快速搜索，并且支持`PC`端和手机端 ，我在源代码的基础上更新了下，达到初始时自带我的一些网址导航， 并且修复了天气接口。但是城市选择列表的`json`文件原作者的`url`已无法访问，所以我修改成了固定值**南京**，如果哪位有此`json`文件，可以分享给我，感谢！

你可以编译我的文件直接使用，或者自己修改代码后再编译使用，只需编译一次，即可放在任意的`Web`服务器上运行。

下面是编译步骤，在Centos系统上运行的。

```bash
# 安装前端环境和git环境
yum -y install wget git
wget https://nodejs.org/dist/v12.16.1/node-v12.16.1-linux-x64.tar.xz
# 解压下载的node包，分别执行以下指令
xz -d node-v12.16.1-linux-x64.tar.xz
tar -xf node-v12.16.1-linux-x64.tar
# 配置node和npm。注意node所在目录，我的node目录是/root/node-v12.16.1-linux-x64
ln -s /root/node-v12.16.1-linux-x64/bin/node /usr/bin/node
ln -s /root/node-v12.16.1-linux-x64/bin/npm /usr/bin/npm
# 查看node和npm，出现版本号说明安装成功
node -v
npm -v
# 创建你自己的目录，在目录下拉取此项目
mkdir homepage
cd /root/homepage
git clone https://github.com/wanglu58/opage.git
# 进入此项目目录
cd opage/
# 安装依赖
npm install
# 开始编译
npm run build
# 你会发现项目中多了dist目录，进入此目录可看到index.html文件和static文件夹
cd ./dist/
# 拷贝这2个文件到任意的Web环境当中，就能看到你的专属导航主页啦！
```

我把这些文件放到了我的群晖当中
![图1.png][1]
直接浏览器输入群晖IP地址，就进入到了导航页！ 安装导航页完成！
![图2.png][2]


[1]: https://www.xkblogs.com/usr/uploads/2020/04/2693023232.png
[2]: https://www.xkblogs.com/usr/uploads/2020/04/1970665077.png
