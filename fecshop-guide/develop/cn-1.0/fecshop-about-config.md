Fecshop ��ʼ����
================

> �����ֶ���װ��Linxu ��Fecshop�Ĵ���󣬾Ϳ��Խ��������ˡ�


1������ fecshop app advanced

```
��common/main-local.php������mysql��mongodb��redis

```


```
<?php
return [
    'components' => [
        'db' => [
            'class' => 'yii\db\Connection',
            'dsn' => 'mysql:host=localhost;dbname=fecshop',  # Fecshop��mysql�����ݿ����֣�����Ҫ��mysql�н���һ�����ݿ�
            'username' => 'root',  # mysql���˻�
            'password' => '123456', # mysql������
            'charset' => 'utf8',
        ],
        'mongodb' => [
            'class' => 'yii\mongodb\Connection',
            # ���˻������ã�username���û�����password�����룬fecshop�����ݿ�
            //'dsn' => 'mongodb://username:password@localhost:27017/fecshop',
            # ���˻������ã�fecshop�����ݿ�
            'dsn' => 'mongodb://127.0.0.1:27017/fecshop',
            # ���Ƽ� �������mongodb�Ǹ��Ƽ�����վ��������ʹ������ĸ��Ƽ������÷�ʽ��
            //'dsn' => 'mongodb://10.10.10.252:10001/fecshop,mongodb://10.10.10.252:10002/fecshop,mongodb://10.10.10.252:10004/fecshop?replicaSet=terry&readPreference=primaryPreferred',
        ],


```

mongodbĬ����û������ģ������Խ�mongodb�Ķ˿���iptables������κͶ˿ڷ�ռ���
��֤��ȫ����Ȼ����Ҳ��������mongodb���û��������롣


4�����û���

4.1 ���host

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


4.2������nginx

```
appfront.fecshoptest.com appfront.fecshoptest.es ָ�� fecshop/appfront/web 
 
appadmin.fecshoptest.com ָ��fecshop/appadmin/web

apphtml5.fecshoptest.com ָ��fecshop/apphtml5/web

appapi.fecshoptest.com 	 ָ��fecshop/appapi/web

appserver.fecshoptest.com ָ��fecshop/appserver/web

img.fecshoptest.com 	ָ��fecshop/appimage/common

img2.fecshoptest.com 	ָ��fecshop/appimage/appadmin

img3.fecshoptest.com 	ָ��fecshop/appimage/appfront

img4.fecshoptest.com 	ָ��fecshop/appimage/apphtml5

img5.fecshoptest.com 	ָ��fecshop/appimage/appserver

```

5���������ԣ�������ʹ��Ĭ�ϣ���


�������ļ�����`@common\config\fecshop_local_services\FecshopLang.php`



6�����û��ң�������ʹ��Ĭ�ϣ���


���ļ���`@common\config\fecshop_local_services\Page.php`



7������store��������ͼƬ�������������Ժ��������ʾ������һ�£�


store�������ļ���`@app\config\fecshop_local_services\Store.php`

Ʃ���ҵĴ���(�����Ժ��ҵı���һ�£���Ӧ�����Ѿ����������host)��

```
<?php
   return [
   'store' => [
		'class' => 'fecshop\services\Store',
		'stores' => [
			# ���ݵ�key��������
			'appfront.fecshoptest.com' => [
				'language' 		=> 'en_US',   # ���Ա�����������岽��fecshoplang�ж��壬�����޷��õ��������ԡ�
				'languageName' 	=> 'English', # �����store��ʱ�򣬱���鿴 ��ӵ������� fecshoplang���Ƿ��塣
				# ���屾��ģ��·����������дfecshop��ģ�壬���߿����µ�ģ���ļ���
				//'localThemeDir'	=> '@appfront/theme/terry/theme01',
				# ���������ģ��·����������дfecshop��ģ�壬���߿����µ�ģ���ļ���
				'thirdThemeDir'	=> [],
				# ��ǰ���Ե�Ĭ�ϻ��ң����ұ���������������������д���
				'currency' 		=> 'USD',
				'mobile'		=> [ # ���豸����ʲô������ʱ�򣬽�����ת��
					'enable'		=> true,
					'condition'		=> ['phone','tablet'], # phone �����ֻ���tablet����ƽ��
					'redirectUrl' 	=> 'apphtml5.fecshoptest.com',	# ������ƶ��豸���ʽ���������ת
				],
				# �������˺ŵ�¼����
				'thirdLogin' => [
					'facebook' =>[                       #fb api���� ��fb����һ��app����pc���ֻ��������� 
						'facebook_app_id'     => '184963',
						'facebook_app_secret' => '2e097dd7139',
					],
					"google" => [                       #�ȸ�api visit https://code.google.com/apis/console to generate your google api
						'CLIENT_ID'  	 => '38037grhccontent.com',
						'CLIENT_SECRET'  => 'ei8RaoCHYm0rrwO',
					],
				]

				//'image'	=> [
				//	'domain' => 'img.appfront.fancyecommerce.com',
				//	'baseDir'=> '@appimage/appfront',
				//]
			],
			'appfront.fecshoptest.com/fr' => [
				'language' 		=> 'fr_FR',
				'languageName' 	=> 'Fran?ais',
				'localThemeDir'	=> '@appfront/theme/terry/theme01',
				'thirdThemeDir'	=> [],
				'currency' 		=> 'RMB',
				'mobile'		=> [
					'enable'			=> true,
					'condition'			=> ['phone'], # phone �����ֻ���tablet����ƽ�塣
					'redirectDomain' 	=> 'apphtml5.fecshoptest.com/fr', # ��ת���url��
				],
			],
			'appfront.fecshoptest.es' => [
				'language' 		=> 'es_ES',
				'languageName' 	=> 'Espa?ol',
				'localThemeDir'	=> '@appfront/theme/terry/theme01',
				'thirdThemeDir'	=> [],
				'currency' 		=> 'USD',
				'mobile'		=> [
					'enable'		=> true,
					'condition'		=> ['tablet'],
					'redirectDomain' 	=> 'fecshop.apphtml5.es.fancyecommerce.com',	
				],
			],
			'appfront.fecshoptest.com/cn' => [
				'language' 		=> 'zh_CN',
				'languageName' 	=> '����',
				'localThemeDir'	=> '@appfront/theme/terry/theme01',
				'thirdThemeDir'	=> [],
				'currency' 		=> 'RMB',
				'mobile'		=> [
					'enable'		=> false,
					'condition'		=> ['phone','tablet'],
					'redirectDomain' 	=> 'fecshop.apphtml5.fancyecommerce.com/cn',	
				],
			],
		],
		
	],
			
];
```

