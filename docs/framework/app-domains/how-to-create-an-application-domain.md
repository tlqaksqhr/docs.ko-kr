---
title: "방법: 응용 프로그램 도메인 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "응용 프로그램 도메인, 만들기"
ms.assetid: ba1fa43e-49f5-47d9-bd7f-3024af16f4ba
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: 응용 프로그램 도메인 만들기
응용 프로그램 도메인은 필요할 경우 CLR\(공용 언어 런타임\) 호스트에 의해 자동으로 만들어집니다  그러나 사용자가 응용 프로그램 도메인을 직접 만들어 개별적으로 관리하려는 어셈블리를 로드할 수도 있습니다.  또한 코드를 실행하려는 응용 프로그램 도메인을 만들 수 있습니다.  
  
 사용자는 <xref:System.AppDomain?displayProperty=fullName> 클래스에서 오버로드된 **CreateDomain** 메서드 중 하나를 사용하여 새 응용 프로그램 도메인을 만들 수 있습니다.  이 응용 프로그램 도메인에 이름을 지정하고 이 이름을 사용하여 도메인을 참조할 수 있습니다.  
  
 다음 예제는 새 응용 프로그램 도메인을 만들고 `MyDomain`으로 이름을 지정한 다음 호스트 도메인 이름과 새로 만들어진 자식 응용 프로그램 도메인을 콘솔에 출력합니다.  
  
## 예제  
 [!code-cpp[ADCreateDomain#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADCreateDomain/CPP/source2.cpp#2)]
 [!code-csharp[ADCreateDomain#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADCreateDomain/CS/source2.cs#2)]
 [!code-vb[ADCreateDomain#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADCreateDomain/VB/source2.vb#2)]  
  
## 참고 항목  
 [Hosting Overview](http://msdn.microsoft.com/ko-kr/ea527626-99e3-4995-81c4-c8f3e60eb6d5)   
 [Programming with Application Domains](http://msdn.microsoft.com/ko-kr/bd36055b-56bd-43eb-b4d8-820c37172131)   
 [응용 프로그램 도메인 사용](../../../docs/framework/app-domains/use.md)