---
title: "GetRawInputDevices | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "GetRawInputDevices 메서드"
  - "원시 입력[WPF]"
ms.assetid: c4d37ecd-065a-4d1c-9e6c-26804ae968ca
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# GetRawInputDevices
PresentationHost.exe가 호스트 응용 프로그램과 관련된 원시 입력 장치\(휴먼 인터페이스 장치\)를 검색할 수 있게 합니다.  
  
## 구문  
  
```  
HRESULT GetRawInputDevices( [out] IEnumRAWINPUTDEVICE **ppEnum );  
```  
  
#### 매개 변수  
 `ppEnum`  
  
 \[out\] 원시 입력 장치를 열거하기 위한 [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md)에 대한 포인터입니다.  
  
## 속성 값\/반환 값  
 HRESULT:  
  
 S\_OK \- [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md)는 S\_OK가 반환된 경우에만 PresentationHost.exe에서 사용됩니다.  
  
 E\_NOTIMPL  
  
## 설명  
 원시 입력 장치는 키보드, 마우스 및 리모콘과 같은 덜 일반적인 장치를 포함하는 입력 장치 집합입니다.  
  
 원시 입력 장치 목록이 검색된 후 PresentationHost.exe는 WM\_INPUT 알림 메시지를 받을 장치를 등록합니다.  
  
## 참고 항목  
 [http:\/\/msdn.microsoft.com\/library\/default.asp?url\=\/library\/winui\/winui\/windowsuserinterface\/userinput\/rawinput\/rawinputreference\/rawinputfunctions\/getrawinputdevicelist.asp](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputfunctions/getrawinputdevicelist.asp)   
 [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md)