��������ľ��庬�壬��ע�����Ѿ�˵�������ڵ�����facebook��google��¼����λ�ȡ
CLIENT_ID��CLIENT_SECRET���Բο��ҵĲ��ģ�
[ facebook login ���� app_id �� app_secret](http://blog.csdn.net/terry_water/article/details/55095721) ��
[ google login api ���� CLIENT_SECRET �� CLIENT_SECRET](http://blog.csdn.net/terry_water/article/details/55095209)

7��ͼƬ���������ļ���`@common\config\fecshop_local_services\Image.php`
,Ʃ���ҵĴ���(�����Ժ��ҵı���һ�£���Ӧ�����Ѿ����������host)��

```
<?php
/**
 * FecShop file.
 * @link http://www.fecshop.com/
 * @copyright Copyright (c) 2016 FecShop Software LLC
 * @license http://www.fecshop.com/license/
 */
return [
	'image' => [
		'appbase'	=> [
			'appfront' => [
				'basedir' => '@appimage/appfront',
				'basedomain' => 'http://img3.fecshoptest.com',
			],
			'apphtml5' => [
				'basedir' => '@appimage/apphtml5',
				'basedomain' => 'http://img2.fecshoptest.com',
			],
			'appadmin' => [
				'basedir' => '@appimage/appadmin',
				'basedomain' => 'http://img2.fecshoptest.com',
			],
			'common' => [
				'basedir' => '@appimage/common',
				'basedomain' => 'http://img.fecshoptest.com',
			],
		],
	],
];
```

�����ܻ��ʣ�ΪʲôҪ��ͼƬ����������ͼƬ����վʹ��һ���������Ϳ�����
ԭ�����������ҳ���ʱ��ÿһ���������ص����Ӹ����������Ƶģ���
ͼƬʹ�ò�ͬ��������������ͼƬ�������أ��ӿ�ҳ���ˢ�¡�



8�������Ƿ�ǿ�Ƹ���assets��webĿ¼������ǿ�����������������������ã���ѡ���ã������Ȳ����������

`@app/config/main.php`������Կ������������


�����yii2��֪ʶ����

```
'assetManager' => [
	'forceCopy' => true,
],
```

��������ϣ� ��forceCopy���ó�false `['forceCopy' => false]`

ԭ�򣺱��ؿ��������޸�css����ˣ�ÿ�ξ���Ҫyii��asset��css������web·�����棨����ķ���������yii2�ڳ�ʼ����ʱ��ͻ�ǿ�ư���Ҫ��css���Ƶ�
web/assets·�����棬Ʃ��yii2��װ��bootstrapǰ�˿�ܣ���
��������ϻ����������ǳ��ķ���Դ����ˣ����Ϲرռ��ɣ�������������µ�css�ļ���
��ô����Ҫ�ֶ����@app/web/assets������ļ��У�������Ϸ��������󣬿���Ҳ����ν���Ǻǡ�����

9���������ݿ��(migrate)����fecshop��Ŀ¼ִ�������������

9.1��Yii2 migratge��ʽ�����

mysql(����mysql�ı����ݣ�����):

```
./yii migrate --interactive=0 --migrationPath=@fecshop/migrations/mysqldb
```

mongodb(����mongodb�ı����ݣ�����):

```
./yii mongodb-migrate  --interactive=0 --migrationPath=@fecshop/migrations/mongodb
```

9.2���������ݰ�װ��

mongodb��ʾ�����ݴ��·��Ϊ��

`./vendor/fancyecommerce/fecshop/migrations/mongodb-example-data/example_data.js`

����ͨ��mongodb�ĺ�̨������ͨ��php��rockmongo��װ��Щmongodb�е�ʾ�����ݡ�

mongodb��ʾ�����ݲ�ƷͼƬ�Ƚϴ�û�зŵ��汾�����棬����Ե��ٶ���������`appimage.zip`�����ص�ַΪ��`https://pan.baidu.com/s/1kVwRD2Z`
�������ͼƬ�󣬽�appimage���ǵ���Ŀ¼���ɣ����Ǻ�������ֲ�ƷͼƬû�г�������ô����Ҫ��� `appimage/common/media/catalog/product/cache/*`���������ļ����ļ��У�
��������ͼƬ���棬����ˢ��ҳ�漴�ɡ�

10������nginx  mysql  mongodb  php����Ϳ��Է��ʱ������õ�fecshop�ˡ