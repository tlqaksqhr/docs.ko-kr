---
title: "My.Request Object | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "My.MyWebExtension.Request"
  - "My.Request"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Request object"
ms.assetid: 93d5f0e2-6b60-4a2c-8652-d90216f6ad10
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# My.Request Object
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

요청된 페이지의 <xref:System.Web.HttpRequest> 개체를 가져옵니다.  
  
## 설명  
 `My.Request` 개체에는 현재 HTTP 요청 정보가 포함되어 있습니다.  
  
 `My.Request` 개체는 ASP.NET 응용 프로그램에만 사용할 수 있습니다.  
  
## 예제  
 다음 예제에서는 `My.Request` 개체에서 헤더 컬렉션을 가져오고 `My.Response` 개체를 사용하여 ASP.NET 페이지에 씁니다.  
  
 [!code-vb[VbVbalrMyWeb#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-request-object_1.aspx)]  
  
## 참고 항목  
 <xref:System.Web.HttpRequest>   
 [My.Response Object](../../../visual-basic/language-reference/objects/my-response-object.md)