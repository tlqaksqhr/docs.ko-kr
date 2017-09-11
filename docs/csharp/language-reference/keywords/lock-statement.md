---
title: "lock 문(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- lock_CSharpKeyword
- lock
dev_langs:
- CSharp
helpviewer_keywords:
- lock keyword [C#]
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
caps.latest.revision: 43
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 00dcbb9feec11587265bf61667d91c2c1598065b
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="lock-statement-c-reference"></a><span data-ttu-id="3e59a-102">lock 문(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="3e59a-102">lock Statement (C# Reference)</span></span>
<span data-ttu-id="3e59a-103">`lock` 키워드는 지정된 개체에 대한 상호 배타적 잠금을 얻고 문을 실행한 다음 잠금을 해제하여 문 블록을 임계 영역으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="3e59a-103">The `lock` keyword marks a statement block as a critical section by obtaining the mutual-exclusion lock for a given object, executing a statement, and then releasing the lock.</span></span> <span data-ttu-id="3e59a-104">다음 예제에는 `lock` 문이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e59a-104">The following example includes a `lock` statement.</span></span>  
  
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
  
 <span data-ttu-id="3e59a-105">자세한 내용은 [스레드 동기화](http://msdn.microsoft.com/library/413e1f28-a2c5-4eec-8338-aa43e7982ff4)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3e59a-105">For more information, see [Thread Synchronization](http://msdn.microsoft.com/library/413e1f28-a2c5-4eec-8338-aa43e7982ff4).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e59a-106">주의</span><span class="sxs-lookup"><span data-stu-id="3e59a-106">Remarks</span></span>  
 <span data-ttu-id="3e59a-107">`lock` 키워드는 한 스레드가 임계 영역에 있는 동안 다른 스레드가 코드의 임계 영역에 들어오지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e59a-107">The `lock` keyword ensures that one thread does not enter a critical section of code while another thread is in the critical section.</span></span> <span data-ttu-id="3e59a-108">다른 스레드가 잠긴 코드에 들어오려고 하면 개체가 해제될 때까지 대기 및 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e59a-108">If another thread tries to enter a locked code, it will wait, block, until the object is released.</span></span>  
  
 <span data-ttu-id="3e59a-109">[스레딩](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c) 섹션에서 스레딩에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3e59a-109">The section [Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c) discusses threading.</span></span>  
  
 <span data-ttu-id="3e59a-110">`lock` 키워드는 블록의 시작 부분에서 <xref:System.Threading.Monitor.Enter%2A>를 호출하고 블록의 끝 부분에서 <xref:System.Threading.Monitor.Exit%2A>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="3e59a-110">The `lock` keyword calls <xref:System.Threading.Monitor.Enter%2A> at the start of the block and <xref:System.Threading.Monitor.Exit%2A> at the end of the block.</span></span> <span data-ttu-id="3e59a-111"><xref:System.Threading.Thread.Interrupt%2A>가 `lock` 문의 입력을 기다리는 스레드를 중단하면 <xref:System.Threading.ThreadInterruptedException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e59a-111">A <xref:System.Threading.ThreadInterruptedException> is thrown if <xref:System.Threading.Thread.Interrupt%2A> interrupts a thread that is waiting to enter a `lock` statement.</span></span>  
  
 <span data-ttu-id="3e59a-112">일반적으로 코드 제어를 벗어나서 `public` 형식이나 인스턴스를 잠그지 마세요.</span><span class="sxs-lookup"><span data-stu-id="3e59a-112">In general, avoid locking on a `public` type, or instances beyond your code's control.</span></span> <span data-ttu-id="3e59a-113">일반적인 구문 `lock (this)`, `lock (typeof (MyType))` 및 `lock ("myLock")`은 이 지침을 위반합니다.</span><span class="sxs-lookup"><span data-stu-id="3e59a-113">The common constructs `lock (this)`, `lock (typeof (MyType))`, and `lock ("myLock")` violate this guideline:</span></span>  
  
-   <span data-ttu-id="3e59a-114">인스턴스를 공개적으로 액세스할 수 있는 경우 `lock (this)`에서 문제가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3e59a-114">`lock (this)` is a problem if the instance can be accessed publicly.</span></span>  
  
-   <span data-ttu-id="3e59a-115">`MyType`을 공개적으로 액세스할 수 있는 경우 `lock (typeof (MyType))`에서 문제가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3e59a-115">`lock (typeof (MyType))` is a problem if `MyType` is publicly accessible.</span></span>  
  
-   <span data-ttu-id="3e59a-116">동일한 문자열을 사용하는 프로세스의 다른 코드가 같은 잠금을 공유하기 때문에 `lock("myLock")`에서 문제가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3e59a-116">`lock("myLock")` is a problem because any other code in the process using the same string, will share the same lock.</span></span>  
  
 <span data-ttu-id="3e59a-117">잠글 `private` 개체를 정의하거나, `private static` 개체 변수를 정의하여 모든 인스턴스에 공통된 데이터를 보호하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3e59a-117">Best practice is to define a `private` object to lock on, or a `private static` object variable to protect data common to all instances.</span></span>  
  
 <span data-ttu-id="3e59a-118">`lock` 문의 본문에서 [await](../../../csharp/language-reference/keywords/await.md) 키워드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3e59a-118">You can't use the [await](../../../csharp/language-reference/keywords/await.md) keyword in the body of a `lock` statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e59a-119">예제</span><span class="sxs-lookup"><span data-stu-id="3e59a-119">Example</span></span>  
 <span data-ttu-id="3e59a-120">다음 샘플에서는 C#에서 잠금 없이 스레드를 간단하게 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3e59a-120">The following sample shows a simple use of threads without locking in C#.</span></span>  
  
 <span data-ttu-id="3e59a-121">[!code-cs[csrefKeywordsFixedLock#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="3e59a-121">[!code-cs[csrefKeywordsFixedLock#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e59a-122">예제</span><span class="sxs-lookup"><span data-stu-id="3e59a-122">Example</span></span>  
 <span data-ttu-id="3e59a-123">다음 샘플에서는 스레드 및 `lock`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e59a-123">The following sample uses threads and `lock`.</span></span> <span data-ttu-id="3e59a-124">`lock` 문이 있으면 문 블록은 임계 영역이 되며 `balance`가 음수가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e59a-124">As long as the `lock` statement is present, the statement block is a critical section and `balance` will never become a negative number.</span></span>  
  
 <span data-ttu-id="3e59a-125">[!code-cs[csrefKeywordsFixedLock#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="3e59a-125">[!code-cs[csrefKeywordsFixedLock#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/lock-statement_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="3e59a-126">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="3e59a-126">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3e59a-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3e59a-127">See Also</span></span>  
 <span data-ttu-id="3e59a-128"><xref:System.Reflection.MethodImplAttributes></span><span class="sxs-lookup"><span data-stu-id="3e59a-128"><xref:System.Reflection.MethodImplAttributes></span></span>   
 <span data-ttu-id="3e59a-129"><xref:System.Threading.Mutex></span><span class="sxs-lookup"><span data-stu-id="3e59a-129"><xref:System.Threading.Mutex></span></span>   
 <span data-ttu-id="3e59a-130">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="3e59a-130">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="3e59a-131">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="3e59a-131">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="3e59a-132">[스레딩](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c) </span><span class="sxs-lookup"><span data-stu-id="3e59a-132">[Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c) </span></span>  
 <span data-ttu-id="3e59a-133">[C# 키워드](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="3e59a-133">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="3e59a-134">[문 키워드](../../../csharp/language-reference/keywords/statement-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="3e59a-134">[Statement Keywords](../../../csharp/language-reference/keywords/statement-keywords.md) </span></span>  
 <span data-ttu-id="3e59a-135">@System.Threading.Monitor</span><span class="sxs-lookup"><span data-stu-id="3e59a-135">@System.Threading.Monitor</span></span>   
 <span data-ttu-id="3e59a-136">[연동 작업](../../../standard/threading/interlocked-operations.md) </span><span class="sxs-lookup"><span data-stu-id="3e59a-136">[Interlocked Operations](../../../standard/threading/interlocked-operations.md) </span></span>  
 <span data-ttu-id="3e59a-137">[AutoResetEvent](../../../standard/threading/autoresetevent.md) </span><span class="sxs-lookup"><span data-stu-id="3e59a-137">[AutoResetEvent](../../../standard/threading/autoresetevent.md) </span></span>  
 [<span data-ttu-id="3e59a-138">스레드 동기화</span><span class="sxs-lookup"><span data-stu-id="3e59a-138">Thread Synchronization</span></span>](http://msdn.microsoft.com/library/413e1f28-a2c5-4eec-8338-aa43e7982ff4)

