Nginx Docker镜像
  这个Dockerfile用于构建一个基于Nginx的镜像，适用于在Docker容器中运行Web应用。

环境变量
  LANG=zh_CN.UTF-8: 设置默认语言为中文
  LANGUAGE=zh_CN.UTF-8: 设置默认语言环境为中文
   LC_ALL=zh_CN.UTF-8: 设置默认区域设置为中文

时区设置和语言包安装
  修改apt源为清华大学镜像源，提高软件包下载速度

更新源列表
  安装tzdata和locales软件包，用于设置和管理时区和语言环境
  将时区设置为"Asia/Shanghai"
  创建指向/usr/share/zoneinfo/Asia/Shanghai的符号链接，使系统能正确读取时区信息
  使用dpkg-reconfigure locales设置语言环境，以支持中文
  使用localedef命令生成中文的UTF-8编码，并设置为默认语言
  安装一些常用的中文字体
清理缓存和不必要文件
  清理不必要的缓存文件和临时文件。
