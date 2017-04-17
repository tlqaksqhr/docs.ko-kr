---
title: "reentrancy MDA | Microsoft Docs"
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
  - "unmanaged code, debugging"
  - "transitioning threads unmanaged to managed code"
  - "reentrancy MDA"
  - "reentrancy without an orderly transition"
  - "managed debugging assistants (MDAs), reentrancy"
  - "illegal reentrancy"
  - "MDAs (managed debugging assistants), reentrancy"
  - "threading [.NET Framework], managed debugging assistants"
  - "managed code, debugging"
  - "native debugging, MDAs"
ms.assetid: 7240c3f3-7df8-4b03-bbf1-17cdce142d45
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# reentrancy MDA
`reentrancy` MDA\(관리 디버깅 도우미\)는 이전에 관리 코드에서 네이티브 코드로의 전환이 순차적 전환을 통해 수행되지 않은 경우 네이티브 코드에서 관리 코드로 전환하려고 할 때 활성화됩니다.  
  
## 증상  
 네이티브 코드에서 관리 코드로 전환할 때 개체 힙이 손상되거나 다른 심각한 오류가 발생합니다.  
  
 네이티브 코드와 관리 코드 사이에서 양방향으로 전환하는 스레드는 순차적 전환을 수행해야 합니다.  그러나 벡터가 사용된 예외 처리기 같은 운영 체제의 특정 하위 수준 확장성 지점에서는 순차적 전환을 수행하지 않고 관리 코드에서 네이티브 코드로 전환할 수 있습니다.  이러한 전환은 CLR\(공용 언어 런타임\)이 아니라 운영 체제에서 제어합니다.  이러한 확장성 지점 내에서 실행되는 모든 네이티브 코드는 관리 코드로 다시 호출하면 안 됩니다.  
  
## 원인  
 벡터가 사용된 예외 처리기 같은 하위 수준 운영 체제 확장성 지점은 관리 코드를 실행하는 동안 활성화됩니다.  이 확장성 지점을 통해 호출된 응용 프로그램 코드는 다시 관리 코드로 호출하려고 합니다.  
  
 이 문제는 항상 응용 프로그램 코드로 인해 발생합니다.  
  
## 해결  
 이 MDA를 활성화한 스레드에 대한 스택 추적을 검사합니다.  스레드가 관리 코드로 잘못 호출하려고 합니다.  스택 추적에는 이 확장성 지점이 사용하는 응용 프로그램 코드, 이 확장성 지점을 제공하는 운영 체제 코드 및 확장성 지점이 중단한 관리 코드가 포함되어야 합니다.  
  
 예를 들어, 벡터가 사용된 예외 처리기 내부에서 관리 코드를 호출하려고 할 때 활성화되는 MDA가 표시됩니다.  스택에는 운영 체제 예외 처리 코드 및 <xref:System.DivideByZeroException>이나 <xref:System.AccessViolationException> 같은 예외를 트리거하는 일부 관리 코드가 표시됩니다.  
  
 이 예제에서 올바른 해결 방법은 벡터가 사용된 예외 처리기를 비관리 코드에서 완벽하게 구현하는 것입니다.  
  
## 런타임 효과  
 이 MDA는 CLR에 아무런 영향을 주지 않습니다.  
  
## Output  
 MDA는 잘못된 재진입을 시도하고 있음을 보고합니다.  스레드의 스택을 검사하여 이 문제가 발생한 원인과 문제 해결 방법을 확인합니다.  다음은 샘플 출력입니다.  
  
```  
Additional Information: Attempting to call into managed code without   
transitioning out first.  Do not attempt to run managed code inside   
low-level native extensibility points. Managed Debugging Assistant   
'Reentrancy' has detected a problem in 'D:\ConsoleApplication1\  
ConsoleApplication1\bin\Debug\ConsoleApplication1.vshost.exe'.  
```  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <reentrancy />  
  </assistants>  
</mdaConfig>  
```  
  
## 예제  
 다음 코드 예제에서는 <xref:System.AccessViolationException>을 throw합니다.  벡터가 사용된 예외 처리기를 지원하는 Windows 버전에서 이 예외는 관리되는 벡터가 적용된 예외 처리기를 호출합니다.  `reentrancy` MDA가 사용되는 경우 이 MDA는 운영 체제의 벡터가 사용된 예외 처리 지원 코드에서 `MyHandler`를 호출하려고 할 때 활성화됩니다.  
  
```  
using System;  
public delegate int ExceptionHandler(IntPtr ptrExceptionInfo);  
  
public class Reenter   
{  
    public static ExceptionHandler keepAlive;  
  
    [System.Runtime.InteropServices.DllImport("kernel32", ExactSpelling=true,   
        CharSet=System.Runtime.InteropServices.CharSet.Auto)]  
    public static extern IntPtr AddVectoredExceptionHandler(int bFirst,   
        ExceptionHandler handler);  
  
    static int MyHandler(IntPtr ptrExceptionInfo)   
    {  
        // EXCEPTION_CONTINUE_SEARCH  
        return 0;  
    }  
    void Run() {}  
  
    static void Main()   
    {  
        keepAlive = new ExceptionHandler(Reenter.MyHandler);  
        IntPtr ret = AddVectoredExceptionHandler(1, keepAlive);  
        try   
        {  
            // Dispatch on null should AV.  
            Reenter r = null;   
            r.Run();  
        }   
        catch { }  
    }  
}  
```  
  
## 참고 항목  
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)