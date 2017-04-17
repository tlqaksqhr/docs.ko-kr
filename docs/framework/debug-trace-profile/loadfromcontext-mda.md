---
title: "loadFromContext MDA | Microsoft Docs"
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
  - "MDAs (managed debugging assistants), LoadFrom context"
  - "managed debugging assistants (MDAs), LoadFrom context"
  - "LoadFrom context"
  - "LoadFromContext MDA"
ms.assetid: a9b14db1-d3a9-4150-a767-dcf3aea0071a
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# loadFromContext MDA
어셈블리가 `LoadFrom` 컨텍스트에 로드되면 `loadFromContext` MDA\(관리 디버깅 도우미\)가 활성화됩니다.  이 상황은 <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName>이나 다른 비슷한 메서드를 호출하면 발생할 수 있습니다.  
  
## 증상  
 일부 로더 메서드를 사용하면 어셈블리가 `LoadFrom` 컨텍스트에 로드될 수 있습니다.  이 컨텍스트를 사용하는 경우 예기치 않은 serialization, 캐스팅 및 종속성 확인 동작이 발생할 수 있습니다.  일반적으로 이 문제를 방지하려면 어셈블리를 `Load` 컨텍스트에 로드하는 것이 좋습니다.  이 MDA 없이 어셈블리가 로드된 컨텍스트를 확인하는 것은 어렵습니다.  
  
## 원인  
 일반적으로 전역 어셈블리 캐시나 <xref:System.AppDomainSetup.ApplicationBase%2A?displayProperty=fullName> 속성과 같은 `Load` 컨텍스트의 외부 경로에서 어셈블리를 로드할 경우 어셈블리가 `LoadFrom` 컨텍스트에 로드되었습니다.  
  
## 해결  
 <xref:System.Reflection.Assembly.LoadFrom%2A> 호출이 더 이상 필요하지 않도록 응용 프로그램을 구성합니다.  이렇게 하려면 다음 기술을 사용할 수 있습니다.  
  
-   전역 어셈블리 캐시에 어셈블리를 설치합니다.  
  
-   어셈블리를 <xref:System.AppDomain>의 <xref:System.AppDomainSetup.ApplicationBase%2A> 디렉터리에 저장합니다.  기본 도메인인 경우 <xref:System.AppDomainSetup.ApplicationBase%2A> 디렉터리에는 프로세스를 시작한 실행 파일이 포함되어 있습니다.  어셈블리를 옮기기가 쉽지 않은 경우 새 <xref:System.AppDomain>을 만들어야 할 수도 있습니다.  
  
-   종속 어셈블리가 실행 파일을 기준으로 자식 디렉터리에 있는 경우 응용 프로그램 구성 파일\(.config\)이나 보조 응용 프로그램 도메인에 검색 경로를 추가합니다.  
  
 각 경우에서 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> 메서드를 사용하도록 코드를 변경할 수 있습니다.  
  
## 런타임 효과  
 이 MDA는 CLR에  영향을 주지 않습니다.  로드 요청의 결과로 사용된 컨텍스트를 보고합니다.  
  
## Output  
 이 MDA는 어셈블리가 `LoadFrom` 컨텍스트에 로드되었음을 보고합니다.  어셈블리의 약식 이름과 경로를 지정합니다.  `LoadFrom` 컨텍스트를 사용하지 않도록 완화 방안도 제안합니다.  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <loadFromContext />  
  </assistants>  
</mdaConfig>  
```  
  
## 예제  
 다음 코드 예제에서는 이 MDA를 활성화할 수 있는 상황을 보여 줍니다.  
  
```  
using System.Reflection;  
namespace ConsoleApplication1  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // The following call caused the LoadFrom context to be used  
            // because the assembly is loaded using LoadFrom and the path is   
            // located outside of the Load context probing path.   
            Assembly.LoadFrom(@"C:\Text\Test.dll");  
        }  
    }  
}  
```  
  
## 참고 항목  
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)