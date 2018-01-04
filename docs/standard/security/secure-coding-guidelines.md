---
title: "보안 코딩 지침"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managed wrapper to native code implementation
- secure coding
- reusable components
- library code that exposes protected resources
- code, security
- code security
- secure coding, options
- components [.NET Framework], security
- code security, options
- security-neutral code
- security [.NET Framework], coding guidelines
ms.assetid: 4f882d94-262b-4494-b0a6-ba9ba1f5f177
caps.latest.revision: "20"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3e75f3c74c5966ce5ce22b23f7ba179e903d37aa
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="secure-coding-guidelines"></a>보안 코딩 지침
정보 기반 보안 및 코드 액세스 보안은 보안 구현을 위한 매우 강력하고 명시적인 메커니즘을 제공합니다. 대부분의 응용 프로그램 코드는 .NET Framework에서 구현하는 인프라를 간편하게 사용할 수 있습니다. 경우에 따라, 보안 시스템을 확장하거나 새로운 임시 메서드를 사용하여 빌드되는 추가적인 응용 프로그램 관련 보안이 필요합니다.  
  
 .NET Framework에서 적용한 권한 및 기타 적용을 코드에 사용하여 악성 코드가 중요한 정보를 도용하거나 원하지 않는 작업을 수행하지 않도록 방어해야 합니다. 또한 신뢰할 수 있는 코드를 사용하여 예상되는 모든 시나리오에서 보안과 유용성 간의 균형을 맞춰야 합니다.  
  
 이 개요에서는 보안 시스템에서 사용하기 위해 코드를 설계하는 여러 가지 방법에 대해 설명합니다.  
  
## <a name="securing-resource-access"></a>리소스 액세스 보안  
 코드를 설계하고 작성하는 경우, 특히 출처를 알 수 없는 코드를 사용하거나 호출하는 경우 코드에 부여된 리소스 액세스 권한을 보호하고 제한해야 합니다. 따라서 코드의 보안을 유지하도록 다음과 같은 기술을 염두에 둡니다.  
  
-   CAS(코드 액세스 보안) 사용 안 함  
  
-   부분적으로 신뢰할 수 있는 코드 사용 안 함  
  
-   .NET Remoting 사용 안 함  
  
-   DCOM(분산 구성 요소 개체 모델) 사용 안 함  
  
-   이진 포맷터 사용 안 함  
  
 코드 액세스 보안 및 보안 투명 코드는 부분적으로 신뢰할 수 있는 코드의 보안 경계로 지원되지 않게 됩니다. 대체 보안 조치를 적용하지 않고 출처를 알 수 없는 코드를 로드 및 실행하지 않는 것이 좋습니다. 대체 보안 조치는 다음과 같습니다.  
  
-   가상화  
  
-   AppContainers  
  
-   OS(운영 체제) 사용자 및 사용 권한  
  
-   Hyper-V 컨테이너  
  
## <a name="security-neutral-code"></a>보안 중립 코드  
 보안 중립 코드는 보안 시스템에서 명시적인 작업을 수행하는 것이 없습니다. 단순히 코드에 부여되는 권한을 실행합니다. 보호되는 작업(예: 파일 사용, 네트워킹 등)과 관련된 보안 예외를 catch하지 못하는 응용 프로그램은 처리되지 않은 예외를 발생시킬 수 있지만, 보안 중립 코드는 .NET Framework 보안 기술의 이점을 활용할 수 있습니다.  
  
 보안 중립 라이브러리에는 사용자가 파악해야 하는 특징이 있습니다. 라이브러리가 파일을 사용하거나 비관리 코드를 호출하는 API 요소를 제공한다고 가정해 보겠습니다. 코드에 해당 권한이 없으면 예상대로 실행되지 않습니다. 하지만 코드에 권한이 있더라도 이 코드를 호출하는 모든 응용 프로그램이 작동하려면 동일한 권한이 있어야 합니다. 호출 코드에 적합 한 권한 없는 경우는 <xref:System.Security.SecurityException> 코드 액세스 보안 스택 워크의 결과로 나타납니다.  
  
