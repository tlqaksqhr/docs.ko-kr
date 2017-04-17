---
title: "illegalPrepareConstrainedRegion MDA | Microsoft Docs"
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
  - "PrepareConstrainedRegions method"
  - "managed debugging assistants (MDAs), illegal PrepareConstrainedRegions"
  - "try/catch exception handling, managed debugging assistants"
  - "IllegalPrepareConstrainedRegions MDA"
  - "MDAs (managed debugging assistants), illegal PrepareConstrainedRegions"
ms.assetid: 2f9b5031-f910-4e01-a196-f89eab313eaf
caps.latest.revision: 15
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 15
---
# illegalPrepareConstrainedRegion MDA
<xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A?displayProperty=fullName> 메서드 호출이 예외 처리기의 `try` 문 바로 앞에 오지 않으면 `illegalPrepareConstrainedRegion` MDA\(관리 디버깅 도우미\)가 활성화됩니다.  이 제한은 MSIL 수준에 해당하는 것이므로 해당 호출과 `try` 사이에 주석과 같은 비코드 생성 소스를 둘 수 있습니다.  
  
## 증상  
 CER\(제약이 있는 실행 영역\)가 그 자체로 처리되지 않고 단순 예외 처리 블록\(`finally` 또는 `catch`\)으로 처리됩니다.  따라서 해당 영역은 메모리 부족 조건 또는 스레드 중단 등의 이벤트에서 실행되지 않습니다.  
  
## 원인  
 CER에 대한 준비 패턴이 제대로 수행되지 않았습니다.  오류가 발생합니다.  `catch`\/`finally`\/`fault`\/`filter` 블록에서 CER를 소개할 때 예외 처리기를 표시하는 데 사용된 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> 메서드 호출은 `try` 문보다 바로 전에 사용되어야 합니다.  
  
## 해결  
 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>에 대한 호출이 `try` `` 문 바로 앞에 오도록 합니다.  
  
## 런타임 효과  
 이 MDA는 CLR에 아무런 영향을 주지 않습니다.  
  
## Output  
 MDA는 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> 메서드를 호출하는 메서드의 이름, MSIL 오프셋, 호출이 try 블록의 시작 부분 바로 앞에 오지 않음을 나타내는 메시지 등을 표시합니다.  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <illegalPrepareConstrainedRegion/>  
  </assistants>  
</mdaConfig>  
```  
  
## 예제  
 다음 코드 예제는 이 MDA가 활성화되도록 하는 패턴을 보여 줍니다.  
  
```  
void MethodWithInvalidPCR()  
{  
    RuntimeHelpers.PrepareConstrainedRegions();  
    Object o = new Object();  
    try  
    {  
        …  
    }  
    finally  
    {  
        …  
    }  
}  
```  
  
## 참고 항목  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop 마샬링](../../../docs/framework/interop/interop-marshaling.md)