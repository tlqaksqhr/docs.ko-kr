---
title: "My.Response Object | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "My.MyWebExtension.Response"
  - "My.Response"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Response object"
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# My.Response Object
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

<xref:System.Web.UI.Page>에 연결된 <xref:System.Web.HttpResponse> 개체를 가져옵니다.  이 개체를 사용하면 클라이언트에 HTTP 응답 데이터를 보내고 이 응답에 대한 정보를 포함할 수 있습니다.  
  
## 설명  
 `My.Response` 개체는 페이지에 연결된 현재 <xref:System.Web.HttpResponse> 개체를 포함하고 있습니다.  
  
 `My.Response` 개체는 [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp-md.md)] 응용 프로그램에만 사용할 수 있습니다.  
  
## 예제  
 다음 예제에서는 `My.Request` 개체에서 헤더 컬렉션을 가져오고 `My.Response` 개체를 사용하여 ASP.NET 페이지에 씁니다.  
  
 [!code-vb[VbVbalrMyWeb#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-response-object_1.aspx)]  
  
## 참고 항목  
 <xref:System.Web.HttpResponse>   
 [My.Request Object](../../../visual-basic/language-reference/objects/my-request-object.md)