## <a name="application-code-that-is-not-a-reusable-component"></a>재사용 가능한 구성 요소가 아닌 응용 프로그램 코드  
 사용하는 코드가 다른 코드에서 호출되지 않는 응용 프로그램에 속하는 경우 보안은 단순하며 특수 코딩이 필요하지 않을 수 있습니다. 하지만 악성 코드는 해당 코드를 호출할 수 있습니다. 코드 액세스 보안으로 악성 코드가 리소스에 액세스하는 것을 방지할 수 있지만, 이러한 코드는 중요한 정보가 들어 있을 수 있는 필드 또는 속성의 값을 판독할 수 있습니다.  
  
 또한 해당 코드가 인터넷 또는 기타 신뢰할 수 없는 소스로부터의 사용자 입력을 허용하는 경우에는 악의적인 입력에 주의해야 합니다.  
  
## <a name="managed-wrapper-to-native-code-implementation"></a>네이티브 코드 구현에 대한 관리되는 래퍼  
 일반적으로 이 시나리오에서는 네이티브 코드에서 관리 코드에 사용 가능하게 하려는 몇 가지 유용한 기능을 구현합니다. 관리되는 래퍼는 플랫폼 호출 또는 COM interop를 사용하여 쉽게 작성할 수 있습니다. 하지만 이 작업을 성공적으로 수행하려면 래퍼 호출자에게 비관리 코드 권한이 있어야 합니다. 즉, 기본 정책에 따라 인트라넷 또는 인터넷에서 다운로드되는 코드는 래퍼와 작동되지 않습니다.  
  
 이러한 래퍼를 사용하는 모든 응용 프로그램에 비관리 코드 권한을 부여하는 대신, 래퍼 코드에만 권한을 부여하는 것이 좋습니다. 기본 기능이 리소스를 노출하지 않으며 구현도 안전할 경우에는, 래퍼는 모든 코드가 이를 통해 호출할 수 있도록 해당 권한을 어셜션하기만 하면 됩니다. 리소스가 포함되어 있으면, 보안 코딩은 다음 섹션에 설명된 라이브러리 코드의 경우와 동일해야 합니다. 래퍼는 호출자를 이러한 리소스에 노출할 가능성이 있기 때문에, 네이티브 코드가 안전한지 신중하게 확인해야 하며 이는 래퍼의 책임입니다.  
  
## <a name="library-code-that-exposes-protected-resources"></a>보호되는 리소스를 노출하는 라이브러리 코드  
 이 보안 코딩 방식은 가장 강력하지만 잘못 수행할 경우 위험할 수 있습니다. .NET Framework의 클래스가 사용하는 리소스에 대해 권한을 적용하는 것과 마찬가지로, 라이브러리는 다른 방법으로는 사용할 수 없는 특정 리소스에 액세스하기 위해 다른 코드의 인터페이스 역할을 합니다. 리소스를 노출할 경우, 먼저 코드는 리소스에 적절한 권한을 요구해야 합니다(즉, 보안 검사를 수행해야 함). 그런 다음 실제 작업을 수행할 수 있도록 해당 권한을 어설션합니다.  
  
## <a name="related-topics"></a>관련 항목  
  
|제목|설명|  
|-----------|-----------------|  
|[상태 데이터 보안](../../../docs/standard/security/securing-state-data.md)|전용 멤버를 보호하는 방법을 설명합니다.|  
|[보안 및 사용자 입력](../../../docs/standard/security/security-and-user-input.md)|사용자 입력을 허용하는 응용 프로그램에 대한 보안 문제를 설명합니다.|  
|[보안 및 경합 상태](../../../docs/standard/security/security-and-race-conditions.md)|코드에서 경합 상태를 방지하는 방법을 설명합니다.|  
|[보안 및 빠른 코드 생성](../../../docs/standard/security/security-and-on-the-fly-code-generation.md)|동적 코드를 생성하는 응용 프로그램에 대한 보안 문제를 설명합니다.|  
|[역할 기반 보안](../../../docs/standard/security/role-based-security.md)|.NET Framework 역할 기반 보안을 자세히 설명하고 코드에서의 사용 지침을 제공합니다.|
