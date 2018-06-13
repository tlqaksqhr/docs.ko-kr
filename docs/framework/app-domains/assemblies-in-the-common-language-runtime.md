---
title: 공용 언어 런타임의 어셈블리
ms.date: 03/30/2017
helpviewer_keywords:
- dynamic assemblies
- security [.NET Framework], boundaries
- boundaries of assemblies
- assemblies [.NET Framework], about
- assemblies [.NET Framework], boundaries
- reference scope boundaries
- assemblies [.NET Framework]
- version boundaries
- type boundaries
ms.assetid: 2cfebe19-7436-49f1-bd99-3c4019f0b676
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eefd3773d26fe71741668a9df366f041ba0ae0a4
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32744332"
---
# <a name="assemblies-in-the-common-language-runtime"></a>공용 언어 런타임의 어셈블리
어셈블리는 .NET Framework 응용 프로그램의 문서 블록으로서 배포, 버전 제어, 다시 사용, 활성화 범위 지정 및 보안 권한의 기본 단위를 형성합니다. 어셈블리는 서로 함께 사용되어 논리적 기능 단위를 형성하도록 빌드되는 형식 및 리소스의 컬렉션입니다. 어셈블리는 형식 구현을 인식하는 데 필요한 정보와 함께 공용 언어 런타임을 제공합니다. 런타임에 대해, 형식은 어셈블리 컨텍스트 외부에 존재하지 않습니다.  
  
 어셈블리는 다음 기능을 수행합니다.  
  
-   공용 언어 런타임에서 실행되는 코드가 포함됩니다. PE(이식 가능한 실행) 파일의 MSIL(Microsoft Intermediate Language) 코드는 연관된 어셈블리 매니페스트가 없는 경우 실행되지 않습니다. 각 어셈블리에는 진입점이 하나만 있습니다(즉, `DllMain`, `WinMain` 또는 `Main`).  
  
-   보안 경계를 형성합니다. 어셈블리는 권한이 요청되고 허용되는 단위입니다. 어셈블리에 적용되는 보안 경계에 대한 자세한 내용은 [어셈블리 보안 고려 사항](../../../docs/framework/app-domains/assembly-security-considerations.md)을 참조하세요.  
  
-   형식 경계를 형성합니다. 각 형식의 ID에는 해당 형식이 존재하는 어셈블리의 이름이 포함됩니다. 한 어셈블리의 범위에서 로드된 `MyType`이라는 형식은 다른 어셈블리의 범위에서 로드된 `MyType`이라는 형식과 다릅니다.  
  
-   참조 범위 경계를 형성합니다. 어셈블리의 매니페스트에는 형식을 해석하고 리소스 요청을 만족하는 데 사용되는 어셈블리 메타데이터가 포함되어 있습니다. 이 메타데이터는 어셈블리 외부에 노출되는 형식과 리소스를 지정합니다. 또한 매니페스트는 어셈블리가 종속된 다른 어셈블리를 열거합니다.  
  
-   버전 경계를 형성합니다. 어셈블리는 공용 언어 런타임에서 버전 관리가 가능한 가장 작은 단위입니다. 동일한 어셈블리의 모든 형식과 리소스는 하나의 단위로 버전이 관리됩니다. 어셈블리의 매니페스트는 종속 어셈블리에 대해 지정한 버전 종속성을 설명합니다. 버전 관리에 대한 자세한 내용은 [어셈블리 버전 관리](../../../docs/framework/app-domains/assembly-versioning.md)를 참조하세요.  
  
-   배포 단위를 형성합니다. 응용 프로그램이 시작될 때 응용 프로그램이 처음으로 호출하는 어셈블리만 있어야 합니다. 유틸리티 클래스가 포함된 지역화 리소스 또는 어셈블리 등의 다른 어셈블리는 요청 시 검색할 수 있습니다. 따라서 응용 프로그램이 처음 다운로드될 때 단순함을 유지할 수 있습니다. 어셈블리 배포에 대한 자세한 내용은 [응용 프로그램 배포](../../../docs/framework/deployment/index.md)를 참조하세요.  
  
