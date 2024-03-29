## 配置邮件 - 163/126邮箱配置示例 

如果没有企业邮箱，个人免费邮箱推荐使用163或126邮箱，邮件发送比较稳定，垃圾邮件也较QQ邮箱少。
1. 开启SMTP服务
登录163邮箱，找到邮箱【设置】-【POP3/SMTP/IMAP】，开启POP3/SMTP服务，网易邮箱要求开启SMTP服务前邮箱要绑定手机，根据提示操作即可，开启时要设置一个授权码，此授权码为SMTP服务器密码，需要填写到网校后台，请妥善保存。  
![](/media/edusoho-email.PNG)  
最终的设置效果，邮箱必须要开启SMTP服务。
1. 配置网校后台
路径：【管理后台】-【系统】-【站点设置】-【邮件服务器配置】，配置参数为：
  - 邮件发送：开启
  - SMTP服务器地址：ssl://smtp.163.com （如果是126邮箱，即填写ssl://smtp.126.com）；
  - SMTP端口号：465/994;
  - SMTP用户名：banchefu@163.com（邮箱地址）；
  - SMTP密码：填写在开启SMTP服务时设置的授权码；
  - 发信人地址：banchefu@163.com（邮箱地址）；
  - 发信人名称：建议填写网站名称， 比如气球鱼学院，那么学员收到的邮件就会显示来自气球鱼学院。  
3. 验证配置是否正确
路径：【管理后台】-【用户】-【用户管理】-【操作】-【发送邮件】；  
找到自己的账号发送邮件测试，如果系统提示发送成功，邮箱配置就是正确的。  
若提示发送失败，请根据以上格式检查，SMTP密码是否填写正确，以及配置的信息中，是不是包含空格。

## 配置文件上传允许大小
两个文件`/etc/php/7.0/fpm/php.ini`和`/etc/php/7.0/apache2/php.ini`中都要配置。
```
post_max_size = 1024M
memory_limit = 1024M
upload_max_filesize = 1024M
```
修改配置后，重启PHP和Apache
```
sudo service php7.0-fpm restart
sudo service apache2 restart
```

**课程文件上传的目录**
```
/var/www/html/edusoho/app/data/udisk/course-activity/39/
```
*39是课程的ID*

## 常见问题
[http://www.qiqiuyu.com/faq/search?categoryId=72](http://www.qiqiuyu.com/faq/search?categoryId=72)

