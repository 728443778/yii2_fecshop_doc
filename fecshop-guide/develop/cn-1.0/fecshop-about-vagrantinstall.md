Fecshop vagrant��װ
====================

> Vagrant��һ������Ruby�Ĺ��ߣ����ڴ����Ͳ������⻯����������
>�� ʹ��Oracle�Ŀ�ԴVirtualBox���⻯ϵͳ��ʹ�� Chef�����Զ������⻷����

1. vagrant �̳�

�����û��ʹ��vagrant�����û�й�ϵ����������һ��vagrantʹ�õĽ̳̣���ַ���£�
[vagrant ���ز���linux����](http://www.fancyecommerce.com/2016/09/22/vagrant-%E4%B8%8B%E8%BD%BD%E9%83%A8%E7%BD%B2linux%E7%8E%AF%E5%A2%83/)


2. ���Fecshop ������box

���û����Ƚϸ��ӣ��ұ����Ѿ����ú���fecshop�Ļ������������һ��box��
��ַ�ڰٶ����̣����ص�ַΪ��https://pan.baidu.com/s/1kVwRD2Z�� 
�������ļ��У����� package.box����������Ľ̳̼��ؽ���box���ɡ�

��װ��ɺ󣬸�����ڵ������Ͷ�Ӧ���ļ�·��Ϊ��

```
pc�˵�ַ��appfront.fecshoptest.com appfront.fecshoptest.es ָ�� /www/web/develop/fecshop/appfront/web 

��̨�˵�ַ��appadmin.fecshoptest.com ָ��/www/web/develop/fecshop/appadmin/web

html5�˵�ַ��δ��������apphtml5.fecshoptest.com ָ��/www/web/develop/fecshop/apphtml5/web

api�˵�ַ��δ��������appapi.fecshoptest.com     ָ��/www/web/develop/fecshop/appapi/web

�ֻ�app�˵�ַ��δ��������appserver.fecshoptest.com ָ��/www/web/develop/fecshop/appserver/web

commonͼƬ�˵�ַ��img.fecshoptest.com     ָ��/www/web/develop/fecshop/appimage/common

appadminͼƬ�˵�ַ��img2.fecshoptest.com  ָ��/www/web/develop/fecshop/appimage/appadmin

appfrontͼƬ�˵�ַ��img3.fecshoptest.com  ָ��/www/web/develop/fecshop/appimage/appfront

apphtml5ͼƬ�˵�ַ��img4.fecshoptest.com  ָ��/www/web/develop/fecshop/appimage/apphtml5

appserverͼƬ�˵�ַ��img5.fecshoptest.com     ָ��/www/web/develop/fecshop/appimage/appserver

rock mongo���ʵ�ַ��rock.fecshoptest.com    �˺ţ�admin  ���룺123456

phpmyadmin���ʵ�ַ: my.fecshoptest.com      �˺ţ�root   ���룺123456

��̨�˵�ַ��appadmin.fecshoptest.com���ʺ󣬺�̨���û���������Ϊadmin  123456
```

�����������Ҫ����windows���hosts

��C:\Windows\System32\drivers\etc\hosts��������´��루���������IP����
127.0.0.1 �滻������IP���ɡ�����

```
127.0.0.1       rock.fecshoptest.com
127.0.0.1       my.fecshoptest.com
127.0.0.1       appadmin.fecshoptest.com
127.0.0.1       appfront.fecshoptest.com
127.0.0.1       appfront.fecshoptest.es
127.0.0.1       apphtml5.fecshoptest.com
127.0.0.1       appapi.fecshoptest.com
127.0.0.1       appserver.fecshoptest.com
127.0.0.1       img.fecshoptest.com		#appimage/common
127.0.0.1       img2.fecshoptest.com	#appimage/appadmin
127.0.0.1       img3.fecshoptest.com	#appimage/appfront
127.0.0.1       img4.fecshoptest.com	#appimage/apphtml5
127.0.0.1       img5.fecshoptest.com	#appimage/appserver
```


�����Ϳ��Է����ˣ�Ʃ�磺appfront.fecshoptest.com ����ǰ��pc web��
appadmin.fecshoptest.com ���ʺ�̨web






























