---
title: "방법: 어셈블리에서 형식 및 멤버 정보 가져오기 | Microsoft Docs"
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
  - "어셈블리[.NET Framework], 정보 가져오기"
  - "어셈블리 정보 가져오기"
ms.assetid: 348ae651-ccda-4f13-8eda-19e8337e9438
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: 어셈블리에서 형식 및 멤버 정보 가져오기
<xref:System.Reflection> 네임스페이스에는 어셈블리에서 정보를 가져오는데 사용되는 여러 가지 메서드가 들어있습니다.  이 단원에서는 이 메서드 중 하나에 대해 설명합니다.  자세한 내용은[리플렉션 개요](../../../docs/framework/reflection-and-codedom/reflection.md)를 참조하십시오.  
  
 다음 예제는 어셈블리에서 형식과 멤버 정보를 가져옵니다.  
  
## 예제  
 [!code-cpp[Conceptual.Types.ViewInfo#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source6.cpp#8)]
 [!code-csharp[Conceptual.Types.ViewInfo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source6.cs#8)]
 [!code-vb[Conceptual.Types.ViewInfo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source6.vb#8)]  
  
## 참고 항목  
 [Hosting Overview](http://msdn.microsoft.com/ko-kr/ea527626-99e3-4995-81c4-c8f3e60eb6d5)   
 [Programming with Application Domains](http://msdn.microsoft.com/ko-kr/bd36055b-56bd-43eb-b4d8-820c37172131)   
 [리플렉션](../../../docs/framework/reflection-and-codedom/reflection.md)   
 [응용 프로그램 도메인 사용](../../../docs/framework/app-domains/use.md)