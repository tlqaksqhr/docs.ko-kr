---
title: "응용 프로그램 도메인 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application domains, about
- common language runtime, application domains
- runtime, application domains
ms.assetid: c6d99815-e022-4d2c-9420-1d7ab5b9d504
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: eade3728c8a51785214cf3d8de53d8a64a668f1f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="using-application-domains"></a>응용 프로그램 도메인 사용
응용 프로그램 도메인은 공용 언어 런타임에 대한 격리 단위를 제공하고 프로세스 내에서 생성되고 실행됩니다. 응용 프로그램 도메인은 대개 런타임을 프로세스로 로드하고 응용 프로그램 도메인 내에서 사용자 코드를 실행하는 응용 프로그램인 런타임 호스트에서 만들어집니다. 런타임 호스트는 프로세스와 기본 응용 프로그램 도메인을 만들고 그 내부에서 관리 코드를 실행합니다. 런타임 호스트에는 ASP.NET, Microsoft Internet Explorer 및 Windows 셸이 포함됩니다.  
  
 대부분 응용 프로그램의 경우 자체적인 응용 프로그램 도메인을 만들 필요가 없습니다. 런타임 호스트에서 필요한 응용 프로그램 도메인을 만듭니다. 그러나 응용 프로그램이 코드를 분리하거나 DLL을 사용하고 언로드해야 할 경우 직접 추가적인 응용 프로그램 도메인을 만들고 구성할 수 있습니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [방법: 응용 프로그램 도메인 만들기](../../../docs/framework/app-domains/how-to-create-an-application-domain.md)  
 응용 프로그램 도메인을 프로그래밍 방식으로 만드는 방법을 설명합니다.  
  
 [방법: 응용 프로그램 도메인 언로드](../../../docs/framework/app-domains/how-to-unload-an-application-domain.md)  
 응용 프로그램 도메인을 프로그래밍 방식으로 언로드하는 방법을 설명합니다.  
  
 [방법: 응용 프로그램 도메인 구성](../../../docs/framework/app-domains/how-to-configure-an-application-domain.md)  
 응용 프로그램 도메인을 구성하는 방법을 소개합니다.  
  
 [응용 프로그램 도메인에서 설치 정보 검색](../../../docs/framework/app-domains/retrieve-setup-information.md)  
 응용 프로그램 도메인에서 설정 정보를 검색하는 방법을 설명합니다.  
  
 [방법: 응용 프로그램 도메인에 어셈블리 로드](../../../docs/framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)  
 어셈블리를 응용 프로그램 도메인으로 로드하는 방법을 설명합니다.  
  
 [방법: 어셈블리에서 형식 및 멤버 정보 가져오기](../../../docs/framework/app-domains/how-to-obtain-type-and-member-information-from-an-assembly.md)  
 어셈블리에 대한 정보를 검색하는 방법을 설명합니다.  
  
 [어셈블리 섀도 복사](../../../docs/framework/app-domains/shadow-copy-assemblies.md)  
 어셈블리가 사용되는 동안 섀도 복사를 통해 어셈블리 업데이트를 허용하는 방법과 섀도 복사를 구성하는 방법을 설명합니다.  
  
 [방법: 첫째 예외 알림 받기](../../../docs/framework/app-domains/how-to-receive-first-chance-exception-notifications.md)  
 공용 언어 런타임이 예외 처리기 검색을 시작하기 전에 예외가 throw되었다는 알림을 받을 수 있는 방법을 설명합니다.  
  
 [어셈블리 로드 해결](../../../docs/framework/app-domains/resolve-assembly-loads.md)  
 <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> 이벤트를 사용하여 어셈블리 로드 실패를 해결하는 방법에 대한 지침을 제공합니다.  
  
## <a name="reference"></a>참조  
 <xref:System.AppDomain>  
 응용 프로그램 도메인을 나타냅니다. 응용 프로그램 도메인을 만들고 제어하기 위한 메서드를 제공합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [공용 언어 런타임의 어셈블리](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 어셈블리가 실행하는 함수의 개요를 제공합니다.  
  
 [어셈블리를 사용한 프로그래밍](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 어셈블리를 만들고, 서명하고, 특성을 설정하는 방법에 대해 설명합니다.  
  
 [동적 메서드 및 어셈블리 내보내기](../../../docs/framework/reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
 동적 어셈블리를 만드는 방법에 대해 설명합니다.  
  
 [응용 프로그램 도메인](../../../docs/framework/app-domains/application-domains.md)  
 응용 프로그램 도메인에 대해 개념적으로 설명합니다.  
  
 [리플렉션 개요](../../../docs/framework/reflection-and-codedom/reflection.md)  
 **Reflection** 클래스를 사용하여 어셈블리에 대한 정보를 얻는 방법을 설명합니다.
