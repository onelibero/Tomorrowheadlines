## 工程介绍

- common：定义项目通用配置(如异常)
- feign-api：远程接口调用
- gateway：管理网关微服务
- model：对应实体类（pojo，dto）
- service：吧微服务做统一管理（写对应服务）
- test：测试
- utils：工具类

## 全局异常

common中进行定义

- 处理不可控异常
- 处理可控异常（自定义处理）
  - ExceptionHandler(指定异常类型)
- resources目录下的META-INF下的spring.factories指定
  - 只要有微服务引入了这个模块，在初始化spring容器的时候就会找到这个类，吧当前这个类进行初始化

## 用户表

- tinyint类型：不知道unsigned（非负数），范围（-128-127），指定unsigned，范围（0,255），通常表示小范围的数值，或者表示true或false
- salt：盐值，一般用作md5加密算法的加密值
  - 手动加密，md5+随机字符串
  - 注册：根据用户生成salt，对密码+salt进行md5加密，将salt和加密后密码进行存储
  - 登录：用户输入密码和查出来的salt进行md5加密，对比密码

## 微服务搭建

service搭建微服务

- 新建user模块
  - 写好相应的模块（控制层，服务器，启动类）
  - 在资源目录下新建
    - bootstarp.yml：配置文件（端口和nacos配置）
    - logback.xml：日志
    - 相关Mybatis等配置放在nacos上进行配置



