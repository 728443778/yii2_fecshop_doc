Fecshop 安装
=======================


github: https://github.com/fancyecommerce/yii2_fecshop_app_advanced

[![Latest Stable Version](https://poser.pugx.org/fancyecommerce/fecshop-app-advanced/v/stable)](https://packagist.org/packages/fancyecommerce/fecshop-app-advanced) [![Total Downloads](https://poser.pugx.org/fancyecommerce/fecshop-app-advanced/downloads)](https://packagist.org/packages/fancyecommerce/fecshop-app-advanced) [![Latest Unstable Version](https://poser.pugx.org/fancyecommerce/fecshop-app-advanced/v/unstable)](https://packagist.org/packages/fancyecommerce/fecshop-app-advanced)


> 项目已经开始, 正在开发中，框架整理阶段。
> Terry

#### 1.安装 fecshop app advanced

安装这个扩展的首选方式是通过 [composer](http://getcomposer.org/download/).

安装composer

```
curl -sS https://getcomposer.org/installer | php  
mv composer.phar /usr/local/bin/composer 
composer self-update
```

安装fecshop app advanced

```
composer global require "fxp/composer-asset-plugin:~1.1.1"
composer create-project --prefer-dist  fancyecommerce/fecshop-app-advanced
cd fecshop-app-advanced
./init

```


执行完上面，就安装完成了。

#### 2.配置 fecshop app advanced

```
在common/main-local.php中配置mysql和mongodb
在appfront/config/main-local.php中配置redis
在appadmin/config/main-local.php中配置redis
在apphtml5/config/main-local.php中配置redis
如果您还要使用appserver ，appapi，则在相应的config文件夹下的main-local.php中配置redis
```

#### 3.配置nginx

```
nginx root 分别指向 appfront/web ,appadmin/web,apphtml5/web
```

#### 4.通过migrate安装数据库mysql和mongodb 


#### 5.访问配置的域名。如果出现asset文件夹权限问题，设置一下文件夹777即可。 
