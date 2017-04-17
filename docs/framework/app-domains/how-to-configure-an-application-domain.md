---
title: "방법: 응용 프로그램 도메인 구성 | Microsoft Docs"
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
  - "응용 프로그램 도메인, 구성"
  - "ApplicationBase 속성"
ms.assetid: 07ea8438-7a34-49f0-a7e8-3d6ff7e4a482
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: 응용 프로그램 도메인 구성
<xref:System.AppDomainSetup> 클래스를 사용하면 새 응용 프로그램 도메인의 구성 정보를 공용 언어 런타임에 제공할 수 있습니다.  사용자 고유의 응용 프로그램도 메인을 만드는 경우 가장 중요한 속성은 <xref:System.AppDomainSetup.ApplicationBase%2A>입니다.  다른 **AppDomainSetup** 속성은 런타임 호스트에서 특정 응용 프로그램 도메인을 구성하는 데 주로 사용됩니다.  
  
 **ApplicationBase** 속성은 응용 프로그램의 루트 디렉터리를 정의합니다.  형식 요청을 충족시켜기 위해 런타임은 이 형식이 포함된 어셈블리를 **ApplicationBase** 속성의 지정 디렉터리에서 검색합니다.  
  
> [!NOTE]
>  새 응용 프로그램 도메인은 작성자의 **ApplicationBase** 속성만을 상속합니다.  
  
 다음 예제는 **AppDomainSetup** 클래스의 인스턴스를 만들고, 이 클래스를 사용하여 새 응용 프로그램 도메인을 만들고, 정보를 콘솔에 출력한 다음 응용 프로그램 도메인을 언로드합니다.  
  
## 예제  
 [!code-cpp[ADApplicationBase#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADApplicationBase/CPP/source2.cpp#2)]
 [!code-csharp[ADApplicationBase#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADApplicationBase/CS/source2.cs#2)]
 [!code-vb[ADApplicationBase#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADApplicationBase/VB/source2.vb#2)]  
  
## 참고 항목  
 [Hosting Overview](http://msdn.microsoft.com/ko-kr/ea527626-99e3-4995-81c4-c8f3e60eb6d5)   
 [Programming with Application Domains](http://msdn.microsoft.com/ko-kr/bd36055b-56bd-43eb-b4d8-820c37172131)   
 [응용 프로그램 도메인 사용](../../../docs/framework/app-domains/use.md)