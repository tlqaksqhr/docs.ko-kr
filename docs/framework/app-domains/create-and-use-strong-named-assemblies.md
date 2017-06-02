---
title: "강력한 이름의 어셈블리 만들기 및 사용 | Microsoft Docs"
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
- strong-name bypass feature
- strong-named assemblies, about strong-named assemblies
- strong-named assemblies
- signing assemblies
- assemblies [.NET Framework], signing
- strong-named assemblies, scenarios
- assemblies [.NET Framework], strong-named
- strong-named assemblies, loading into trusted application domains
- assembly binding, strong-named
ms.assetid: ffbf6d9e-4a88-4a8a-9645-4ce0ee1ee5f9
caps.latest.revision: 17
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 7c694fc26d65fee277c7a6873494c8d1900408b2
ms.contentlocale: ko-kr
ms.lasthandoff: 06/02/2017

---
# <a name="creating-and-using-strong-named-assemblies"></a>강력한 이름의 어셈블리 만들기 및 사용
<a name="top"></a> 강력한 이름은 간단한 텍스트 이름, 버전 번호 및 문화권 정보(제공되는 경우)를 포함하는 어셈블리 ID와 공개 키 및 디지털 서명으로 구성됩니다. 디지털 서명은 해당 개인 키를 사용하여 어셈블리 파일에서 생성됩니다. 어셈블리 파일은 어셈블리를 구성하는 모든 파일의 이름과 해시가 들어 있는 어셈블리 매니페스트를 포함합니다.  
  
 강력한 이름의 어셈블리는 다른 강력한 이름의 어셈블리에서 형식만 사용할 수 있습니다. 그러지 않으면 강력한 이름의 어셈블리 보안이 손상됩니다.  
  
 이 개요는 다음과 같은 단원으로 구성됩니다.  
  
