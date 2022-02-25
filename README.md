# YuanShen_User_Info
原神个人信息查询

用于调查研究原神现有用户的活跃天数和深渊情况

希望米哈游官方人员看到了不要和谐(

# 用法

- 首先运行`add_cookie.py`, 根据引导添加cookie (或者直接编辑`mys_cookies.db`)。

    可以添加多个cookie，系统会自动根据可用情况选择对应的cookie使用。

- 添加cookie后：

    - 直接运行`ys_UserInfoGet.py`

        系统会自动生成100个范围在100000000到210000000之间的UID，然后返回查询结果。返回完成后系统会自动在相对路径下生成Genshin Data.xlsx文件，可以使用Microsoft Excel打开查看。内容包含查询到的未关闭隐私的uid的活跃天数和深渊等级。

    - 或者运行`ys_UserInfoGet.py [uid1] [uid2] [uid3] ……`
    
        系统会查询指定的uid的信息并输出在屏幕上。

##  获取Cookie方法


1. 浏览器**无痕模式**打开 [https://bbs.mihoyo.com/ys/](https://bbs.mihoyo.com/ys/) ，登录账号
2. 打开[https://api-takumi.mihoyo.com/binding/api/getUserGameRolesByCookie](https://api-takumi.mihoyo.com/binding/api/getUserGameRolesByCookie)，（这个在这里获取Cookie并不会触发`Debugger`，当然也可以忽略这个步骤）
3. 按**⌥⌘I**(Option+Command+I) 或F12，打开`开发者工具`，找到并点击`Network`
4. 按**⌘R**(Command+R) 或F5刷新页面，按下图复制 Cookie：

![How to get mys cookie](https://i.loli.net/2020/10/28/TMKC6lsnk4w5A8i.png)

当触发`Debugger`时，可尝试按`Ctrl + F8`关闭，然后再次刷新页面，最后复制 Cookie。也可以使用另一种方法：

1. 复制代码 `var cookie=document.cookie;var ask=confirm('Cookie:'+cookie+'\n\nDo you want to copy the cookie to the clipboard?');if(ask==true){copy(cookie);msg=cookie}else{msg='Cancel'}`
2. 浏览器**无痕模式**打开 [https://bbs.mihoyo.com/ys/](https://bbs.mihoyo.com/ys/) ，登录账号
3. 按`F12`，打开`开发者工具`，找到并点击`Console`
4. 控制台粘贴代码并运行，获得类似`Cookie:xxxxxx`的输出信息
5. `xxxxxx`部分即为所需复制的 Cookie，点击确定复制


# 感谢列表：

[Steesha](https://github.com/Steesha)：帮忙拿到了DS的算法

[Womsxd](https://github.com/Womsxd)： 提供了详细的基本框架
