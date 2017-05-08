---
title: "응용 프로그램 도메인에서 설치 정보 검색 | Microsoft Docs"
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
  - "AppDomainSetup 개체"
  - "응용 프로그램 도메인, 설정 정보 검색"
  - "설정 정보 검색"
ms.assetid: 5cdb12ae-1e37-4a62-8ec7-93d6dcc6e8d9
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# 응용 프로그램 도메인에서 설치 정보 검색
응용 프로그램 도메인의 각 인스턴스는 속성과 <xref:System.AppDomainSetup> 정보로 구성됩니다.  <xref:System.AppDomain?displayProperty=fullName> 클래스를 사용하면 응용 프로그램 도메인에서 설치 정보를 검색할 수 있습니다.  이 클래스에서는 몇몇 멤버를 제공하는데, 이 멤버는 응용 프로그램 도메인과 관련된 구성 정보를 검색합니다.  
  
 또한 응용 프로그램 도메인에서 **AppDomainSetup** 개체를 쿼리하면 이전에 도메인에 전달되었던 설치 정보를 얻을 수 있습니다.  
  
 다음 예제는 새 응용 프로그램 도메인을 만든 다음 몇몇 멤버 값을 콘솔에 출력합니다.  
  
 [!code-cpp[AppDomain_Setup#2](../../../samples/snippets/cpp/VS_Snippets_CLR/AppDomain_Setup/CPP/source2.cpp#2)]
 [!code-csharp[AppDomain_Setup#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AppDomain_Setup/CS/source2.cs#2)]
 [!code-vb[AppDomain_Setup#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AppDomain_Setup/VB/source2.vb#2)]  
  
 다음 예제는 응용 프로그램 도메인의 설치 정보를 설정한 다음 검색합니다.  `AppDomain.SetupInformation.ApplicationBase`를 사용하여 구성 정보를 가져온다는 점에 주목합니다.  
  
 [!code-cpp[AppDomain_Setup#3](../../../samples/snippets/cpp/VS_Snippets_CLR/AppDomain_Setup/CPP/source3.cpp#3)]
 [!code-csharp[AppDomain_Setup#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AppDomain_Setup/CS/source3.cs#3)]
 [!code-vb[AppDomain_Setup#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AppDomain_Setup/VB/source3.vb#3)]  
  
## 참고 항목  
 [Hosting Overview](http://msdn.microsoft.com/ko-kr/ea527626-99e3-4995-81c4-c8f3e60eb6d5)   
 [Programming with Application Domains](http://msdn.microsoft.com/ko-kr/bd36055b-56bd-43eb-b4d8-820c37172131)   
 [응용 프로그램 도메인 사용](../../../docs/framework/app-domains/use.md)