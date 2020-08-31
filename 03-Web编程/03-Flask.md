## 一 Flask 简介

Flask 诞生于 2010 年，是利用 Python 语言基于 Werkzeug 工具箱编写的轻量级 Web 开发框架。

Flask 本身相当于一个内核，其他几乎所有的功能都要用到扩展（邮件扩展 Flask-Mail，用户认证 Flask-Login，数据库 Flask-SQLAlchemy），都需要用第三方的扩展来实现。比如可以用 Flask 扩展加入 ORM、窗体验证工具，文件上传、身份验证等。Flask 没有默认使用的数据库，你可以选择 MySQL，也可以用 NoSQL。

其 WSGI 工具箱采用 Werkzeug（路由模块），模板引擎则使用 Jinja2。这两个也是 Flask 框架的核心。

文档地址：http://docs.jinkan.org/docs/flask/
