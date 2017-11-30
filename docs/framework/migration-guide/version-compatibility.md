---
title: ".NET Framework의 버전 호환성"
ms.custom: updateeachrelease
ms.date: 10/17/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
helpviewer_keywords:
- .NET Framework, version compatibility
- .NET Framework 4.5, compatibility with earlier versions
- .NET Framework versions, compatibility
ms.assetid: 2f25e522-456a-48c3-8a53-e5f39275649f
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 166d61339d2b74f378b50ade4b78fd41e9692f76
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="version-compatibility-in-the-net-framework"></a>.NET Framework의 버전 호환성
이전 버전과의 호환성은 특정 버전의 플랫폼용으로 개발된 앱이 해당 플랫폼의 다음 버전에서도 실행되는 것을 의미합니다. .NET Framework에서는 이전 버전과의 호환성을 최대한 지원하려고 합니다. 한 버전의 .NET Framework용으로 작성된 소스 코드는 다음 버전의 .NET Framework에서 컴파일되어야 하며 한 버전의 .NET Framework에서 실행되는 이진 파일은 다음 버전의 .NET Framework에서 동일하게 작동해야 합니다.  
  
<a name="Apps"></a>   
## <a name="version-compatibility-for-apps"></a>앱의 버전 호환성  
 기본적으로 앱은 빌드에 사용된 .NET Framework 버전에서 실행됩니다. 해당 버전이 없고 앱 구성 파일에 지원되는 버전이 정의되지 않은 경우 .NET Framework 초기화 오류가 발생할 수 있습니다. 이 경우 앱을 실행하지 못합니다.  
  
 앱이 실행되는 특정 버전을 정의하려면 하나 이상의 [\<supportedRuntime>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) 요소를 앱의 구성 파일에 추가합니다. 각 `<supportedRuntime>` 요소에는 지원되는 런타임 버전이 나열됩니다. 우선 순위가 가장 높은 버전이 처음에 지정되고 우선 순위가 가장 낮은 버전이 마지막에 지정됩니다.  
  
```xml  
<configuration>  
   <startup>  
      <supportedRuntime version="v2.0.50727" />  
      <supportedRuntime version="v4.0" />  
   </startup>  
</configuration>  
```  
  
 자세한 내용은 [방법: .NET Framework 4 또는 4.x를 지원하도록 앱 구성](../../../docs/framework/migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)을 참조하십시오.  
  
## <a name="version-compatibility-for-components"></a>구성 요소의 버전 호환성  
 앱에서는 실행되는 .NET Framework의 버전을 자체적으로 제어할 수 있지만, 구성 요소는 제어할 수 없습니다. 구성 요소 및 클래스 라이브러리는 특정 앱의 컨텍스트에서 로드되므로 앱이 실행되는 .NET Framework 버전에서 자동으로 실행됩니다.  
  
 이러한 제한 사항 때문에 구성 요소에서 호환성 보장은 특히 중요합니다. .NET Framework 4부터 <xref:System.Runtime.Versioning.ComponentGuaranteesAttribute?displayProperty=nameWithType> 특성을 해당 구성 요소에 적용하여 구성 요소가 여러 버전 간 호환성을 유지해야 하는 수준을 지정할 수 있습니다. 여러 도구에서는 이 특성을 사용하여 이후 버전의 구성 요소에서 호환성 보장을 잠재적으로 위반할 수 있는 가능성을 검색할 수 있습니다.  
  
