> #### 作者主页：[舒克日记](https://blog.csdn.net/cativen)
>
>  简介：Java领域优质创作者、Java项目、学习资料、技术互助
>
> <b><font color=red>文中获取源码</font></b>

## 系统概要

​

本文将介绍一款基于Java开发的仓库管理系统，该系统可以帮助企业实现对仓库物品的高效管理，提高仓库运营效率。文章将详细介绍系统的架构、功能以及实际应用场景。

## 引言

随着电商行业的快速发展，仓库管理变得越来越重要。一个高效的仓库管理系统可以降低企业的运营成本，提高物流效率，为客户提供更好的服务。本文将介绍一款基于Java开发的仓库管理系。

## 功能模块

一、业务模块

1、客户管理

客户列表 客户分页和模糊查询 客户的增删改查

2、供应商管理

供应商列表 供应商分页和模糊查询 供应商的增删改查

3、商品管理

商品列表 商品分页和模糊查询 商品的增删改查

4、商品进货管理

商品进货列表 商品进货分页和模糊查询 商品进货的增删改查

5、商品退货管理

商品退货列表 商品退货分页和模糊查询 商品退货删除

6、商品销售管理

商品销售列表 商品销售分页和模糊查询 商品销售的增删改查，也包括商品的退户管理

7、商品销售退货管理

商品销售退货列表 商品销售退货分页和模糊查询 商品销售退货删除

二、系统模块

1、用户登陆

校验用户名、密码以及验证码 登陆成功将登陆信息写入登陆日志 未登录直接访问服务器资源进行拦截

2、菜单管理

全查询菜单和根据左边的树查询不同菜单 菜单的添加、修改、删除

3、角色管理

全查询角色和模糊查询 角色的添加、修改、删除以及给角色分配权限

4、用户管理

全查询用户和模糊查询 用户的添加、修改、删除、重置密码以及给用户分配角色

5、部门管理

全查询部门、模糊查询以及根据左边的树查询不同的部门 部门的添加、修改、删除 技术选型

# 运行指导

idea导入源码空间站顶目教程说明(Vindows版)-ssm篇：

http://mtw.so/5MHvZq

源码地址：[http://www.codegym.top](http://www.codegym.top/)



## 后台技术选型

SpringBoot Shiro MybatisPlus

## 前端技术选型

LayUI、DTree

开发环境

操作系统：Windows 10、Java、IDEA、Navicat、Git、Maven 3.5.2、Tomcat 8.5、MySQL 5.0

## 截图

![微信图片20240926000139](https://img-blog.csdnimg.cn/img_convert/6d366ef9c9379a1839a81357543de900.png)

![微信图片20240926000214](https://img-blog.csdnimg.cn/img_convert/d812801f4b20f4b53a0b5a35ed6164d9.png)

![微信图片20240926000222](https://img-blog.csdnimg.cn/img_convert/b197debdc25726537922db78c2ac16dd.png)

![微信图片20240926000227](https://img-blog.csdnimg.cn/img_convert/2015cb37fffdff6f3af366a51c78e3c7.png)

![微信图片20240926000234](https://img-blog.csdnimg.cn/img_convert/2c26a250cff9efa0b419af78e1ae81d5.png)

### 代码

```
    private String getToken(UserDO userDO) {
        TokenInfo tokenInfo = new TokenInfo();
        tokenInfo.setUserId(userDO.getId());
        tokenInfo.setTenantId(userDO.getTenantId());
        tokenInfo.setUserName(userDO.getUsername());
        if (userDO.getId().equals(platformConfig.getAdministratorId())) {
            tokenInfo.setTypeEnum(com.qqt.iot.enums.UserTypeEnum.ADMIN);
        } else {
            tokenInfo.setTypeEnum(com.qqt.iot.enums.UserTypeEnum.USER);
        }
        return JwtUtils.genToken(tokenInfo);
    }
```
