# Shiro安全框架入门篇（登录验证实例详解与源码）

## 一、Shiro框架简单介绍

Apache Shiro是Java的一个安全框架，旨在简化身份验证和授权。Shiro在JavaSE和JavaEE项目中都可以使用。它主要用来处理身份认证，授权，企业会话管理和加密等。Shiro的具体功能点如下：

（1）身份认证/登录，验证用户是不是拥有相应的身份；

（2）授权，即权限验证，验证某个已认证的用户是否拥有某个权限；即判断用户是否能做事情，常见的如：验证某个用户是否拥有某个角色。或者细粒度的验证某个用户对某个资源是否具有某个权限；

（3）会话管理，即用户登录后就是一次会话，在没有退出之前，它的所有信息都在会话中；会话可以是普通JavaSE环境的，也可以是如Web环境的；

（4）加密，保护数据的安全性，如密码加密存储到数据库，而不是明文存储；

（5）Web支持，可以非常容易的集成到Web环境；

Caching：缓存，比如用户登录后，其用户信息、拥有的角色/权限不必每次去查，这样可以提高效率；

（6）shiro支持多线程应用的并发验证，即如在一个线程中开启另一个线程，能把权限自动传播过去；

（7）提供测试支持；

（8）允许一个用户假装为另一个用户（如果他们允许）的身份进行访问；

（9）记住我，这个是非常常见的功能，即一次登录后，下次再来的话不用登录了。

文字描述可能并不能让猿友们完全理解具体功能的意思。下面我们以登录验证为例，向猿友们介绍Shiro的使用。至于其他功能点，猿友们用到的时候再去深究其用法也不迟。