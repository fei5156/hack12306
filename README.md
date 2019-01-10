# hack12306
12306 订票 Python SDK

## 项目结构
```
hack12306
├── LICENSE
├── README.md
├── hack12306
│   ├── __init__.py
│   ├── auth.py
│   ├── base.py
│   ├── constants.py
│   ├── exceptions.py
│   ├── order.py
│   ├── pay.py
│   ├── query.py
│   ├── settings.py
│   ├── user.py
│   └── utils.py
├── requirements-test.txt
├── setup.py
└── tests
    ├── __init__.py
    ├── config.py
    ├── test_auth.py
    ├── test_order.py
    ├── test_pay.py
    ├── test_query.py
    └── test_user.py
```

* hack12306/base.py 封装12306所有网络请求
* hack12306/auth.py 12306认证模块
* hack12306/user.py 用户信息查询模块
* hack12306/query.py 余票查询等公共信息查询模块
* hack12306/order.py 订票下单模块
* hack12306/pay.py 订单支付模块
* hack12306/settings.py 配置模块
* hack12306/utils.py 公共的工具函数
* hack12306/constangs.py 常量、枚举、状态等
* tests 测试用例

## 使用说明

用户认证（二维码）-> 查询余票 -> 提交订单 -> 支付订单

* 用户认证流程
![](http://processon.com/chart_image/5c2c2b92e4b0fa03ce872c0b.png)

* 提交订单流程
![](http://processon.com/chart_image/5c32a837e4b048f108c44b77.png)

* 支付订单流程
![](http://processon.com/chart_image/5c32a9a1e4b048f108c44d6f.png)

## 测试

```sh
git clone git@github.com:hack12306/hack12306.git;
virtualenv venv;
source venv/bin/activate;
pip install -r requirements-test.txt;
python setup.py install;
pytest --verbose tests/test_query.py;
python tests/test_auth.py;
python tests/test_order.py;
python tests/test_pay.py;
```
> 测试订单模块，需要配置`tests.config::COOKIES`, 测试支付模块，需要配置`tests.config::ORDER_SEQUENCE_NO`

## 集成

```sh
pip install hack12306 -U --user;
```