---
title: "bindingFailure MDA | Microsoft Docs"
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
  - "binding failure"
  - "binding, failures"
  - "MDAs (managed debugging assistants), binding failures"
  - "assemblies [.NET Framework], binding failures"
  - "managed debugging assistants (MDAs), binding failures"
  - "BindingFailure MDA"
ms.assetid: 26ada5af-175c-4576-931a-9f07fa1723e9
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# bindingFailure MDA
어셈블리를 로드할 수 없으면 `bindingFailure` MDA\(관리 디버깅 도우미\)가 활성화됩니다.  
  
## 증상  
 코드에서 정적 참조를 사용하거나 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> 또는<xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName>과 같은 로더 메서드 중 하나를 사용하여 어셈블리를 로드하려 했습니다.  어셈블리가 로드되지 않았고 <xref:System.IO.FileNotFoundException> 또는 <xref:System.IO.FileLoadException> 예외가 throw되었습니다.  
  
## 원인  
 바인딩 실패는 런타임에서 어셈블리를 로드할 수 없을 때 발생합니다.  바인딩 실패로 인해 다음 중 하나의 결과가 발생할 수 있습니다.  
  
-   CLR\(공용 언어 런타임\)에서 요청된 어셈블리를 찾을 수 없습니다.  이러한 문제는 어셈블리가 설치되지 않았거나 응용 프로그램에서 어셈블리를 찾도록 제대로 구성되지 않은 경우 발생할 수 있습니다.  
  
-   공통 문제 시나리오는 다른 응용 프로그램 도메인으로 형식을 전달하는데, 여기에는 다른 응용 프로그램 도메인에 해당 형식을 포함하는 어셈블리를 로드하기 위해 CLR이 있어야 합니다.  다른 응용 프로그램 도메인이 원래 응용 프로그램 도메인과 다르게 구성된 경우 런타임에서 어셈블리를 로드할 수 없을 수도 있습니다.  예를 들어, 두 응용 프로그램 도메인에 서로 다른 <xref:System.AppDomain.BaseDirectory%2A> 속성 값이 있을 수도 있습니다.  
  
-   요청된 어셈블리가 손상되었거나 어셈블리가 아닙니다.  
  
-   어셈블리를 로드하려는 코드에 어셈블리 로드에 대한 올바른 코드 액세스 보안 권한이 없습니다.  
  
-   사용자 자격 증명이 파일 읽기에 필요한 권한을 제공하지 않습니다.  
  
## 해결  
 첫 번째 단계는 CLR에서 요청된 어셈블리에 바인딩할 수 없는 이유를 확인하는 것입니다.  런타임에서 요청된 어셈블리를 찾을 수 없거나 로드할 수 없는 이유는 원인 섹션에 나열된 몇 가지 시나리오와 같이 여러 가지입니다.  바인딩 실패의 원인을 제거하려면 다음 조치를 수행하는 것이 좋습니다.  
  
-   `bindingFailure` MDA에서 제공된 데이터를 사용하여 원인을 파악합니다.  
  
    -   [Fuslogvw.exe\(어셈블리 바인딩 로그 뷰어\)](../../../docs/framework/tools/fuslogvw-exe-assembly-binding-log-viewer.md)를 실행하여 어셈블리 바인더에서 만든 오류 로그를 읽습니다.  
  
    -   어셈블리가 요청된 위치에 있는지 확인합니다.  <xref:System.Reflection.Assembly.LoadFrom%2A> 메서드 및 <xref:System.Reflection.Assembly.LoadFile%2A> 메서드의 경우에는 요청된 위치를 쉽게 확인할 수 있습니다.  어셈블리 ID를 사용하여 바인딩하는 <xref:System.Reflection.Assembly.Load%2A> 메서드의 경우에는 응용 프로그램 도메인의 <xref:System.AppDomain.BaseDirectory%2A> 속성 프로브 경로 및 전역 어셈블리 캐시에서 해당 ID와 일치하는 어셈블리를 찾아야 합니다.  
  
-   앞에서 확인한 내용에 따라 문제를 해결합니다.  가능한 해결 방법 옵션은 다음과 같습니다.  
  
    -   전역 어셈블리 캐시에 요청된 어셈블리를 설치하고  <xref:System.Reflection.Assembly.Load%2A> 메서드를 호출하여 ID를 기준으로 어셈블리를 로드합니다.  
  
    -   응용 프로그램 디렉터리로 요청된 어셈블리를 복사하고 <xref:System.Reflection.Assembly.Load%2A> 메서드를 호출하여 ID를 기준으로 어셈블리를 로드합니다.  
  
    -   바인딩 실패가 발생한 응용 프로그램 도메인을 다시 구성하여 <xref:System.AppDomain.BaseDirectory%2A> 속성을 변경하거나 개인 검색 경로를 추가하는 방법으로 어셈블리 경로를 포함하도록 합니다.  
  
    -   파일에 대한 액세스 제어 목록을 변경하여 로그온 사용자가 파일을 읽을 수 있도록 합니다.  
  
## 런타임 효과  
 이 MDA는 CLR에 아무런 영향을 주지 않습니다.  바인딩 실패에 대한 데이터만 보고합니다.  
  
## Output  
 MDA는 로드하지 못한 어셈블리를 보고하는데 여기에는 요청된 경로 및\/또는 표시 이름, 바인딩 컨텍스트, 로드가 요청된 응용 프로그램 도메인 및 실패 이유 등이 포함됩니다.  
  
 표시 이름이나 요청된 경로는 해당 데이터를 CLR에 사용할 수 없는 경우에 비워 둘 수 있습니다.  실패한 호출이 <xref:System.Reflection.Assembly.Load%2A> 메서드에 대한 것일 때는 런타임에서 어셈블리에 대한 표시 이름을 확인할 수 없을 수도 있습니다.  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <bindingFailure />  
  </assistants>  
</mdaConfig>  
```  
  
## 예제  
 다음 코드 예제에서는 이 MDA를 활성화할 수 있는 상황을 보여 줍니다.  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.Reflection;  
namespace ConsoleApplication1  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // This call attempts to load a nonexistent assembly.  
            // The call will throw a System.IO.FileNotFound exception  
            // and cause the activation of the bindingFailure MDA   
            // if it is registered.  
            Assembly.Load("NonExistentAssembly");  
        }  
    }  
}  
```  
  
## 참고 항목  
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)