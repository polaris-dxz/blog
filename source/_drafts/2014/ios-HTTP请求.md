---
title: ios HTTP请求
date: 2014-05-16 20:56:40
categories:
tags: iOS
thumbnail:
---

iOS9引入了新特性 [App Transport Security (ATS)](https://developer.apple.com/library/prerelease/ios/releasenotes/General/WhatsNewIniOS/Articles/iOS9.html#//apple_ref/doc/uid/TP40016198-DontLinkElementID_13)，所以需要在 Info.plist加入NSAppTransportSecurity 字典的 AllowsArbitraryLoads key的值为 BOOL。

<!-- more -->

## POST 请求

早期还有NSURLConnection方法，iOS 9 以后被淘汰了，有几个代理方法不能用了（同步请求，异步请求）



原生方法：

```objc
    NSURL* url = [NSURL URLWithString:HomeUrl]; //url
    NSURLRequest* request = [NSURLRequest requestWithURL:url];//请求
    NSURLSession* session = [NSURLSession sharedSession]; //session
    NSURLSessionDataTask* task = [session dataTaskWithRequest:request completionHandler:^(NSData * _Nullable data, NSURLResponse * _Nullable response, NSError * _Nullable error) {
        if(error){
            
            NSLog(@"请求失败");
        }
        else{
            
            NSLog(@"请求成功");
            NSString *receiveStr = [[NSString alloc]initWithData:data encoding:NSUTF8StringEncoding];
            
            NSData * jsonData = [receiveStr dataUsingEncoding:NSUTF8StringEncoding];
            
            NSDictionary *jsonDict = [NSJSONSerialization JSONObjectWithData:jsonData options:NSJSONReadingMutableLeaves error:nil];
        }
    }];
    [task resume];
```







