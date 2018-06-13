---
title: lock 문(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- lock_CSharpKeyword
- lock
helpviewer_keywords:
- lock keyword [C#]
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
ms.openlocfilehash: 2ce870e8caa67d780ce603a6f1dbcc7cd303b842
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33274221"
---
# <a name="lock-statement-c-reference"></a>lock 문(C# 참조)
`lock` 키워드는 지정된 개체에 대한 상호 배타적 잠금을 얻고 문을 실행한 다음 잠금을 해제하여 문 블록을 임계 영역으로 표시합니다. 다음 예제에는 `lock` 문이 포함되어 있습니다.  
  
```csharp  
class Account  
{  
    decimal balance;  
    private Object thisLock = new Object();  
  
    public void Withdraw(decimal amount)  
    {  
        lock (thisLock)  
        {  
            if (amount > balance)  
            {  
                throw new Exception("Insufficient funds");  
            }  
            balance -= amount;  
        }  
    }  
}  
```  
  
 자세한 내용은 [스레드 동기화](../../programming-guide/concepts/threading/thread-synchronization.md)를 참조하세요.  
  
## <a name="remarks"></a>설명  
 `lock` 키워드는 한 스레드가 임계 영역에 있는 동안 다른 스레드가 코드의 임계 영역에 들어오지 않도록 합니다. 다른 스레드가 잠긴 코드에 들어오려고 하면 개체가 해제될 때까지 대기 및 차단됩니다.  
  
 [스레딩](../../programming-guide/concepts/threading/index.md) 섹션에서 스레딩에 대해 설명합니다.  
  
 `lock` 키워드는 블록의 시작 부분에서 <xref:System.Threading.Monitor.Enter%2A>를 호출하고 블록의 끝 부분에서 <xref:System.Threading.Monitor.Exit%2A>를 호출합니다. <xref:System.Threading.Thread.Interrupt%2A>가 `lock` 문의 입력을 기다리는 스레드를 중단하면 <xref:System.Threading.ThreadInterruptedException>이 throw됩니다.  
  
 일반적으로 코드 제어를 벗어나서 `public` 형식이나 인스턴스를 잠그지 마세요. 일반적인 구문 `lock (this)`, `lock (typeof (MyType))` 및 `lock ("myLock")`은 이 지침을 위반합니다.  
  
-   인스턴스를 공개적으로 액세스할 수 있는 경우 `lock (this)`에서 문제가 발생합니다.  
  
-   `MyType`을 공개적으로 액세스할 수 있는 경우 `lock (typeof (MyType))`에서 문제가 발생합니다.  
  
-   동일한 문자열을 사용하는 프로세스의 다른 코드가 같은 잠금을 공유하기 때문에 `lock("myLock")`에서 문제가 발생합니다.  
  
 잠글 `private` 개체를 정의하거나, `private static` 개체 변수를 정의하여 모든 인스턴스에 공통된 데이터를 보호하는 것이 좋습니다.  
  
 `lock` 문의 본문에서 [await](../../../csharp/language-reference/keywords/await.md) 키워드를 사용할 수 없습니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C#에서 잠금 없이 스레드를 간단하게 사용하는 방법을 보여 줍니다.  
  
 [!code-csharp[csrefKeywordsFixedLock#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_1.cs)]  
  
## <a name="example"></a>예  
 다음 샘플에서는 스레드 및 `lock`을 사용합니다. `lock` 문이 있으면 문 블록은 임계 영역이 되며 `balance`가 음수가 되지 않습니다.  
  
 [!code-csharp[csrefKeywordsFixedLock#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_2.cs)]  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Reflection.MethodImplAttributes>  
 <xref:System.Threading.Mutex>  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [스레딩](../../programming-guide/concepts/threading/index.md)  
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)  
 [문 키워드](../../../csharp/language-reference/keywords/statement-keywords.md)  
 <xref:System.Threading.Monitor>  
 [연동 작업](../../../standard/threading/interlocked-operations.md)  
 [AutoResetEvent](../../../standard/threading/autoresetevent.md)  
 [스레드 동기화](../../programming-guide/concepts/threading/thread-synchronization.md)
