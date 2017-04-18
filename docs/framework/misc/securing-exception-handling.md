---
title: "예외 처리 보안 | Microsoft Docs"
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
  - "코드 보안, 예외 처리"
  - "예외 처리, 보안"
  - "보안 코딩, 예외 처리"
  - "보안[.NET Framework], 예외 처리"
ms.assetid: 1f3da743-9742-47ff-96e6-d0dd1e9e1c19
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 10
---
# 예외 처리 보안
Visual C\+\+ 및 Visual Basic에서는 스택의 위쪽에 있는 필터 식이 **finally** 문보다 먼저 실행됩니다.  이 필터와 관련된 **catch** 블록은 **finally** 문 다음에 실행됩니다.  자세한 내용은 [사용자 필터 예외 사용](../../../docs/standard/exceptions/using-user-filtered-exception-handlers.md)을 참조하십시오.  이 단원에서는 이 실행 순서와 관련된 보안 문제에 대해 설명합니다.  다음 의사 코드 예제에서는 필터 문과 **finally** 문이 실행되는 순서를 보여 줍니다.  
  
```cpp  
void Main()   
{  
    try   
    {  
        Sub();  
    }   
    except (Filter())   
    {  
        Console.WriteLine("catch");  
    }  
}  
bool Filter () {  
    Console.WriteLine("filter");  
    return true;  
}  
void Sub()   
{  
    try   
    {  
        Console.WriteLine("throw");  
        throw new Exception();  
    }   
    finally   
    {  
        Console.WriteLine("finally");  
    }  
}                        
```  
  
 이 코드에서는 다음이 출력됩니다.  
  
```  
Throw  
Filter  
Finally  
Catch  
```  
  
 필터가 **finally** 문보다 먼저 실행되므로 다른 코드를 실행하는 데 이용될 수 있는 위치에서 상태를 변경하는 작업을 수행하면 보안 문제가 발생할 수 있습니다.  예를 들면 다음과 같습니다.  
  
```cpp  
try   
{  
    Alter_Security_State();  
    // This means changing anything (state variables,  
    // switching unmanaged context, impersonation, and   
    // so on) that could be exploited if malicious   
    // code ran before state is restored.  
    Do_some_work();  
}   
finally   
{  
    Restore_Security_State();  
    // This simply restores the state change above.  
}  
```  
  
 이 의사 코드에서는 스택 위쪽의 필터가 임의의 코드를 실행할 수 있습니다.  비슷한 결과를 생성하는 다른 작업의 예로는 다른 ID를 임시로 가장하거나 보안 검사를 우회하는 내부 플래그를 설정하거나 스레드와 관련된 culture를 변경하는 것이 있습니다.  권장되는 해결 방법은 스레드 상태에 대한 코드의 변경 사항을 호출자의 필터 블록과 격리하기 위해 예외 처리기를 사용하는 것입니다.  그러나 예외 처리기를 올바르게 사용하지 않으면 이 문제가 해결되지 않습니다.  다음 예제에서는 UI culture를 전환시키지만 모든 유형의 스레드 상태 변경은 마찬가지로 노출될 수 있습니다.  
  
```cpp  
YourObject.YourMethod()  
{  
   CultureInfo saveCulture = Thread.CurrentThread.CurrentUICulture;  
   try {  
      Thread.CurrentThread.CurrentUICulture = new CultureInfo("de-DE");  
      // Do something that throws an exception.  
}  
   finally {  
      Thread.CurrentThread.CurrentUICulture = saveCulture;  
   }  
}  
  
```  
  
```vb  
Public Class UserCode  
   Public Shared Sub Main()  
      Try  
         Dim obj As YourObject = new YourObject  
         obj.YourMethod()  
      Catch e As Exception When FilterFunc  
         Console.WriteLine("An error occurred: '{0}'", e)  
         Console.WriteLine("Current Culture: {0}",   
Thread.CurrentThread.CurrentUICulture)  
      End Try  
   End Sub  
  
   Public Function FilterFunc As Boolean  
      Console.WriteLine("Current Culture: {0}", Thread.CurrentThread.CurrentUICulture)  
      Return True  
   End Sub  
  
End Class  
```  
  
 이 경우 올바른 해결 방법은 **try**\/**catch** 블록에서 기존의 **try**\/**finally** 블록을 래핑하는 것입니다.  다음 예제에서 볼 수 있는 것처럼 **catch\-throw** 절을 기존의 **try**\/**finally** 블록으로 삽입하는 것만으로는 문제를 해결하지 못합니다.  
  
```cpp  
YourObject.YourMethod()  
{  
    CultureInfo saveCulture = Thread.CurrentThread.CurrentUICulture;  
  
    try   
    {  
        Thread.CurrentThread.CurrentUICulture = new CultureInfo("de-DE");  
        // Do something that throws an exception.  
    }  
    catch { throw; }  
    finally   
    {  
        Thread.CurrentThread.CurrentUICulture = saveCulture;  
    }  
}  
```  
  
 이 예제에서는 `FilterFunc`가 제어권을 얻기 전에 **finally** 문이 실행되지 않았기 때문에 문제를 해결하지 못합니다.  
  
 다음 예제에서는 호출자의 예외 필터 블록에 예외를 제공하기 전에 **finally** 절이 실행되도록 함으로써 문제를 해결합니다.  
  
```cpp  
YourObject.YourMethod()  
{  
    CultureInfo saveCulture = Thread.CurrentThread.CurrentUICulture;  
    try    
    {  
        try   
        {  
            Thread.CurrentThread.CurrentUICulture = new CultureInfo("de-DE");  
            // Do something that throws an exception.  
        }  
        finally   
        {  
            Thread.CurrentThread.CurrentUICulture = saveCulture;  
        }  
    }  
    catch { throw; }  
}  
```  
  
## 참고 항목  
 [보안 코딩 지침](../../../docs/standard/security/secure-coding-guidelines.md)