## <a name="backward-compatibility-and-the-net-framework-45"></a>이전 버전과의 호환성과 .NET Framework 4.5  
 .NET Framework 4.5 및 이후 버전은 이전 버전과 호환성 및 이전 버전의.NET Framework로 빌드된 앱입니다. 즉, 앱 및 이전 버전으로 빌드된 구성 요소는 수정 하지 않아도 작동.NET Framework 4.5 및 이후 버전입니다. 그러나 기본적으로 앱 실행을 개발 된, 공용 언어 런타임 버전에서 되므로 앱이.NET Framework 4.5 이상 버전에서 실행할 수 있도록 구성 파일을 제공 하는 데 할 수 있습니다. 자세한 내용은 이 문서 앞부분의 [앱의 버전 호환성](#Apps) 섹션을 참조하십시오.  
  
 실제 상황에서 .NET Framework의 외견상 중요하지 않은 변경 사항 및 프로그래밍 기술 변경 사항에 의해 이 호환성이 손상될 수 있습니다. 예를 들어 .NET Framework 4.5 성능 향상 기능이 이전 버전에서 발생하지 않은 경합 상태를 발생시킬 수 있습니다. 마찬가지로 .NET Framework 어셈블리에 하드 코드된 경로 사용, 특정 버전의 .NET Framework와 같음 비교 수행, 리플렉션을 사용한 전용 필드 값 가져오기는 이전 버전과 호환되지 않습니다. 또한 각 .NET Framework 버전에는 일부 앱 및 구성 요소의 호환성에 영향을 줄 수 있는 버그 수정 내용 및 보안 관련 변경 사항이 포함되어 있습니다.  
  
 응용 프로그램 또는 구성 요소는.NET Framework 4.5에서 예상한 대로 작동 하지 않는 경우 (의 포인트 릴리스 포함는 [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7, 또는 4.7.1, 다음 검사 목록을 사용 합니다.  
  
-  응용 프로그램 참조를.NET Framework 4.0으로 시작 하는.NET Framework의 모든 버전에서 실행 하려면 개발 되었으면 [.NET Framework의 응용 프로그램 호환성](application-compatibility.md) 대상된.NET Framework 버전 간의 변경 사항 목록을 생성 하려면 및 앱 실행 되는 버전을 지정 합니다.  

- .NET Framework 3.5 응용 프로그램이 있는 경우 참조도 [.NET Framework 4 마이그레이션 문제](../../../docs/framework/migration-guide/net-framework-4-migration-issues.md)합니다.

- .NET Framework 2.0 응용 프로그램을 사용 하는 경우 표시 [.NET Framework 3.5 s p 1의 변경 내용을](http://go.microsoft.com/fwlink/?LinkId=186989)합니다.

- .NET Framework 1.1 앱이 있는 경우 표시 [.NET Framework 2.0에서 변경 내용을](http://go.microsoft.com/fwlink/?LinkID=125263)합니다.  
  
-   코드를 다시 컴파일하거나 기존 소스 코드 버전에서.NET Framework 4.5 또는 해당 포인트에서 실행 되도록 하는 경우 또는 새 버전의 응용 프로그램 또는 대상으로 하는 구성 요소를 개발 하는 경우는 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 기존 소스 코드 기반의 검사에서 해당 포인트 릴리스 또는 [ 클래스 라이브러리에서 사용 되지 않는 기능](../../../docs/framework/whats-new/whats-obsolete.md) 에 대 한 형식 및 멤버에 사용 되 고 설명 된 해결 방법을 적용 합니다. 이전에 컴파일된 코드는 사용되지 않는 것으로 표시된 형식과 멤버에 대해 계속해서 실행됩니다.  
  
-   [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]가 변경되어 앱이 깨지는 것으로 확인된 경우 [런타임 설정 스키마](../../../docs/framework/configure-apps/file-schema/runtime/index.md)에서 앱 구성 파일의 런타임 설정을 사용하여 이전 동작을 복원할 수 있는지 여부를 확인합니다.  
  
-   문서화되지 않은 문제가 발생한 경우 [Microsoft Connect](http://go.microsoft.com/fwlink/?LinkID=154815)에 버그를 등록하고 해당 버그 번호로 [netfxcf@microsoft.com](mailto:netfxcf@microsoft.com)에 문의하십시오.  
  
## <a name="compatibility-and-side-by-side-execution"></a>호환성 및 Side-By-Side 실행  
 문제에 대한 적합한 해결 방법을 찾지 못한 경우 .NET Framework 4.5(또는 해당 포인트 릴리스 중 하나)가 버전 1.1, 2.0 및 3.5와 side-by-side 실행된다는 것과 버전 4.5는 버전 4를 대체하는 내부 업데이트임을 기억하십시오. 버전 1.1, 2.0 및 3.5를 대상으로 하는 앱의 경우 대상 컴퓨터에 적절한 .NET Framework 버전을 설치하여 앱을 가장 적합한 환경에서 실행할 수 있습니다. Side-by-Side 실행에 대한 자세한 내용은 [Side-by-Side 실행](../../../docs/framework/deployment/side-by-side-execution.md)을 참조하십시오.  
  
## <a name="see-also"></a>참고 항목  
 [새로운 기능](../../../docs/framework/whats-new/index.md)  
 [클래스 라이브러리의 사용되지 않는 기능](../../../docs/framework/whats-new/whats-obsolete.md)  
 [응용 프로그램 호환성](../../../docs/framework/migration-guide/application-compatibility.md)  
 [Microsoft .NET Framework 지원 수명 주기 정책](http://go.microsoft.com/fwlink/p/?LinkId=248212)  
 [.NET Framework 4 마이그레이션 문제](../../../docs/framework/migration-guide/net-framework-4-migration-issues.md)
