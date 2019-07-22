### php-yaf拓展
```
# 下载yaf
wget -c http://pecl.php.net/get/yaf-3.0.8.tgz
# 解压缩
cd yaf-3.0.8/ && phpize
# 编译安装
./configure --with-php-config=php-config
make && make install
# 启用拓展
echo 'extension=yaf.so
yaf.use_namespace=1' > /etc/php/7.3/mods-available/yaf.ini
ln -s /etc/php/7.3/mods-available/yaf.ini /etc/php/7.3/fpm/conf.d/20-yaf.ini
# 重启服务
service php7.3-fpm restart
```

### 目录写权限
```
chown www-data:www-data ./conf/application.ini
chown -R www-data:www-data ./install/
chown -R www-data:www-data ./temp/
chown -R www-data:www-data ./log
```

### 版本信息泄露

```
application\views\showmsg\index.html
application\views\error\error.html
application\modules\Member\views\common\header.html
application\modules\Member\views\common\footer.html
application\modules\Admin\views\common\header.html
application\modules\Admin\views\common\footer.html
```
