---
title: "응용 프로그램 도메인에서 설치 정보 검색"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- AppDomainSetup object
- retrieving setup information
- application domains, retrieving setup information
ms.assetid: 5cdb12ae-1e37-4a62-8ec7-93d6dcc6e8d9
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ed6674580649e645ea3e647fa00682f2545255e9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="retrieving-setup-information-from-an-application-domain"></a>응용 프로그램 도메인에서 설치 정보 검색
응용 프로그램 도메인의 각 인스턴스는 두 속성과 <xref:System.AppDomainSetup> 정보로 구성됩니다. <xref:System.AppDomain?displayProperty=nameWithType> 클래스를 사용하여 응용 프로그램 도메인에서 설치 정보를 검색할 수 있습니다. 이 클래스는 응용 프로그램 도메인에 대한 구성 정보를 검색하는 여러 멤버를 제공합니다.  
  
 응용 프로그램 도메인에 대한 **AppDomainSetup** 개체를 쿼리하여 만들 때 도메인에 전달된 설치 정보를 가져올 수도 있습니다.  
  
 다음 예제에서는 새 응용 프로그램 도메인을 만들고 여러 멤버 값을 콘솔에 출력합니다.  
  
 [!code-cpp[AppDomain_Setup#2](../../../samples/snippets/cpp/VS_Snippets_CLR/AppDomain_Setup/CPP/source2.cpp#2)]
 [!code-csharp[AppDomain_Setup#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AppDomain_Setup/CS/source2.cs#2)]
 [!code-vb[AppDomain_Setup#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AppDomain_Setup/VB/source2.vb#2)]  
  
 다음 예제에서는 응용 프로그램 도메인에 대한 설치 정보를 설정한 후 검색합니다. `AppDomain.SetupInformation.ApplicationBase`는 구성 정보를 가져옵니다.  
  
 [!code-cpp[AppDomain_Setup#3](../../../samples/snippets/cpp/VS_Snippets_CLR/AppDomain_Setup/CPP/source3.cpp#3)]
 [!code-csharp[AppDomain_Setup#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AppDomain_Setup/CS/source3.cs#3)]
 [!code-vb[AppDomain_Setup#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AppDomain_Setup/VB/source3.vb#3)]  
  
## <a name="see-also"></a>참고 항목  
 [응용 프로그램 도메인으로 프로그래밍](http://msdn.microsoft.com/en-us/bd36055b-56bd-43eb-b4d8-820c37172131)  
 [응용 프로그램 도메인 사용](../../../docs/framework/app-domains/use.md)