-   Side-by-Side 실행이 지원되는 단위입니다. 여러 버전의 어셈블리 실행에 대한 자세한 내용은 [어셈블리 및 Side-by-Side 실행](../../../docs/framework/app-domains/assemblies-and-side-by-side-execution.md)을 참조하세요.  
  
 어셈블리는 정적 또는 동적이 될 수 있습니다. 정적 어셈블리에는 .NET Framework 형식(인터페이스 및 클래스)과 어셈블리 리소스(비트맵, JPEG 파일, 리소스 파일 등)가 포함될 수 있습니다. 정적 어셈블리는 PE(이식 가능한 실행) 파일로 디스크에 저장됩니다. .NET Framework를 사용하여, 메모리에서 직접 실행되며 실행 전에 디스크에 저장되지 않는 동적 어셈블리를 만들 수도 있습니다. 동적 어셈블리는 실행된 후에 디스크에 저장할 수 있습니다.  
  
 여러 가지 방법으로 어셈블리를 만들 수 있습니다. 이전에 .dll 또는 .exe 파일을 만들기 위해 사용했던 Visual Studio 등의 개발 도구를 사용할 수 있습니다. [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]에 제공된 도구를 사용하여, 다른 개발 환경에서 만든 모듈이 포함된 어셈블리를 만들 수 있습니다. 또한 <xref:System.Reflection.Emit?displayProperty=nameWithType> 등의 공용 언어 런타임 API를 사용하여 동적 어셈블리를 만들 수도 있습니다.  
  
## <a name="related-topics"></a>관련 항목  
  
|제목|설명|  
|-----------|-----------------|  
|[어셈블리 콘텐츠](../../../docs/framework/app-domains/assembly-contents.md)|어셈블리를 구성하는 요소에 대해 설명합니다.|  
|[어셈블리 매니페스트](../../../docs/framework/app-domains/assembly-manifest.md)|어셈블리 매니페스트의 데이터란 무엇이며 이 데이터가 어셈블리에 저장되는 방법에 대해 설명합니다.|  
|[전역 어셈블리 캐시](../../../docs/framework/app-domains/gac.md)|전역 어셈블리 캐시란 무엇이며 이 캐시가 어셈블리와 함께 사용되는 방법에 대해 설명합니다.|  
|[강력한 이름의 어셈블리](../../../docs/framework/app-domains/strong-named-assemblies.md)|강력한 이름의 어셈블리에 대한 특징을 설명합니다.|  
|[어셈블리 보안 고려 사항](../../../docs/framework/app-domains/assembly-security-considerations.md)|어셈블리에 보안이 사용되는 방법에 대해 설명합니다.|  
|[어셈블리 버전 관리](../../../docs/framework/app-domains/assembly-versioning.md)|.NET Framework 버전 관리 정책에 대한 개요를 제공합니다.|  
|[어셈블리 배치](../../../docs/framework/app-domains/assembly-placement.md)|어셈블리가 배치되는 위치에 대해 설명합니다.|  
|[어셈블리 및 Side-by-Side 실행](../../../docs/framework/app-domains/assemblies-and-side-by-side-execution.md)|여러 버전의 런타임 또는 어셈블리를 동시에 사용하는 방법에 대한 개요를 제공합니다.|  
|[어셈블리를 사용한 프로그래밍](../../../docs/framework/app-domains/programming-with-assemblies.md)|어셈블리를 만들고, 서명하고, 특성을 설정하는 방법에 대해 설명합니다.|  
|[동적 메서드 및 어셈블리 내보내기](../../../docs/framework/reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)|동적 어셈블리를 만드는 방법에 대해 설명합니다.|  
|[런타임에서 어셈블리를 찾는 방법](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)|.NET Framework가 런타임에서 어셈블리 참조를 확인하는 방법에 대해 설명합니다.|  
  
## <a name="reference"></a>참조  
 <xref:System.Reflection.Assembly?displayProperty=nameWithType>
