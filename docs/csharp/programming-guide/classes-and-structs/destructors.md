---
title: "종료자(C# 프로그래밍 가이드)"
ms.date: 2017-05-10
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- ~ [C#], in finalizers
- C# language, finalizers
- finalizers [C#]
ms.assetid: 1ae6e46d-a4b1-4a49-abe5-b97f53d9e049
caps.latest.revision: 24
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
ms.openlocfilehash: 43bb7e6488da5eda863e7ad70b25c9bf55bebb52
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="finalizers-c-programming-guide"></a><span data-ttu-id="5c6e3-102">종료자(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="5c6e3-102">Finalizers (C# Programming Guide)</span></span>
<span data-ttu-id="5c6e3-103">종료자는 클래스의 인스턴스를 소멸하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c6e3-103">Finalizers are used to destruct instances of classes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c6e3-104">설명</span><span class="sxs-lookup"><span data-stu-id="5c6e3-104">Remarks</span></span>  
  
-   <span data-ttu-id="5c6e3-105">종료자는 구조체에서 정의할 수 없으며,</span><span class="sxs-lookup"><span data-stu-id="5c6e3-105">Finalizers cannot be defined in structs.</span></span> <span data-ttu-id="5c6e3-106">클래스에서만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c6e3-106">They are only used with classes.</span></span>  
  
-   <span data-ttu-id="5c6e3-107">클래스에는 종료자가 하나만 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c6e3-107">A class can only have one finalizer.</span></span>  
  
-   <span data-ttu-id="5c6e3-108">종료자는 상속하거나 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5c6e3-108">Finalizers cannot be inherited or overloaded.</span></span>  
  
-   <span data-ttu-id="5c6e3-109">종료자를 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5c6e3-109">Finalizers cannot be called.</span></span> <span data-ttu-id="5c6e3-110">자동으로 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c6e3-110">They are invoked automatically.</span></span>  
  
-   <span data-ttu-id="5c6e3-111">종료자는 한정자를 사용하거나 매개 변수를 갖지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5c6e3-111">A finalizer does not take modifiers or have parameters.</span></span>  
  
 <span data-ttu-id="5c6e3-112">예를 들어 다음은 `Car` 클래스에 대한 종료자의 선언입니다.</span><span class="sxs-lookup"><span data-stu-id="5c6e3-112">For example, the following is a declaration of a finalizer for the `Car` class.</span></span>
  
 <span data-ttu-id="5c6e3-113">[!code-cs[csProgGuideObjects#86](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/destructors_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="5c6e3-113">[!code-cs[csProgGuideObjects#86](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/destructors_1.cs)]</span></span>  

<span data-ttu-id="5c6e3-114">다음 예제와 같이 종료자를 식 본문 정의로 구현할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c6e3-114">A finalizer can also be implemented as an expression body definition, as the following example shows.</span></span>

<span data-ttu-id="5c6e3-115">[!code-cs[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="5c6e3-115">[!code-cs[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]</span></span>  
  
 <span data-ttu-id="5c6e3-116">종료자는 개체의 기본 클래스에서 <xref:System.Object.Finalize%2A>를 암시적으로 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6e3-116">The finalizer implicitly calls <xref:System.Object.Finalize%2A> on the base class of the object.</span></span> <span data-ttu-id="5c6e3-117">따라서 종료자 호출은 다음 코드로 암시적으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c6e3-117">Therefore, a call to a finalizer is implicitly translated to the following code:</span></span>  
  
```csharp  
protected override void Finalize()  
{  
    try  
    {  
        // Cleanup statements...  
    }  
    finally  
    {  
        base.Finalize();  
    }  
}  
```  
  
 <span data-ttu-id="5c6e3-118">즉, `Finalize` 메서드가 상속 체인의 모든 인스턴스에 대해 최다 파생에서 최소 파생까지 재귀적으로 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c6e3-118">This means that the `Finalize` method is called recursively for all instances in the inheritance chain, from the most-derived to the least-derived.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5c6e3-119">빈 종료자는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5c6e3-119">Empty finalizers should not be used.</span></span> <span data-ttu-id="5c6e3-120">클래스에 종료자가 포함되어 있으면 `Finalize` 큐에서 항목이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c6e3-120">When a class contains a finalizer, an entry is created in the `Finalize` queue.</span></span> <span data-ttu-id="5c6e3-121">종료자를 호출하면 가비지 수집기가 호출되어 큐를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6e3-121">When the finalizer is called, the garbage collector is invoked to process the queue.</span></span> <span data-ttu-id="5c6e3-122">종료자가 비어 있으면 성능이 불필요하게 저하됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c6e3-122">An empty finalizer just causes a needless loss of performance.</span></span>  
  
 <span data-ttu-id="5c6e3-123">종료자가 호출되는 시기는 가비지 수집기에 의해 결정되기 때문에 프로그래머가 제어할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5c6e3-123">The programmer has no control over when the finalizer is called because this is determined by the garbage collector.</span></span> <span data-ttu-id="5c6e3-124">가비지 수집기는 응용 프로그램에서 더 이상 사용되지 않는 개체를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6e3-124">The garbage collector checks for objects that are no longer being used by the application.</span></span> <span data-ttu-id="5c6e3-125">개체를 종료할 수 있는 것으로 판단되면 종료자(있는 경우)를 호출하고 개체를 저장하는 데 사용된 메모리를 회수합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6e3-125">If it considers an object eligible for finalization, it calls the finalizer (if any) and reclaims the memory used to store the object.</span></span> <span data-ttu-id="5c6e3-126">종료자는 프로그램이 종료될 때도 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c6e3-126">Finalizers are also called when the program exits.</span></span>  
  
 <span data-ttu-id="5c6e3-127"><xref:System.GC.Collect%2A>를 호출하여 강제로 가비지 수집할 수 있지만 대부분의 경우 성능 문제가 발생할 수 있으므로 방지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6e3-127">It is possible to force garbage collection by calling <xref:System.GC.Collect%2A>, but most of the time, this should be avoided because it may create performance issues.</span></span>  
  
## <a name="using-finalizers-to-release-resources"></a><span data-ttu-id="5c6e3-128">종료자를 사용하여 리소스 해제</span><span class="sxs-lookup"><span data-stu-id="5c6e3-128">Using Finalizers to Release Resources</span></span>  
 <span data-ttu-id="5c6e3-129">일반적으로 C#에서는 가비지 수집을 사용하는 런타임을 대상으로 하지 않는 언어로 개발할 때 필요한 만큼 많은 메모리 관리가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5c6e3-129">In general, C# does not require as much memory management as is needed when you develop with a language that does not target a runtime with garbage collection.</span></span> <span data-ttu-id="5c6e3-130">이는 .NET Framework 가비지 수집기에서 개체에 대한 메모리 할당 및 해제를 암시적으로 관리하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="5c6e3-130">This is because the .NET Framework garbage collector implicitly manages the allocation and release of memory for your objects.</span></span> <span data-ttu-id="5c6e3-131">그러나 응용 프로그램에서 창, 파일 및 네트워크 연결 등의 관리되지 않는 리소스를 캡슐화하는 경우 종료자를 사용하여 해당 리소스를 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6e3-131">However, when your application encapsulates unmanaged resources such as windows, files, and network connections, you should use finalizers to free those resources.</span></span> <span data-ttu-id="5c6e3-132">개체를 종료할 수 있으면 가비지 수집기에서 개체의 `Finalize` 메서드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6e3-132">When the object is eligible for finalization, the garbage collector runs the `Finalize` method of the object.</span></span>  
  
## <a name="explicit-release-of-resources"></a><span data-ttu-id="5c6e3-133">리소스의 명시적 해제</span><span class="sxs-lookup"><span data-stu-id="5c6e3-133">Explicit Release of Resources</span></span>  
 <span data-ttu-id="5c6e3-134">응용 프로그램에서 비용이 많이 드는 외부 리소스를 사용하는 경우 가비지 수집기에서 개체를 해제하기 전에 리소스를 명시적으로 해제하는 방법을 제공하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5c6e3-134">If your application is using an expensive external resource, we also recommend that you provide a way to explicitly release the resource before the garbage collector frees the object.</span></span> <span data-ttu-id="5c6e3-135">이렇게 하려면 <xref:System.IDisposable> 인터페이스에서 개체에 필요한 정리를 수행하는 `Dispose` 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="5c6e3-135">You do this by implementing a `Dispose` method from the <xref:System.IDisposable> interface that performs the necessary cleanup for the object.</span></span> <span data-ttu-id="5c6e3-136">이렇게 하면 응용 프로그램의 성능을 상당히 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c6e3-136">This can considerably improve the performance of the application.</span></span> <span data-ttu-id="5c6e3-137">이렇게 리소스를 명시적으로 제어하는 경우에도 종료자는 `Dispose` 메서드 호출에 실패할 경우 리소스를 정리하는 안전한 방법이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c6e3-137">Even with this explicit control over resources, the finalizer becomes a safeguard to clean up resources if the call to the `Dispose` method failed.</span></span>  
  
 <span data-ttu-id="5c6e3-138">리소스 정리에 대한 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5c6e3-138">For more details about cleaning up resources, see the following topics:</span></span>  
  
-   [<span data-ttu-id="5c6e3-139">관리되지 않는 리소스 정리</span><span class="sxs-lookup"><span data-stu-id="5c6e3-139">Cleaning Up Unmanaged Resources</span></span>](../../../standard/garbage-collection/unmanaged.md)  
  
-   [<span data-ttu-id="5c6e3-140">Dispose 메서드 구현</span><span class="sxs-lookup"><span data-stu-id="5c6e3-140">Implementing a Dispose Method</span></span>](../../../standard/garbage-collection/implementing-dispose.md)  
  
-   [<span data-ttu-id="5c6e3-141">using 문</span><span class="sxs-lookup"><span data-stu-id="5c6e3-141">using Statement</span></span>](../../../csharp/language-reference/keywords/using-statement.md)  
  
## <a name="example"></a><span data-ttu-id="5c6e3-142">예제</span><span class="sxs-lookup"><span data-stu-id="5c6e3-142">Example</span></span>  
 <span data-ttu-id="5c6e3-143">다음 예제에서는 상속 체인을 구성하는 세 가지 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5c6e3-143">The following example creates three classes that make a chain of inheritance.</span></span> <span data-ttu-id="5c6e3-144">`First` 클래스는 기본 클래스이고, `Second`는 `First`에서 파생되며, `Third`는 `Second`에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c6e3-144">The class `First` is the base class, `Second` is derived from `First`, and `Third` is derived from `Second`.</span></span> <span data-ttu-id="5c6e3-145">세 클래스 모두 종료자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c6e3-145">All three have finalizers.</span></span> <span data-ttu-id="5c6e3-146">`Main`에서 최다 파생 클래스의 인스턴스가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="5c6e3-146">In `Main`, an instance of the most-derived class is created.</span></span> <span data-ttu-id="5c6e3-147">프로그램이 실행되면 세 클래스에 대한 종료자가 최다 파생부터 최소 파생까지 순서대로 자동으로 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c6e3-147">When the program runs, notice that the finalizers for the three classes are called automatically, and in order, from the most-derived to the least-derived.</span></span>  
  
 <span data-ttu-id="5c6e3-148">[!code-cs[csProgGuideObjects#85](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/destructors_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="5c6e3-148">[!code-cs[csProgGuideObjects#85](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/destructors_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="5c6e3-149">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="5c6e3-149">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5c6e3-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5c6e3-150">See Also</span></span>  
 <span data-ttu-id="5c6e3-151"><xref:System.IDisposable></span><span class="sxs-lookup"><span data-stu-id="5c6e3-151"><xref:System.IDisposable></span></span>   
 <span data-ttu-id="5c6e3-152">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="5c6e3-152">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="5c6e3-153">[생성자](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span><span class="sxs-lookup"><span data-stu-id="5c6e3-153">[Constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span></span>  
 [<span data-ttu-id="5c6e3-154">가비지 수집</span><span class="sxs-lookup"><span data-stu-id="5c6e3-154">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)

