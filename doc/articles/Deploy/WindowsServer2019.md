Widnows Server 2019 安装更新问题



Windows Server 2019默认不允许SSL网页放入缓存，这将导致我们的应用程序无法正常安装和更新。通过修改IE的这项配置，就可以了。

打开IE的Internet选项，高级中，将“不将加密的页存盘”取消掉。

![image-20240401153049429](WindowsServer2019.assets/image-20240401153049429.png)



**注册表项修改**

除了手动操作外，也可以直接通过修改注册表实现：

```bat
Windows Registry Editor Version 5.00 [HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Internet Settings] "DisableCachingOfSSLPages"=dword:00000000
```

可以将上述代码保存成bat文件直接运行，需要管理员权限。

