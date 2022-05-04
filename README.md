# WeiboKeywordsSpider-
基于selenium + java的可以自定义关键词和抓取时间的微博爬取器

## 1 - 环境
本项目在IDEA运行，基于JDK1.8，需要自行导入selenium和json的jar包。
浏览器驱动为Chrome，根据自己的driver位置修改main函数中的driver位置。


## 2 - 效果
自定义抓取开始与结束时间，设置关键词列表，在微博广场上抓取{关键词1|关键词2|...|关键词n}的博文信息。信息包括微博的文字内容、转发数、点赞数、评论数、发微博用户的ID、地区、性别 、follower数量以及发微博的时间。
抓取的结果按照每小时抓取保存在一个json文件中。


## 3 - 使用方法
- 由于微博限制非登录用户只能获得部分广场信息，如果本地没有Cookies信息，需要首先设置isGetCookie = true，并手动登陆一次；一旦获取过一次Cookies，之后再次运行可以设置isGetCookie = false，无需手动登录。
- 设置抓取的开始时间与结束时间以及关键词，开run！
```
    String beginDay = "2022-04-12";
    String endDay = "2022-04-20";
    Set<String> keywords = new HashSet<String>() {{
        add("女拳");
        add("女权");
        add("性别歧视");
    }};
```

## 4 - Bugs
- 目前无法改变高级搜索中年份的值，在抓取2022年以前的博文时可能会出错。（待修复）
- 可能无法在高级搜索中获得当月的数据。（待修复）
- 在抓取过程中页面会持续弹出，因此如果想多开的话很困扰。（待修复）
