---
title: "lock 문(C# 참조) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "lock_CSharpKeyword"
  - "lock"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "lock 키워드[C#]"
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
caps.latest.revision: 43
caps.handback.revision: 43
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# lock 문(C# 참조)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`lock` 키워드는 지정된 개체를 상호 배타적으로 잠그고 문을 실행한 다음 잠금을 해제함으로써 문 블록을 임계 영역으로 표시합니다.  다음 예제에서는 포함 된 `lock` 문.  
  
```  
  
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
  
 자세한 내용은 [스레드 동기화](../Topic/Thread%20Synchronization%20\(C%23%20and%20Visual%20Basic\).md)를 참조하십시오.  
  
## 설명  
 `lock` 키워드를 사용하면 다른 스레드가 코드의 임계 영역에 있는 동안에는 특정 스레드가 임계 영역에 들어갈 수 없습니다.  다른 스레드가 잠긴 코드에 들어가려고 할 경우 개체가 해제될 때까지 대기합니다.  
  
 스레딩에 대한 자세한 내용은 [스레딩](../Topic/Threading%20\(C%23%20and%20Visual%20Basic\).md) 단원을 참조하십시오.  
  
 `lock` 키워드는 블록의 시작 부분에서 <xref:System.Threading.Monitor.Enter%2A>를 호출하고 블록의 끝 부분에서 <xref:System.Threading.Monitor.Exit%2A>를 호출합니다.  A <xref:System.Threading.ThreadInterruptedException> 경우 throw 됩니다 <xref:System.Threading.Thread.Interrupt%2A> 인터럽트를 시작 하려고 대기 하는 스레드는 `lock` 문.  
  
 일반적으로 코드에서 제어되지 않는 인스턴스나 `public` 형식은 잠그지 않는 것이 좋습니다.  일반적인 구문 `lock (this)`, `lock (typeof (MyType))` 및 `lock ("myLock")`은 다음과 같이 이 지침을 위반합니다.  
  
-   `lock (this)` \- 해당 인스턴스에 공용으로 액세스할 수 있는 경우 문제가 됩니다.  
  
-   `lock (typeof (MyType))` \- `MyType`에 공용으로 액세스할 수 있는 경우 문제가 됩니다.  
  
-   `lock("myLock")` \- 동일한 문자열을 사용하는 프로세스의 다른 코드가 동일한 잠금을 공유하게 되므로 문제가 됩니다.  
  
 가장 좋은 방법은 `private` 개체를 정의하여 잠그거나 `private static` 개체 변수를 정의하여 모든 인스턴스에 공통된 데이터를 보호하는 것입니다.  
  
 사용할 수 없습니다는  [기다립니다](../../../csharp/language-reference/keywords/await.md) 본문의 키워드는 `lock` 문.  
  
## 예제  
 다음 샘플에서는 C\#에서 잠금 없이 스레드를 사용하는 간단한 방법을 보여 줍니다.  
  
 [!code-cs[csrefKeywordsFixedLock#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_1.cs)]  
  
## 예제  
 다음 샘플에서는 스레드와 `lock`을 사용합니다.  `lock` 문이 있으면 문 블록이 임계 영역이 되고 `balance`는 음수가 되지 않습니다.  
  
 [!code-cs[csrefKeywordsFixedLock#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_2.cs)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## 참고 항목  
 <xref:System.Reflection.MethodImplAttributes>   
 <xref:System.Threading.Mutex>   
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [스레딩](../Topic/Threading%20\(C%23%20and%20Visual%20Basic\).md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [문 키워드](../../../csharp/language-reference/keywords/statement-keywords.md)   
 [Monitor](../Topic/Monitors.md)   
 [Interlocked Operations](../Topic/Interlocked%20Operations.md)   
 [AutoResetEvent](../Topic/AutoResetEvent.md)   
 [스레드 동기화](../Topic/Thread%20Synchronization%20\(C%23%20and%20Visual%20Basic\).md)