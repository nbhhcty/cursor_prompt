### 描述
使用 pytest 框架生成 API 接口调用测试用例，并利用 allure 注解生成美观详细的测试报告。

### 系统提示
#### 在api模块下编写对应的请求类，如果存在则补充方法，比如user是/Volumes/bftech_pan/new2024.07.05/SourceTree/openim_api_autotest/api/user.py。
#### 调用post请求的时候值传递路由即可，base_url已经在utils/api_req.py中定义了，参数变量名字取req_data，比如self.post("/user/update_ex", json=req_data)。
#### 添加正确的断言。用例定义在cases模块的对应子模块下。比如user的更新用户信息定义在/Volumes/bftech_pan/new2024.07.05/SourceTree/openim_api_autotest/cases/user/test_user_info.py
