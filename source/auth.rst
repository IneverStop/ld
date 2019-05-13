Auth模块
========

1. 端口号
-----------
 9999

2. 接口
--------

2.1 获取验证码
^^^^^^^^^^^^^^^^

2.2 访问路径
^^^^^^^^^^^^^
  GET /code

2.3 逻辑
^^^^^^^^^
    根据前台生成的randomStr，后台生成一个验证码图片字节流，直接返回给前台。

2.4 Request
^^^^^^^^^^^^^
+---------------+---------------+-------------------------------------+
|   Field Name  |      Type     |    Description                      |
+===============+===============+=====================================+
|    randomStr  |      Number   |  前台生成的随机字符串，前台要记录这 |
|               |               | 个，之后需要根据这个验证 验证码是否 |
|               |               | 正确                                |
+---------------+---------------+-------------------------------------+

2.5 Sample Request
^^^^^^^^^^^^^^^^^^^





	(1) Baidu_

	(2) http://www.baidu.com
	
	(3) inneru_
	
	(4) page go_

.. _Baidu: http://www.baidu.com/
.. _go: h2.html

3. line
shutupdalgjadlsgjadsl;gjadslgjalsdgjasdlgjasdlkfgjadls;kfjasd;lfksad;

.. _inneru: