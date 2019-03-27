---
layout: post
title:  获得logo和LaunchImage
date:   2019-03-27 00:00:00 +0800
categories: iOS
tag: 杂七杂八-iOS
---

* content
{:toc}



一、获得logo图片 {#logo}
====================================

```
/** 获取app的icon图标名称 */
- (void)getAppIconName{
NSDictionary *infoDict = [[NSBundle mainBundle] infoDictionary];
//获取app中所有icon名字数组
NSArray *iconsArr = infoDict[@"CFBundleIcons"][@"CFBundlePrimaryIcon"][@"CFBundleIconFiles"];
//取最后一个icon的名字
NSString *iconLastName = [iconsArr lastObject];
//打印icon名字
NSLog(@"iconLastName: %@", iconLastName);
}

```

二、获得LaunchImage图片  {#LaunchImage}
====================================

```
/** 获取app的启动图片名称，并设置为本控制器背景图片 */
- (void)getLaunchImageName{
NSString *launchImageName = @""; //启动图片名称变量
CGFloat screenHeight = [UIScreen mainScreen].bounds.size.height;
//获取与当前设备匹配的启动图片名称
if (screenHeight == 480){ //4，4S
launchImageName = @"LaunchImage-700";
}
else if (screenHeight == 568){ //5, 5C, 5S, iPod
launchImageName = @"LaunchImage-700-568h";
}
else if (screenHeight == 667){ //6, 6S
launchImageName = @"LaunchImage-800-667h";
}
else if (screenHeight == 736){ // 6Plus, 6SPlus
launchImageName = @"LaunchImage-800-Landscape-736h";
}
else if (screenHeight == 812){ // x, xs
launchImageName = @"LaunchImage-800-Landscape-812h";
}
else if (screenHeight == 896){ // xr xsmax
launchImageName = @"LaunchImage-800-Landscape-896h";
}
if (launchImageName.length < 1) return;
//设备启动图片为控制器的背景图片
UIImage *img = [UIImage imageNamed:launchImageName];
self.view.backgroundColor = [UIColor colorWithPatternImage:img]; 
}
```