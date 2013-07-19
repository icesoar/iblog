---
layout: post
title: "Jenkins XCode iOS code signing"
description: "Jenkins中XCode iOS签名问题"
category: CodeBuilding
tags: [Jenkins, iOS, XCode, Code Signing]
---
{% include JB/setup %}

###无法找到Provisioning Profile

	== Available provisioning profiles
	[ios] $ /usr/bin/security find-identity -p codesigning -v
    	 0 valid identities found

原因是Jenkins没有权限访问KeyChains，具体原因不明，根据解决方法来看，也许和Session有关。解决方法：

打开`/Library/LaunchDaemons/org.jenkins-ci.plist`，添加代码    
	`<key>SessionCreate</key>`
	`<true/>`


###签名失败

	...build/[YourAppName].app: User interaction is not allowed.
	Command /usr/bin/codesign failed with exit code 1

原因是codesign没有权限访问Key。解决方法：

（我使用的是中文版系统）
打开“钥匙串访问”，“钥匙串”中选择“登录”，“种类”中选择“证书”。找到你的iOS签名证书，双击对应的私钥（专用密钥）打开属性窗口，进入“访问控制”页面。检查“总是允许通过这些应用程序访问”中是否有“codesign”，如没有，点击“+”，找到`/usr/bin/codesign`，将其加入。点击“存储更改”。

