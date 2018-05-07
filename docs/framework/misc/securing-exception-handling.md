---
title: 예외 처리 보안
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- code security, exception handling
- security [.NET Framework], exception handling
- secure coding, exception handling
- exception handling, security
ms.assetid: 1f3da743-9742-47ff-96e6-d0dd1e9e1c19
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fe978930a9f84e0084f79f5fe585a1ecc3bf4eb2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="securing-exception-handling"></a>예외 처리 보안
Visual c + + 및 Visual Basic에서 스택 추가 필터 식을 전에 실행할 **마지막** 문. **catch** 블록에 연결 된 후 실행 되는 해당 필터는 **마지막** 문. 자세한 내용은 참조 [사용자 필터 예외](../../../docs/standard/exceptions/using-user-filtered-exception-handlers.md)합니다. 이 섹션에서는이 순서에 따른 보안 위험을 검사 합니다. 다음 의사 코드 예제에서는 필터 문 순서를 보여 줍니다 및 **마지막** 문을 실행 합니다.  
  
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
  
 이 코드에서는 다음이 출력 됩니다.  
  
```  
Throw  
Filter  
Finally  
Catch  
```  
  
 필터가 먼저 실행는 **마지막** 문, 여기서 다른 코드를 실행 하는 데 이용 변경 상태를 수행 하면 보안 문제를 유발 될 수 있도록 합니다. 예를 들어:  
  
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
  
 이 의사 코드에서는 임의의 코드를 실행 하기 위해 스택의 상위 필터입니다. 비슷한 영향을 미칠 수 있는 작업의 다른 예제는 임시 일부 보안 검사를 무시 하는 내부 플래그를 설정 하는 다른 id 가장 하거나 스레드와 연결 된 문화권을 변경 합니다. 권장된 솔루션 호출자의 필터 블록에서 스레드 상태에는 코드의 변경 내용을 격리 하는 예외 처리기를 도입 하는 것입니다. 그러나이 예외 처리기 제대로 도입 될 중요 하거나이 문제가 해결 되지 않습니다. 다음 예제에서는 UI 문화권을 전환 하지만 모든 종류의 스레드 상태 변경 마찬가지로 노출 될 수 있습니다.  
  
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
  
 올바른 수정이 경우 기존 래핑하는 **시도**/**마지막** 블록는 **시도**/**catch** 블록입니다. 소개는 **catch throw** 기존 절 **시도**/**마지막** 블록 다음 예제에 표시 된 대로 문제를 해결 되지 않으면 합니다.  
  
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
  
 때문에 문제가 해결 되지 않으면는 **마지막** 하기 전에 문이 실행 되지 않은 `FilterFunc` 컨트롤을 가져옵니다.  
  
 다음 예제는 다음을 통해 문제를 해결는 **마지막** 절이 호출자의 예외 필터 블록에 예외를 제공 하기 전에 실행 됩니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 [보안 코딩 지침](../../../docs/standard/security/secure-coding-guidelines.md)
