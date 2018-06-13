---
title: .NET Framework의 Side-by-Side 실행
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution
ms.assetid: 649f1342-766b-49e6-a90d-5b019a751e11
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea7a26a5b8ce0f30893e9ca66873ad61f82ff8df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33395163"
---
# <a name="side-by-side-execution-in-the-net-framework"></a>.NET Framework의 Side-by-Side 실행
Side-by-side 실행은 동일한 컴퓨터에서 여러 버전의 응용 프로그램 또는 구성 요소를 실행하는 기능입니다. 동일한 컴퓨터에서 여러 버전의 공용 언어 런타임과, 하나의 런타임 버전을 사용하는 여러 버전의 응용 프로그램 및 구성 요소를 동시에 사용할 수 있습니다.  
  
 다음 그림에서는 동일한 컴퓨터에서 두 가지 다른 버전의 런타임을 사용하는 여러 응용 프로그램을 보여 줍니다. 응용 프로그램 A, B, C는 런타임 버전 1.0을 사용하지만 응용 프로그램 D는 런타임 버전 1.1을 사용합니다.  
  
 ![Side&#45;by&#45;side 실행](../../../docs/framework/deployment/media/simplesbs.gif "simplesbs")  
두 가지 버전의 런타임에 대한 Side-by-Side 실행  
  
 .NET Framework는 공용 언어 런타임과 API 형식이 포함된 어셈블리의 컬렉션으로 구성되어 있습니다. 런타임과 .NET Framework 어셈블리의 버전은 별도로 관리됩니다. 예를 들어, 런타임 버전 4.0은 실제로 버전 4.0.319이며 .NET Framework 어셈블리 버전 1.0은 버전 1.0.3300.0입니다.  
  
 다음 그림에서는 동일한 컴퓨터에서 두 가지 다른 버전의 구성 요소를 사용하는 여러 응용 프로그램을 보여 줍니다. 응용 프로그램 A와 B는 구성 요소 버전 1.0을 사용하지만 응용 프로그램 C는 동일한 구성 요소의 버전 2.0을 사용합니다.  
  
 ![Side&#45;by&#45;side 실행](../../../docs/framework/deployment/media/compsbs.gif "compsbs")  
두 가지 버전의 구성 요소에 대한 Side-by-Side 실행  
  
 Side-by-Side 실행을 사용하면 응용 프로그램이 바인딩하는 구성 요소 버전과 응용 프로그램이 사용하는 런타임 버전을 보다 강력하게 제어할 수 있습니다.  
  
## <a name="benefits-of-side-by-side-execution"></a>Side-by-Side 실행의 장점  
 Windows XP 및 .NET Framework 이전에는 응용 프로그램이 동일한 코드의 호환되지 않는 여러 버전을 구분할 수 없었으므로 DLL 충돌이 발생했습니다. DLL에 포함된 형식 정보는 파일 이름에만 바인딩되었습니다. 응용 프로그램은 DLL에 포함된 형식이 응용 프로그램을 빌드할 때 사용된 형식과 같은지를 알 수 없었습니다. 따라서 새 버전의 구성 요소가 이전 버전을 덮어쓰고 응용 프로그램을 중단시킬 수 있었습니다.  
  
 Side-by-Side 실행 및 .NET Framework는 DLL 충돌을 없애기 위한 다음과 같은 기능을 제공합니다.  
  
-   강력한 이름의 어셈블리  
  
     Side-by-Side 실행은 강력한 이름의 어셈블리를 사용하여 형식 정보를 특정 버전의 어셈블리에 바인딩합니다. 이렇게 하면 응용 프로그램이나 구성 요소가 잘못된 버전의 어셈블리에 바인딩되지 않도록 할 수 있습니다. 또한, 강력한 이름의 어셈블리를 사용하면 동일한 컴퓨터에 여러 버전의 파일이 함께 있을 수 있으며 응용 프로그램에서 이러한 파일을 사용할 수 있습니다. 자세한 내용은 [강력한 이름의 어셈블리](../../../docs/framework/app-domains/strong-named-assemblies.md)를 참조하세요.  
  
-   버전 인식 코드 저장소  
  
     .NET Framework에서는 전역 어셈블리 캐시에 버전 인식 코드 저장소를 제공합니다. 전역 어셈블리 캐시는 .NET Framework가 설치된 모든 컴퓨터에 있는 컴퓨터 수준의 코드 캐시입니다. 이 캐시는 버전, 문화권 및 게시자 정보에 따라 어셈블리를 저장하며 여러 버전의 구성 요소와 응용 프로그램을 지원합니다. 자세한 내용은 [전역 어셈블리 캐시](../../../docs/framework/app-domains/gac.md)를 참조하세요.  
  
-   격리.  
  
     .NET Framework를 사용하면 격리 상태로 실행되는 응용 프로그램과 구성 요소를 만들 수 있습니다. 이러한 격리성은 Side-by-Side 실행의 필수 요소입니다. 격리성을 통해 사용 중인 리소스를 인식하고 여러 버전의 응용 프로그램 또는 구성 요소 간에 리소스를 안전하게 공유할 수 있습니다. 또한 버전 고유의 방식으로 파일이 저장됩니다. 격리에 대한 자세한 내용은 [Side-by-Side 실행용 구성 요소를 만들기 위한 지침](../../../docs/framework/deployment/guidelines-for-creating-components-for-side-by-side-execution.md)을 참조하세요.  
  
## <a name="version-compatibility"></a>버전 호환성  
 .NET Framework 버전 1.0과 1.1은 서로 호환되도록 디자인되었습니다. .NET Framework 버전 1.0으로 빌드한 응용 프로그램을 버전 1.1에서 실행하거나 .NET Framework 버전 1.1로 빌드한 응용 프로그램을 버전 1.0에서 실행할 수 있습니다. 그러나 .NET Framework 버전 1.1에 추가된 API 기능은 .NET Framework 버전 1.0에서 작동되지 않습니다. 버전 2.0에서 만든 응용 프로그램은 버전 2.0에서만 실행됩니다. 버전 2.0 응용 프로그램은 버전 1.1 이하에서 실행되지 않습니다.  
  
 .NET Framework 버전은 런타임과 관련 .NET Framework 어셈블리로 구성되는 하나의 단위로 취급됩니다. 이러한 개념을 어셈블리 통합이라고 합니다. 다른 버전의 .NET Framework 어셈블리를 포함하도록 어셈블리 바인딩을 리디렉션할 수 있지만 기본 어셈블리 바인딩을 재정의하는 것은 위험할 수 있으며 배포 전에 엄격한 테스트 과정이 필요합니다.  
  
## <a name="locating-runtime-version-information"></a>런타임 버전 정보 찾기  
 응용 프로그램 또는 구성 요소가 컴파일된 런타임 버전 및 응용 프로그램을 실행하는 데 필요한 런타임 버전에 대한 정보는 두 위치에 저장됩니다. 응용 프로그램 또는 구성 요소를 컴파일하면 컴파일에 사용된 런타임 버전에 대한 정보가 관리되는 실행 파일에 저장됩니다. 응용 프로그램 또는 구성 요소에 필요한 런타임 버전에 대한 정보는 응용 프로그램 구성 파일에 저장됩니다.  
  
### <a name="runtime-version-information-in-the-managed-executable"></a>관리되는 실행 파일의 런타임 버전 정보  
 각 관리되는 응용 프로그램과 구성 요소의 PE(이식 가능한 실행) 파일 헤더에는 빌드 시 사용된 런타임 버전에 대한 정보가 포함됩니다. 공용 언어 런타임은 이 정보를 사용하여 응용 프로그램을 실행하는 데 필요할 가능성이 가장 큰 런타임 버전을 확인합니다.  
  
### <a name="runtime-version-information-in-the-application-configuration-file"></a>응용 프로그램 구성 파일의 런타임 버전 정보  
 PE 파일 헤더의 정보 외에도 런타임 버전 정보를 제공하는 응용 프로그램 구성 파일을 사용하여 응용 프로그램을 배포할 수 있습니다. 응용 프로그램 구성 파일은 응용 프로그램과 함께 제공되는, 응용 프로그램 개발자가 만든 XML 기반 파일입니다. [\<startup> 섹션](../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)의 [\<requiredRuntime> 요소](../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)(이 파일에 있는 경우)는 응용 프로그램이 지원하는 구성 요소 버전 및 런타임 버전을 지정합니다. 다양한 런타임 버전과 응용 프로그램 간의 호환성을 테스트하는 데 이 파일을 사용할 수도 있습니다.  
  
 COM 및 COM + 응용 프로그램을 비롯한 비관리 코드에는 런타임에서 관리 코드와 상호 작용하는 데 사용하는 응용 프로그램 구성 파일이 포함될 수 있습니다. 응용 프로그램 구성 파일은 COM을 통해 활성화하는 모든 관리 코드에 영향을 줍니다. 파일에서 지원하는 런타임 버전 및 어셈블리 리디렉션을 지정할 수 있습니다. 기본적으로 관리 코드를 호출하는 COM interop 응용 프로그램은 컴퓨터에 설치된 최신 버전의 런타임을 사용합니다.  
  
 응용 프로그램 구성 파일에 대한 자세한 내용은 [앱 구성](../../../docs/framework/configure-apps/index.md)을 참조하세요.  
  
## <a name="determining-which-version-of-the-runtime-to-load"></a>로드할 런타임 버전 결정  
 공용 언어 런타임은 다음 정보를 사용하여 응용 프로그램을 위해 로드할 런타임 버전을 확인합니다.  
  
-   사용할 수 있는 런타임 버전  
  
-   응용 프로그램에서 지원하는 런타임 버전  
  
### <a name="supported-runtime-versions"></a>지원되는 런타임 버전  
 런타임은 응용 프로그램 구성 파일 및 PE(이식 가능한 실행 ) 파일 헤더를 사용하여 응용 프로그램이 지원하는 런타임 버전을 확인합니다. 응용 프로그램 구성 파일이 없으면 런타임은 해당 버전을 사용할 수 있는 경우 응용 프로그램의 PE 파일 헤더에 지정된 런타임 버전을 로드합니다.  
  
 응용 프로그램 구성 파일이 있으면 런타임은 다음 프로세스의 결과에 따라 로드할 적절한 런타임 버전을 결정합니다.  
  
1.  런타임이 응용 프로그램 구성 파일에서 [\<supportedRuntime>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) 요소를 검사합니다. **\<supportedRuntime>** 요소에 지정되어 있는 지원되는 런타임 버전이 하나 이상 있으면 런타임은 첫 번째 **\<supportedRuntime>** 요소에서 지정하는 런타임 버전을 로드합니다. 이 버전을 사용할 수 없으면 런타임은 다음 **\<supportedRuntime>** 요소를 확인하고 지정된 런타임 버전을 로드하려고 시도합니다. 이 런타임 버전을 사용할 수 없으면 그다음 **\<supportedRuntime>** 요소를 확인합니다. 지원되는 런타임 버전을 사용할 수 없으면 런타임에서 런타임 버전을 로드하지 못하고 사용자에게 메시지를 표시합니다(3단계 참조).  
  
2.  런타임이 응용 프로그램 실행 파일의 PE 파일 헤더를 읽습니다. PE 파일 헤더에 지정된 런타임 버전을 사용할 수 있으면 런타임에서 해당 버전을 로드합니다. 지정된 런타임 버전을 사용할 수 없으면 런타임이 Microsoft에서 PE 헤더의 런타임 버전과 호환되는 것으로 확인된 런타임 버전을 검색합니다. 해당 버전이 없으면 프로세스가 3단계로 넘어갑니다.  
  
3.  런타임이 응용 프로그램에서 지원하는 런타임 버전을 사용할 수 없다는 메시지를 표시합니다. 런타임이 로드되지 않습니다.  
  
    > [!NOTE]
    >  HKLM\Software\Microsoft\\.NETFramework 레지스트리 키 아래에 있는 NoGuiFromShim 값을 사용하거나 COMPLUS_NoGuiFromShim 환경 변수를 사용하여 이 메시지가 표시되지 않도록 할 수 있습니다. 예를 들어 무인 설치 또는 Windows 서비스와 같이 일반적으로 사용자와 상호 작용하지 않는 응용 프로그램에 대한 메시지가 표시되지 않도록 할 수 있습니다. 이 메시지가 표시되지 않도록 설정된 경우 런타임은 이벤트 로그에 메시지를 씁니다.  컴퓨터의 모든 응용 프로그램에 대해 이 메시지가 표시되지 않게 하려면 NoGuiFromShim 레지스트리 값을 1로 설정합니다. 또는 특정 사용자 컨텍스트에서 실행되는 응용 프로그램에 대해 메시지가 표시되지 않게 하려면 COMPLUS_NoGuiFromShim 환경 변수를 1로 설정합니다.  
  
> [!NOTE]
>  런타임 버전이 로드된 후 어셈블리 바인딩 리디렉션에서 다른 버전의 개별 .NET Framework 어셈블리가 로드되도록 지정할 수 있습니다. 이러한 바인딩 리디렉션은 리디렉션되는 특정 어셈블리에만 영향을 줍니다.  
  
## <a name="partially-qualified-assembly-names-and-side-by-side-execution"></a>부분적으로 정규화된 어셈블리 이름 및 Side-by-Side 실행  
 Side-by-Side 문제의 잠재적 소스이므로 부분적으로 정규화된 어셈블리 참조는 응용 프로그램 디렉터리 내의 어셈블리에 바인딩하는 데만 사용할 수 있습니다. 부분적으로 정규화된 어셈블리 참조를 코드에서 사용하지 마세요.  
  
 코드에서 부분적으로 정규화된 어셈블리 참조를 줄이려면 응용 프로그램 구성 파일에서 [\<qualifyAssembly>](../../../docs/framework/configure-apps/file-schema/runtime/qualifyassembly-element.md) 요소를 사용하여 코드에 나타나는 부분적으로 정규화된 어셈블리 참조를 완전히 정규화할 수 있습니다. **\<qualifyAssembly>** 요소를 사용하여 부분 참조에 설정되지 않은 필드만 지정합니다. **fullName** 특성에 나열된 어셈블리 ID는 어셈블리 이름을 정규화하는 데 필요한 모든 정보, 즉 어셈블리 이름, 공개 키, 문화권 및 버전을 포함해야 합니다.  
  
 다음 예제에서는 `myAssembly`라는 어셈블리를 정규화하는 응용 프로그램 구성 파일 항목을 보여 줍니다.  
  
```xml  
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">   
<qualifyAssembly partialName="myAssembly"   
fullName="myAssembly,  
      version=1.0.0.0,   
publicKeyToken=...,   
      culture=neutral"/>   
</assemblyBinding>   
```  
  
 어셈블리 로드 문이 `myAssembly`를 참조할 때마다 이러한 구성 파일 설정으로 인해 런타임이 부분적으로 정규화된 `myAssembly` 참조를 정규화된 참조로 자동으로 변환합니다. 예를들어 Assembly.Load("myAssembly")가 Assembly.Load("myAssembly, version=1.0.0.0, publicKeyToken=..., culture=neutral")이 됩니다.  
  
> [!NOTE]
>  **LoadWithPartialName** 메서드를 사용하여 부분적으로 참조된 어셈블리가 전역 어셈블리 캐시에서 로드되지 않도록 하는 공용 언어 런타임 제한을 건너뛸 수 있습니다. 이 메서드는 Side-by-Side 실행에서 쉽게 문제를 발생시킬 수 있으므로 원격 시나리오에서만 사용해야 합니다.  
  
## <a name="related-topics"></a>관련 항목  
  
|제목|설명|  
|-----------|-----------------|  
|[방법: 자동 바인딩 리디렉션 사용 설정 및 해제](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)|특정 버전의 어셈블리에 응용 프로그램을 바인딩하는 방법에 대해 설명합니다.|  
|[어셈블리 바인딩 리디렉션 구성](../../../docs/framework/deployment/configuring-assembly-binding-redirection.md)|.NET Framework 어셈블리의 특정 버전에 대한 어셈블리 바인딩 참조를 리디렉션하는 방법을 설명합니다.|  
|[In-Process Side-by-Side 실행](../../../docs/framework/deployment/in-process-side-by-side-execution.md)|In-Process Side-by-Side 런타임 호스트 활성화를 사용하여 단일 프로세스에서 여러 버전의 CLR을 실행하는 방법을 설명합니다.|  
|[공용 언어 런타임의 어셈블리](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)|어셈블리에 대해 개념적으로 설명합니다.|  
|[응용 프로그램 도메인](../../../docs/framework/app-domains/application-domains.md)|응용 프로그램 도메인에 대해 개념적으로 설명합니다.|  
  
## <a name="reference"></a>참조  
 [\<supportedRuntime> 요소](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)
