---
title: "방법: 프록시를 사용하여 인터넷과 통신하도록 WebRequest 설정 | Microsoft Docs"
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
ms.assetid: 63c0ef2c-44b5-4c54-9804-ba0b9b001ac7
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# 방법: 프록시를 사용하여 인터넷과 통신하도록 WebRequest 설정
사용 되는 전역 프록시 인스턴스를 만드는이 예제 <xref:System.Net.WebRequest> 는 인터넷과 통신 하는 프록시를 사용 하도록 합니다.  프록시 서버 라는 것을 전제로 `webproxy` 에서 통신 하는 표준 HTTP 포트 80을 포트입니다.  
  
## 예제  
  
```csharp  
WebProxy proxyObject = new WebProxy("http://webproxy:80/");  
GlobalProxySelection.Select = proxyObject;  
```  
  
```vb  
Dim proxyObject As WebProxy = New WebProxy("http://webproxy:80/")  
GlobalProxySelection.Select = proxyObject  
```  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   참조 하는  **System.Net** 네임 스페이스입니다.  
  
## 참고 항목  
 [응용 프로그램 프로토콜 사용](../../../docs/framework/network-programming/using-application-protocols.md)   
 [프록시를 통해 인터넷 액세스](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)