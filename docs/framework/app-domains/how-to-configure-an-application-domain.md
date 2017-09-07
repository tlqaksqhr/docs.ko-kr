---
title: "방법: 응용 프로그램 도메인 구성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application domains, configuring
- ApplicationBase property
ms.assetid: 07ea8438-7a34-49f0-a7e8-3d6ff7e4a482
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4f8c91a11deac63e2ad44628a609ed4ca6501e84
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-configure-an-application-domain"></a>방법: 응용 프로그램 도메인 구성
<xref:System.AppDomainSetup> 클래스를 사용하여 새 응용 프로그램 도메인에 대한 구성 정보를 공용 언어 런타임에 제공할 수 있습니다. 사용자 고유의 응용 프로그램 도메인을 만들 때 가장 중요한 속성은 <xref:System.AppDomainSetup.ApplicationBase%2A>입니다. 다른 **AppDomainSetup** 속성은 런타임 호스트에서 특정 응용 프로그램 도메인을 구성하는 데 주로 사용됩니다.  
  
 **ApplicationBase** 속성은 응용 프로그램의 루트 디렉터리를 정의합니다. 런타임에서 형식 요청을 충족해야 하는 경우 **ApplicationBase** 속성에 지정된 디렉터리에서 해당 형식을 포함하는 어셈블리를 찾습니다.  
  
> [!NOTE]
>  새 응용 프로그램 도메인은 생성자의 **ApplicationBase** 속성만 상속합니다.  
  
 다음 예제에서는 **AppDomainSetup** 클래스 인스턴스를 만들고, 이 클래스를 사용하여 새 응용 프로그램 도메인을 만들고, 콘솔에 정보를 기록한 다음 응용 프로그램 도메인을 언로드합니다.  
  
## <a name="example"></a>예제  
 [!code-cpp[ADApplicationBase#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADApplicationBase/CPP/source2.cpp#2)] [!code-csharp[ADApplicationBase#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADApplicationBase/CS/source2.cs#2)] [!code-vb[ADApplicationBase#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADApplicationBase/VB/source2.vb#2)]  
  
## <a name="see-also"></a>참고 항목  
 [응용 프로그램 도메인으로 프로그래밍](http://msdn.microsoft.com/en-us/bd36055b-56bd-43eb-b4d8-820c37172131)   
 [응용 프로그램 도메인 사용](../../../docs/framework/app-domains/use.md)

