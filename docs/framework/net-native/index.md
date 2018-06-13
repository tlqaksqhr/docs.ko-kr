---
title: .NET 네이티브로 앱 컴파일
ms.date: 03/30/2017
helpviewer_keywords:
- native compilation
- .NET and native code
- compilation with .NET Native
- .NET Native
- C# and native compilation
ms.assetid: 47cd5648-9469-4b1d-804c-43cc04384045
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6900bca2bd94f52ea5603c752681163cde52ce19
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2018
ms.locfileid: "34457309"
---
# <a name="compiling-apps-with-net-native"></a>.NET 네이티브로 앱 컴파일
[!INCLUDE[net_native](../../../includes/net-native-md.md)] Visual Studio 2015 및 이상 버전에 포함 된 Windows 앱 빌드 및 배포에 대 한 미리 컴파일 기술입니다. 관리 코드(C# 또는 Visual Basic)로 작성되었으며 .NET Framework 및 Windows 10의 대상을 네이티브 코드로 지정하는 앱의 릴리스 버전을 자동으로 컴파일합니다.  
  
 일반적으로 .NET Framework를 대상으로 하는 앱은 IL(중간 언어)로 컴파일됩니다. 런타임에 JIT(Just-In-Time) 컴파일러가 IL을 네이티브 코드로 변환합니다. 반면 [!INCLUDE[net_native](../../../includes/net-native-md.md)] 에서는 Windows 앱을 네이티브 코드로 직접 컴파일합니다. 이러한 방식이 개발자에게 의미하는 바는 다음과 같습니다.  
  
-   앱 네이티브 코드의 성능을 기능입니다. 일반적으로 성능이 보다 우수 합니다 IL를 처음 컴파일할 되어 다음 JIT 컴파일러에서 네이티브 코드로 컴파일된 코드를 됩니다. 
  
-   C# 또는 Visual Basic에서 프로그래밍을 계속할 수 있습니다.  
  
-   클래스 라이브러리, 자동 메모리 관리, 가비지 수집, 예외 처리 등의 .NET Framework에서 제공하는 리소스를 계속 활용할 수 있습니다.  
  
 앱 사용자에 대해 [!INCLUDE[net_native](../../../includes/net-native-md.md)] 에서 제공하는 이점은 다음과 같습니다.  
  
-   대부분의 응용 프로그램 및 시나리오에 대 한 빠른 실행 시간입니다.
  
-   대부분의 응용 프로그램 및 시나리오에 대 한 빠른 시작 시간입니다. 
  
-   낮은 배포 및 업데이트 비용입니다.  
  
-   응용 프로그램 메모리 사용량을 최적화합니다.  

> [!IMPORTANT]
> 대부분의 앱와 시나리오에 대 한.NET 네이티브에서는 훨씬 빠른 시작 시간 및 IL NGEN 이미지가 컴파일할 응용 프로그램에 비해 뛰어난 성능을 합니다. 그러나 결과가 달라질 수 있습니다. 을 보장 하기 위해 응용 프로그램에서.NET 네이티브의 향상 된 성능 혜택에 비-.NET 네이티브 버전을 앱의 성능을 비교 해야 합니다. 자세한 내용은 참조 [성능 세션 개요](https://docs.microsoft.com/visualstudio/profiling/performance-session-overview)합니다.
 
[!INCLUDE[net_native](../../../includes/net-native-md.md)] 를 사용하는 경우 이처럼 네이티브 코드로의 컴파일이 수행될 뿐 아니라, .NET Framework 앱 빌드 및 실행 방식도 바뀝니다. 특히 다음과 같습니다.  
  
-   미리 컴파일하는 동안 .NET Framework의 필수 부분이 앱에 정적으로 연결됩니다. 따라서 앱이 .NET Framework의 앱 로컬 라이브러리를 사용하여 실행될 수 있으며 컴파일러가 전역 분석을 수행하여 성능을 개선할 수 있습니다. 따라서 .NET Framework를 업데이트한 후에도 앱이 지속적으로 빠르게 시작됩니다.  
  
-   [!INCLUDE[net_native](../../../includes/net-native-md.md)] 런타임은 정적 미리 최적화 되 고 대부분의 경우에 더 우수한 성능을 제공 합니다. 그와 동시에 개발자의 생산성을 높여 주는 핵심 리플렉션 기능도 계속 제공합니다.  
  
-   [!INCLUDE[net_native](../../../includes/net-native-md.md)] 는 정적 미리 컴파일 시나리오용으로 최적화된 C++ 컴파일러와 같은 백 엔드를 사용합니다.  
  
 [!INCLUDE[net_native](../../../includes/net-native-md.md)] 는 아래 표에 나와 있는 것처럼 내부적으로 C++와 같거나 비슷한 도구를 사용하므로 관리 코드 개발자에게 C++의 성능 이점을 제공할 수 있습니다.  
  
||[!INCLUDE[net_native](../../../includes/net-native-md.md)]|C++|  
|-|----------------------------------------------------------------|-----------|  
|라이브러리|.NET Framework + Windows 런타임|Win32 + Windows 런타임|  
|컴파일러|UTC 최적화 컴파일러|UTC 최적화 컴파일러|  
|배포됨|실행 가능 이진 파일|실행 가능 이진 파일(ASM)|  
|런타임|MRT.dll(최소 CLR 런타임)|CRT.dll(C 런타임)|  
  
 Windows 10용 Windows 앱의 경우 앱 패키지(.appx 파일)의 .NET 네이티브 코드 컴파일 이진 파일을 Windows 스토어에 업로드합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 .NET 네이티브 코드 컴파일을 사용한 앱 개발에 대한 자세한 내용은 다음 항목을 참조하세요.  
  
-   [.NET 네이티브 코드 컴파일 시작: 개발자 환경 연습](../../../docs/framework/net-native/getting-started-with-net-native.md)  
  
-   [.NET 네이티브 및 컴파일:](../../../docs/framework/net-native/net-native-and-compilation.md) .NET 네이티브에서 프로젝트를 네이티브 코드로 컴파일하는 방법입니다.  
  
-   [리플렉션 및 .NET 네이티브](../../../docs/framework/net-native/reflection-and-net-native.md)  
  
    -   [리플렉션을 사용하는 API](../../../docs/framework/net-native/apis-that-rely-on-reflection.md)  
  
    -   [리플렉션 API 참조](../../../docs/framework/net-native/net-native-reflection-api-reference.md)  
  
    -   [런타임 지시문(rd.xml) 구성 파일 참조](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
  
-   [Serialization 및 메타데이터](../../../docs/framework/net-native/serialization-and-metadata.md)  
  
-   [Windows 스토어 앱을 .NET 네이티브로 마이그레이션](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md)  
  
-   [.NET 네이티브 일반 문제 해결](../../../docs/framework/net-native/net-native-general-troubleshooting.md)
