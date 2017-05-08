---
title: "쉽게 디버깅할 수 있도록 이미지 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "이미지[.NET Framework], 디버깅"
  - "디버깅할 실행 파일 이미지"
  - "디버깅[.NET Framework], 실행 파일 이미지"
ms.assetid: 7d90ea7a-150f-4f97-98a7-f9c26541b9a3
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# 쉽게 디버깅할 수 있도록 이미지 만들기
비관리 코드를 컴파일하는 경우, IDE 스위치나 명령줄 옵션을 설정하여 실행 가능 이미지를 디버깅하도록 구성할 수 있습니다.  예를 들어, Visual C\+\+에서 \/**Zi** 명령줄 옵션을 사용하면 디버그 기호 파일\(확장명 .pdb\)을 생성하도록 Visual C\+\+에 요청할 수 있습니다.  마찬가지로, \/**Od** 명령줄 옵션을 사용하면 최적화를 해제하도록 컴파일러에 명령할 수 있습니다.  결과 코드는 더 느리게 실행되므로 쉽게 디버깅을 수행할 수 있습니다.  
  
 .NET Framework에서 관리 코드를 컴파일하는 경우, Visual C\+\+, Visual Basic 및 C\# 등의 컴파일러는 자체의 소스 프로그램을 MSIL\(Microsoft Intermediate Language\)로 컴파일합니다.  MSIL은 실행되기 바로 직전에 네이티브 기계어 코드로 JIT 컴파일됩니다.  비관리 코드의 경우, IDE 스위치나 명령줄 옵션을 설정하여 실행 가능 이미지를 디버깅하도록 구성할 수 있습니다.  또한, 상당히 동일한 방식으로 디버깅을 수행하도록 JIT 컴파일을 구성할 수 있습니다.  
  
 JIT 구성에는 다음과 같은 두 측면이 있습니다.  
  
-   추적 정보를 생성하도록 JIT 컴파일러에 요청할 수 있습니다.  이 경우, 디버거는 MSIL 체인과 이에 상응하는 기계어 코드 체인을 비교할 수 있으며, 지역 변수 및 함수 인수가 저장된 위치를 추적할 수 있습니다.  .NET Framework 버전 2.0에서 JIT 컴파일러는 항상 추적 정보를 생성하기 때문에 이를 요청할 필요가 없습니다.  
  
-   결과 기계어 코드를 최적화하지 않도록 JIT 컴파일러에 요청할 수 있습니다.  
  
 일반적으로, MSIL을 생성하는 컴파일러는 사용자가 지정한 IDE 스위치나 명령줄 옵션\(예: \/**Od**\)에 따라 JIT 컴파일러 옵션을 적절하게 설정합니다.  
  
 일부 경우에 사용자는 기계어 코드를 쉽게 디버깅할 수 있도록 JIT 컴파일러의 동작을 변경하려고 할 것입니다.  예를 들어, 정식 버전 빌드나 컨트롤 최적화를 위해 JIT 추적 정보를 생성하려고 할 수 있습니다.  이 작업을 수행하려면 초기화 파일\(.ini\)을 사용합니다.  
  
 예를 들어, 디버깅하려는 어셈블리의 이름이 MyApp.exe인 경우, 이 어셈블리와 동일한 폴더에 MyApp.ini라는 텍스트 파일을 만듭니다. MyApp.ini 파일에는 다음과 같은 세 줄의 코드가 들어 있습니다.  
  
```  
[.NET Framework Debugging Control]  
GenerateTrackingInfo=1  
AllowOptimize=0  
```  
  
 각 옵션의 값은 0이나 1로 설정될 수 있으며, 존재하지 않는 옵션의 기본값은 0으로 설정될 수 있습니다.  `GenerateTrackingInfo`를 1로 설정하고 `AllowOptimize`를 0으로 설정하면 가장 쉽게 디버깅을 수행할 수 있습니다.  
  
> [!NOTE]
>  .NET Framework 버전 2.0에서는 JIT 컴파일러가 `GenerateTrackingInfo` 값에 관계없이 항상 추적 정보를 생성합니다. 그러나 `AllowOptimize` 값은 여전히 적용됩니다.  [Ngen.exe\(네이티브 이미지 생성기\)](../../../docs/framework/tools/ngen-exe-native-image-generator.md)를 사용하여 최적화 없이 네이티브 이미지를 미리 컴파일할 경우 Ngen.exe가 실행될 때 .ini 파일이 `AllowOptimize=0`인 대상 폴더에 있어야 합니다.  최적화 없이 어셈블리를 미리 컴파일한 경우 Ngen.exe를 다시 실행하여 최적화된 코드를 미리 컴파일하기 전에 NGen.exe **\/uninstall** 옵션을 사용하여 미리 컴파일된 코드를 제거해야 합니다.  .ini 파일이 해당 폴더에 없으면 기본적으로 최적화된 코드가 미리 컴파일됩니다.  
  
> [!NOTE]
>  <xref:System.Diagnostics.DebuggableAttribute?displayProperty=fullName>는 어셈블리의 설정을 제어합니다.  **DebuggableAttribute**에 있는 두 필드에는 JIT 컴파일러의 최적화 수행 및 추적 정보 생성 여부를 설정하는 정보가 들어 있습니다.  .NET Framework 버전 2.0에서는 JIT 컴파일러가 항상 추적 정보를 생성합니다.  
  
> [!NOTE]
>  정식 버전 빌드의 경우 컴파일러는 어떠한 **DebuggableAttribute**도 설정하지 않습니다.  JIT 컴파일러의 기본 동작은 최상의 성능을 발휘하여 기계어 코드를 디버깅하는 것입니다.  JIT 추적을 설정하면 성능이 약간 저하되고, 최적화를 해제하면 성능이 상당히 저하됩니다.  
  
> [!NOTE]
>  **DebuggableAttribute**는 어셈블리 내의 개별 모듈에 적용되는 것이 아니라 전체 어셈블리에 동시에 적용됩니다.  따라서 개발 도구에서는 어셈블리가 이미 만들어진 경우 어셈블리 메타데이터 토큰에 사용자 지정 특성을 연결하고 그렇지 않으면 **System.Runtime.CompilerServices.AssemblyAttributesGoHere**라는 클래스에 사용자 지정 특성을 연결해야 합니다.  그러면 ALink 도구에서는 **DebuggableAttribute** 특성의 수준을 각 모듈 수준에서 해당 특성이 속하는 어셈블리 수준으로 올립니다.  충돌이 발생하는 경우 ALink 동작은 실패할 것입니다.  
  
> [!NOTE]
>  .NET Framework 1.0에서 **\/clr** 및 **\/Zi** 컴파일러 옵션을 지정하면 Microsoft Visual C\+\+ 컴파일러가 **DebuggableAttribute**를 추가합니다.  .NET Framework 1.1에서는 **\/ASSEMBLYDEBUG** 링커 옵션을 사용하거나 코드에 **DebugabbleAttribute**를 수동으로 추가해야 합니다.  
  
## 참고 항목  
 [Debugging, Tracing, and Profiling](../../../docs/framework/debug-trace-profile/index.md)   
 [Enabling JIT\-Attach Debugging](../../../docs/framework/debug-trace-profile/enabling-jit-attach-debugging.md)   
 [Enabling Profiling](http://msdn.microsoft.com/ko-kr/3b669676-f0e0-4ebf-8674-68986dd2020d)