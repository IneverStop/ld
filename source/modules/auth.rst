Auth模块
========

端口号
-----------
 gateway入口端口号9999
 原端口8400

接口
--------

1. 获取图片验证码
^^^^^^^^^^^^^^^^

1.1 访问路径
>>>>>>>>>>>>>>>
::

  GET /code/image

1.2 逻辑
>>>>>>>>>>>>>>>
    根据前台生成的randomStr，后台生成一个验证码图片字节流，直接返回给前台。

1.3 Request
>>>>>>>>>>>>>>>
=============== =============== =============================================
 Field Name          Type          Description
=============== =============== =============================================
 randomStr         Number        前台生成的随机字符串，前台要记录这个，之后
                                  需要根据这个验证 验证码是否正确
=============== =============== =============================================

1.4 Sample Request
>>>>>>>>>>>>>>>>>>>>>>>
::

 /code?randomStr=16751551425211184

1.5 Response
>>>>>>>>>>>>>>>
 | 直接返回验证码的图片对应的字节流

1.6 Sample Response
>>>>>>>>>>>>>>>>>>>>>>
 | 空

---------------------------------------------

2. 获取手机验证码
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

2.1 访问路径
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
::

 GET /code/phone/register 获取注册验证码
 GET /code/phone/login   获取登录验证码

2.2 逻辑
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>

根据前台生成的randomStr，后台生成一个6位验证码，发给指定的手机号码，保存在后台中，并返回给前台发送成功的时间戳。

2.3 Request
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
=============== =============== =============================================
  Field Name         Type                        Description
=============== =============== =============================================
     phone          String               指定的手机号
--------------- --------------- ---------------------------------------------
   randomStr        String      前台生成的随机字符串，前台要记录这个，之后
                                  需要根据这个验证 验证码是否正确
=============== =============== =============================================

2.4 Sample Request
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
::

 /code/phone/register?randomStr=4dydd&&phone=18136085708

2.5 Response
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
=============== =============== =============================================
  Field Name         Type                        Description
=============== =============== =============================================
    status          String                           状态码
--------------- --------------- ---------------------------------------------
    message         String                          返回消息
--------------- --------------- ---------------------------------------------
     data           Number          验证码发送成功时的时间戳
=============== =============== =============================================

2.6 Sample Response
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
::

 {
    "status": "GATEWAY-NORMAL-1001",
    "message": "验证码已发送",
     "data": 1557815071578
 }

---------------------------------------------



3. 登录
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

3.1 访问路径
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
::

 GET /auth/login

3.2 逻辑
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
提供了一个统一的接口，满足如下需求。
 1. 输入账户后首先判断账户是否存在
 2. 然后输入密码，判断密码是否正确
 3. 密码若正确，判断登录次数是否超过3次
 4. 超过3次则需要验证码
验证账号是否存在时，只传入token字段。
不带验证码登录时，需要传入除code之外的字段。
带验证码登录时，需要传入所有字段。


3.3 Request
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
=============== =============== =============================================
  Field Name         Type                        Description
=============== =============== =============================================
     token          String        用户名或者手机号，必须项
--------------- --------------- ---------------------------------------------
   password         String            密码。非必须项
--------------- --------------- ---------------------------------------------
     code           String          验证码。非必须项
--------------- --------------- ---------------------------------------------
   randomStr        String          前台请求验证码时创建的随机字符串。
                                   登录时的必须项，验证账号时不需要
=============== =============== =============================================

3.4 Sample Request
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
::

 1. 判断账户是否存在
    /auth/login?token=nihaodu
 2. 带验证码登录
    /auth/login?token=nihaodu&&password=123456&&randomStr=1234&&code=7nad
 3. 不带验证码登录
    /auth/login?token=nihaodu&&password=123456&&randomStr=1234


3.5 Response
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
=============== =============== =============================================
  Field Name         Type                        Description
=============== =============== =============================================
    status          String                           状态码
--------------- --------------- ---------------------------------------------
    message         String                          返回消息
--------------- --------------- ---------------------------------------------
     data           Number          当登录成功时，data返回登录用户的ID
=============== =============== =============================================

3.6 Sample Response
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
::

 1. 判断账户存在
    {
      "status": "AUTH-NORMAL-1001",
      "message": "账号存在",
      "data": null
    }
 2. 登录，验证码错误
    {
      "status": "AUTH-NORMAL-1001",
      "message": "验证码错误",
      "data": null
    }
 3. 登录成功
    {
      "status": "AUTH-NORMAL-1001",
      "message": "登录成功",
      "data": 1348
    }
 4. 密码错误
    {
      "status": "AUTH-NORMAL-1001",
      "message": "密码不正确，请重新输入",
      "data": null
    }


---------------------------------------------


4. 注册
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

4.1 访问路径
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
::

 GET /auth/register

4.2 逻辑
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>

 注册接口。
 1. 当只有phone参数时，只进行判断手机号码格式、是否可用。
 2. 当有code、randomStr参数，没有password参数时（phone参数此时无所谓有没有），进行验证码校验。
 3. 否则进行注册。

4.3 Request
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
=============== =============== =============================================
  Field Name         Type                        Description
=============== =============== =============================================
     phone          String                        手机号
--------------- --------------- ---------------------------------------------
     code           String                       验证码
--------------- --------------- ---------------------------------------------
   password         String                         密码
--------------- --------------- ---------------------------------------------
   randomStr        String                  前台生成的随机字符串
=============== =============== =============================================

4.4 Sample Request
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
::

    /auth/register?phone=18136085708&password=123456&&code=102302&&randomStr=1234

4.5 Response
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
=============== =============== =============================================
  Field Name         Type                        Description
=============== =============== =============================================
    status          String                           状态码
--------------- --------------- ---------------------------------------------
    message         String                          返回消息
--------------- --------------- ---------------------------------------------
     data            NUMBER                    注册时返回注册成功的ID
=============== =============== =============================================

4.6 Sample Response
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
::

 1. 验证手机号码格式和是否可用
     {
        "status": "AUTH-NORMAL-1001",
        "message": "手机号码已被使用",
        "data": null
     }
 2. 注册成功
    {
        "status": "AUTH-NORMAL-1001",
        "message": "注册成功",
        "data": 1364
    }
 3. 注册时密码格式不正确
    {
        "status": "AUTH-ERROR-1102",
        "message": "密码格式不正确",
        "data": null
    }

---------------------------------------------


5. 重置密码
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

5.1 访问路径
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
::

 PUT /auth/password/reset

5.2 逻辑
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>

 重置密码接口。
 1. 判断手机号是否存在
 2. 判断验证码是否正确
 3. 修改密码

5.3 Request
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
=============== =============== =============================================
  Field Name         Type                        Description
=============== =============== =============================================
     phone          String                手机号
--------------- --------------- ---------------------------------------------
     code           String                验证码
--------------- --------------- ---------------------------------------------
    newPSD          String                新密码
--------------- --------------- ---------------------------------------------
   randomStr        String               随机字符串
=============== =============== =============================================

5.4 Sample Request
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
::

 {
    "phone": "18136085708",
    "code": "828387",
    "randomStr": "1234",
    "newPSD": "111111"
 }

5.5 Response
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
=============== =============== =============================================
  Field Name         Type                        Description
=============== =============== =============================================
    status          String                           状态码
--------------- --------------- ---------------------------------------------
    message         String                          返回消息
--------------- --------------- ---------------------------------------------
     data            NULL
=============== =============== =============================================

5.6 Sample Response
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
::

 {
    "status": "AUTH-ERROR-",
    "message": "验证码错误",
    "data": null
 }

---------------------------------------------

