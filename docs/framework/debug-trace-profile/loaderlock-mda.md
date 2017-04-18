---
title: "loaderLock MDA | Microsoft Docs"
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
  - "deadlocks [.NET Framework]"
  - "LoaderLock MDA"
  - "MDAs (managed debugging assistants), loader locks"
  - "managed debugging assistants (MDAs), loader locks"
  - "operating system loader locks"
  - "loader locks"
  - "locks, threads"
ms.assetid: 8c10fa02-1b9c-4be5-ab03-451d943ac1ee
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# loaderLock MDA
`loaderLock` MDA\(관리 디버깅 도우미\)는 Microsoft Windows 운영 체제 로더 잠금이 있는 스레드에서 관리 코드를 실행하려는 시도를 감지합니다.  이러한 실행 시도는 교착 상태를 초래할 수 있고 운영 체제 로더에 의해 초기화되기 전에 DLL을 사용할 수 있기 때문에 올바르지 않은 작업입니다.  
  
## 증상  
 운영 체제의 로더 잠금 내에서 코드를 실행하는 데 가장 일반적인 오류는 로더 잠금을 필요로 하는 다른 Win32 함수를 호출하려고 할 때 스레드가 교착 상태가 되는 것입니다.  이러한 함수의 예로는 `LoadLibrary`, `GetProcAddress`, `FreeLibrary` 및 `GetModuleHandle`이 있습니다.  응용 프로그램에서는 이러한 함수를 직접 호출하지 않을 수 있으며 CLR\(공용 언어 런타임\)에서는 <xref:System.Reflection.Assembly.Load%2A> 같은 더 높은 수준 호출의 결과나 플랫폼 호출 메서드에 대한 첫 호출로 이러한 함수를 호출할 수 있습니다.  
  
 스레드가 다른 스레드의 시작이나 종료를 기다리고 있는 경우에도 교착 상태가 발생할 수 있습니다.  스레드는 실행을 시작하거나 종료할 때 운영 체제의 로더 잠금을 가져와서 이벤트를 영향 받은 DLL에 전달해야 합니다.  
  
 마지막으로 운영 체제의 로더가 DLL을 제대로 초기화하기 전에 호출이 DLL에 전달될 수도 있습니다.  교착 상태와 관련된 모든 스레드 스택을 검사하여 진단할 수 있는 교착 상태 오류와 달리 이 MDA를 사용하지 않고 초기화되지 않은 DLL 사용을 진단하기는 어렵습니다.  
  
## 원인  
 .NET Framework 버전 1.0 또는 1.1에 기본 제공되는 혼합 관리\/비관리 C\+\+ 어셈블리는 특별히 주의하지 않으면 일반적으로 **\/NOENTRY**에 링크하는 것과 같이 로더 잠금 내에서 관리 코드를 실행하려고 합니다.  이러한 문제에 대한 자세한 내용은 MSDN Library의 "Mixed DLL Loading Problem"을 참조하십시오.  
  
 .NET Framework 버전 2.0에 기본 제공되는 혼합 관리\/비관리 C\+\+ 어셈블리는 이러한 문제가 발생할 가능성이 더 적으며 운영 체제 규칙을 위반한 비관리 DLL을 사용하는 응용 프로그램과 동일하게 위험이 감소합니다.  예를 들어, 비관리 DLL의 `DllMain` 진입점에서 `CoCreateInstance`를 호출하여 COM에 노출된 관리 개체를 가져오면 결과적으로 로더 잠금 내에서 관리 코드가 실행되려고 합니다.  .NET Framework 버전 2.0 이상에서 로더 잠금 문제에 대한 자세한 내용은 [혼합형 어셈블리 초기화](../Topic/Initialization%20of%20Mixed%20Assemblies.md)를 참조하십시오.  
  
## 해결  
 Visual C\+\+ .NET 2002 및 Visual C\+\+ .NET 2003에서 `/clr` 컴파일러 옵션을 사용하여 컴파일한 DLL을 로드할 때 명확하지 않은 교착 상태에 빠질 수 있습니다. 이 문제를 혼합 DLL 로드 또는 로더 잠금 문제라고 합니다.  Visual C\+\+ 2005 이상에서는 혼합형 DLL 로드 프로세스의 불명확한 요소가 대부분 제거되었습니다.  그러나 일부 시나리오에서는 명확한 로더 잠금 문제가 발생할 수 있습니다.  나머지 로더 잠금 문제의 원인과 해결에 대한 자세한 내용은 [혼합형 어셈블리 초기화](../Topic/Initialization%20of%20Mixed%20Assemblies.md)를 참조하십시오.  이 항목에서 로더 잠금 문제가 식별되지 않는 경우 스레드 스택을 검사하여 로더 잠금이 발생하는 이유와 문제 해결 방법을 확인해야 합니다.  이 MDA를 활성화한 스레드에 대한 스택 추적을 봅니다.  스레드는 운영 체제의 로더 잠금을 보유하는 동안 관리 코드를 잘못 호출하려고 합니다.  DLL의 `DllMain` 또는 스택의 동등한 진입점이 표시될 수 있습니다.  해당 진입점 내부에서 잘못 수행할 수 있는 작업에 대한 운영 체제 규칙에는 많은 제한이 따릅니다.  이러한 규칙은 임의의 관리되는 실행을 방해합니다.  
  
## 런타임 효과  
 일반적으로 프로세스 내의 여러 스레드는 교착 상태가 됩니다.  해당 스레드 중 하나는 가비지 수집을 수행하는 스레드일 수 있으므로 이 교착 상태는 전체 프로세스에 큰 영향을 줄 수 있습니다.  또한 운영 체제 로더 잠금을 필요로 하는 어셈블리나 DLL의 로드와 언로드 또는 스레드 중지와 같은 추가 작업을 수행하지 못하게 합니다.  
  
 드물기는 하지만 초기화하기 전에 호출된 DLL에서 액세스 위반이나 비슷한 문제를 트리거할 수도 있습니다.  
  
## Output  
 이 MDA는 잘못된 관리 실행이 시도되고 있음을 보고합니다.  스레드 스택을 검사하여 로더 잠금이 발생하는 이유와 문제 해결 방법을 확인해야 합니다.  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <loaderLock/>  
  </assistants>  
</mdaConfig>  
```  
  
## 참고 항목  
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)