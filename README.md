# 其他解控

此方案可以在(launcher3 5.0.300*-5.02.007)可用

#### 对于平板是密码进入管理员的

[获取管理员密码](https://github.com/KuzeKumiko/Lenovo_tb_x505f_StudyNM/blob/main/getpwd.exe)

进入管理员后 打开usb，如果你是华为，你可能需要断网登录进入设置里连点5次版本号打开开发者并激活usb调试(adb)

如果成功连接电脑

```
adb devices
```

命令行会出现你的设备

然后接下来

```
adb shell am startservice -n com.android.launcher3/com.drupe.swd.launcher.huoshan.mdm.service.ExecuteCmdService --es "cmd" "command_release_control"
```

华为设备的话是重启 其他设备有可能下载浏览器 我不知道 看着办吧

#### 对于设备是二维码 但是我有方法装上程序

自己去写一个吧

```
Intent intent =new Intent();
intent.setAction("com.drupe.swd.launcher.huoshan.mdm.service.ExecuteCmdService");
intent.putExtra("cmd","command_release_control");
intent.putExtra("active",1);//optional
intent.setPackage("com.android.launcher3");
context.startService(intent);
```

[或者直接用现成的,记得改包名](https://github.com/YoungToday/rc/raw/main/app-release.apk)

