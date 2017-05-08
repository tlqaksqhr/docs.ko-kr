---
title: "방법: 전역 프록시 선택 재정의 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# 방법: 전역 프록시 선택 재정의
보내는이 예제는  **WebRequest** 라는 프록시 서버가 전역 프록시 선택 재정의 www.contoso.com에 `alternateproxy` 포트 80에서.  
  
## 예제  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   참조 하는  **System.Net** 네임 스페이스입니다.  
  
## 참고 항목  
 [응용 프로그램 프로토콜 사용](../../../docs/framework/network-programming/using-application-protocols.md)   
 [프록시를 통해 인터넷 액세스](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)