-   [강력한 이름 시나리오](#strong_name_scenario)  
  
-   [신뢰할 수 있는 어셈블리의 서명 확인 건너뛰기](#bypassing_signature_verification)  
  
-   [관련 항목](#related_topics)  
  
<a name="strong_name_scenario"></a>   
## <a name="strong-name-scenario"></a>강력한 이름 시나리오  
 다음 시나리오에서는 강력한 이름이 있는 어셈블리에 서명하고 나중에 이 이름을 사용하여 해당 어셈블리를 참조하는 과정에 대해 설명합니다.  
  
1.  다음 방법 중 하나를 사용하여 강력한 이름의 어셈블리 A를 만듭니다.  
  
    -   강력한 이름 만들기를 지원하는 개발 환경(예: [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)])을 사용합니다.  
  
    -   [Sn.exe(강력한 이름 도구)](../../../docs/framework/tools/sn-exe-strong-name-tool.md)를 사용하여 암호화 키 쌍을 만들고 명령줄 컴파일러 또는 [Al.exe(어셈블리 링커)](../../../docs/framework/tools/al-exe-assembly-linker.md)를 사용하여 해당 키 쌍을 어셈블리에 할당합니다. Windows SDK(소프트웨어 개발 키트)는 Sn.exe와 Al.exe를 모두 제공합니다.  
  
2.  개발 환경 또는 도구에서는 개발자 개인 키를 사용하여 어셈블리 매니페스트가 포함된 파일의 해시에 서명합니다. 이 디지털 서명은 어셈블리 A의 매니페스트가 포함된 PE(이식 가능한 실행) 파일에 저장됩니다.  
  
3.  어셈블리 B는 어셈블리 A의 소비자입니다. 어셈블리 B의 매니페스트에 있는 참조 섹션에는 어셈블리 A의 공개 키를 나타내는 토큰이 있습니다. 토큰은 전체 공개 키의 일부이며, 공간을 절약하기 위해 키 자체 대신 사용됩니다.  
  
4.  어셈블리가 전역 어셈블리 캐시에 있는 경우 공용 언어 런타임은 강력한 이름 서명을 확인합니다. 런타임에 강력한 이름으로 바인딩할 때 공용 언어 런타임은 어셈블리 B의 매니페스트에 저장된 키와 어셈블리 A의 강력한 이름을 생성하는 데 사용된 키를 비교합니다. .NET Framework 보안 검사를 통과하고 바인딩에 성공하면, 어셈블리 B에서 어셈블리 A의 비트가 변조되지 않았고 실제로 어셈블리 A의 개발자가 이러한 비트를 전달했음을 보증합니다.  
  
> [!NOTE]
>  이 시나리오에서는 신뢰 문제를 다루지 않습니다. 어셈블리에는 강력한 이름 외에도 전체 Microsoft Authenticode 서명이 있을 수 있습니다. Authenticode 서명에는 신뢰 관계를 설정하는 인증서가 포함되어 있습니다. 강력한 이름에는 이런 방식으로 코드에 서명하지 않아도 된다는 점에 유의하는 것이 중요합니다. 사실상 강력한 이름 서명을 생성하는 데 사용되는 키가 Authenticode 서명을 생성하는 데 사용되는 키와 동일하지 않아도 됩니다.  
  
 [맨 위로 이동](#top)  
  
<a name="bypassing_signature_verification"></a>   
## <a name="bypassing-signature-verification-of-trusted-assemblies"></a>신뢰할 수 있는 어셈블리의 서명 확인 건너뛰기  
 [!INCLUDE[net_v35SP1_long](../../../includes/net-v35sp1-long-md.md)]부터는 어셈블리가 완전 신뢰 응용 프로그램 도메인(예: `MyComputer` 영역의 기본 응용 프로그램 도메인)에 로드될 때 강력한 이름 서명의 유효성을 검사하지 않습니다. 이를 강력한 이름 건너뛰기 기능이라고 합니다. 완전 신뢰 환경에서는 <xref:System.Security.Permissions.StrongNameIdentityPermission>에 대한 요청이 해당 서명과 관계없이 서명된 완전 신뢰 어셈블리에 대해 항상 성공합니다. 강력한 이름 건너뛰기 기능을 사용하면 이러한 상황에서 완전 신뢰 어셈블리의 강력한 이름 서명을 확인하는 데 따르는 불필요한 오버헤드가 발생하지 않으므로 어셈블리가 더 빠르게 로드됩니다.  
  
 건너뛰기 기능은 강력한 이름으로 서명되었으며 다음과 같은 특징이 있는 모든 어셈블리에 적용됩니다.  
  
-   <xref:System.Security.Policy.StrongName> 증명 정보 없이 완전 신뢰 가능(예: `MyComputer` 영역 증명 정보 보유)  
  
-   완전히 신뢰할 수 있는 <xref:System.AppDomain>에 로드됨  
  
-   해당 <xref:System.AppDomain>의 <xref:System.AppDomainSetup.ApplicationBase%2A> 속성 아래에 있는 위치에서 로드됨  
  
-   서명이 연기되지 않음  
  
 개별 응용 프로그램 또는 컴퓨터에 대해 이 기능을 사용하지 않도록 설정할 수 있습니다. [방법: 강력한 이름 건너뛰기 기능 비활성화](../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md)를 참조하세요.  
  
 [맨 위로 이동](#top)  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a>관련 항목  
  
|제목|설명|  
|-----------|-----------------|  
|[방법: 공개/개인 키 쌍 만들기](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md)|어셈블리 서명을 위해 암호화 키 쌍을 만드는 방법에 대해 설명합니다.|  
|[방법: 강력한 이름으로 어셈블리 서명](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)|강력한 이름의 어셈블리를 만드는 방법에 대해 설명합니다.|  
|[향상된 강력한 이름 지정](../../../docs/framework/app-domains/enhanced-strong-naming.md)|[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에서 강력한 이름에 대해 향상된 기능을 설명합니다.|  
|[방법: 강력한 이름의 어셈블리 참조](../../../docs/framework/app-domains/how-to-reference-a-strong-named-assembly.md)|컴파일 타임 또는 런타임에 강력한 이름의 어셈블리에 있는 형식 또는 리소스를 참조하는 방법에 대해 설명합니다.|  
|[방법: 강력한 이름 건너뛰기 기능 비활성화](../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md)|강력한 이름 서명의 유효성 검사를 건너뛰는 기능을 비활성화하는 방법에 대해 설명합니다. 이 기능은 모든 응용 프로그램 또는 특정 응용 프로그램에 대해 비활성화할 수 있습니다.|  
|[어셈블리 만들기](../../../docs/framework/app-domains/create-assemblies.md)|단일 파일 어셈블리와 다중 파일 어셈블리에 대해 설명합니다.|  
|[NIB: 방법: 어셈블리 서명 연기(Visual Studio)](http://msdn.microsoft.com/en-us/cab63b7a-591e-4674-b236-d77cd29a79ea)|어셈블리를 만든 후 강력한 이름의 어셈블리에 서명하는 방법에 대해 설명합니다.|  
|[Sn.exe(강력한 이름 도구)](../../../docs/framework/tools/sn-exe-strong-name-tool.md)|강력한 이름의 어셈블리를 만들 수 있도록 지원하는 .NET Framework에 포함된 도구에 대해 설명합니다. 이 도구는 키 관리, 서명 생성 및 서명 확인을 위한 옵션을 제공합니다.|  
|[Al.exe(어셈블리 링커)](../../../docs/framework/tools/al-exe-assembly-linker.md)|모듈 또는 리소스 파일에서 어셈블리 매니페스트가 있는 파일을 생성하는 .NET Framework에 포함된 도구에 대해 설명합니다.|
