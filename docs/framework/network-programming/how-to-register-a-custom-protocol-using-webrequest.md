---
title: "방법: WebRequest를 사용하여 사용자 지정 프로토콜 등록 | Microsoft Docs"
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
ms.assetid: 98ddbdb9-66b1-4080-92ad-51f5c447fcf8
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# 방법: WebRequest를 사용하여 사용자 지정 프로토콜 등록
프로토콜 특정 클래스를 등록 하는 방법을 보여 주는이 예제다른 곳에서 정의 됩니다.  이 예제에서 `CustomWebRequestCreator` 구현 하는 사용자 구현 개체입니다는  **만들기** 를 반환 하는 메서드는 `CustomWebRequest` 개체.  작성 한 코드 예제는 `CustomWebRequest` 사용자 지정 프로토콜을 구현 하는 코드입니다.  
  
## 예제  
  
```csharp  
WebRequest.RegisterPrefix("custom", new CustomWebRequestCreator());  
WebRequest req = WebRequest.Create("custom://customHost.contoso.com/");  
```  
  
```vb  
WebRequest.RegisterPrefix("custom", New CustomWebRequestCreator())  
Dim req As WebRequest = WebRequest.Create("custom://customHost.contoso.com/")  
```  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
 참조 하는 <xref:System.Net> 네임 스페이스입니다.  
  
## 참고 항목  
 [플러그형 프로토콜 프로그래밍](../../../docs/framework/network-programming/programming-pluggable-protocols.md)