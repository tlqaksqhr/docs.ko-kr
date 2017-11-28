---
title: "종료자(C# 프로그래밍 가이드)"
ms.date: 05/10/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- ~ [C#], in finalizers
- C# language, finalizers
- finalizers [C#]
ms.assetid: 1ae6e46d-a4b1-4a49-abe5-b97f53d9e049
caps.latest.revision: "24"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b1efe92c371e44eb2d650eb07facc3e7030e9766
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="finalizers-c-programming-guide"></a><span data-ttu-id="be5b8-102">종료자(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="be5b8-102">Finalizers (C# Programming Guide)</span></span>
<span data-ttu-id="be5b8-103">종료자는 클래스의 인스턴스를 소멸하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="be5b8-103">Finalizers are used to destruct instances of classes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be5b8-104">설명</span><span class="sxs-lookup"><span data-stu-id="be5b8-104">Remarks</span></span>  
  
-   <span data-ttu-id="be5b8-105">종료자는 구조체에서 정의할 수 없으며,</span><span class="sxs-lookup"><span data-stu-id="be5b8-105">Finalizers cannot be defined in structs.</span></span> <span data-ttu-id="be5b8-106">클래스에서만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="be5b8-106">They are only used with classes.</span></span>  
  
-   <span data-ttu-id="be5b8-107">클래스에는 종료자가 하나만 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be5b8-107">A class can only have one finalizer.</span></span>  
  
-   <span data-ttu-id="be5b8-108">종료자는 상속하거나 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="be5b8-108">Finalizers cannot be inherited or overloaded.</span></span>  
  
-   <span data-ttu-id="be5b8-109">종료자를 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="be5b8-109">Finalizers cannot be called.</span></span> <span data-ttu-id="be5b8-110">자동으로 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="be5b8-110">They are invoked automatically.</span></span>  
  
-   <span data-ttu-id="be5b8-111">종료자는 한정자를 사용하거나 매개 변수를 갖지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be5b8-111">A finalizer does not take modifiers or have parameters.</span></span>  
  
 <span data-ttu-id="be5b8-112">예를 들어 다음은 `Car` 클래스에 대한 종료자의 선언입니다.</span><span class="sxs-lookup"><span data-stu-id="be5b8-112">For example, the following is a declaration of a finalizer for the `Car` class.</span></span>
  
 [!code-csharp[csProgGuideObjects#86](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/destructors_1.cs)]  

<span data-ttu-id="be5b8-113">다음 예제와 같이 종료자를 식 본문 정의로 구현할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be5b8-113">A finalizer can also be implemented as an expression body definition, as the following example shows.</span></span>

[!code-csharp[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]  
  
 <span data-ttu-id="be5b8-114">종료자는 개체의 기본 클래스에서 <xref:System.Object.Finalize%2A>를 암시적으로 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="be5b8-114">The finalizer implicitly calls <xref:System.Object.Finalize%2A> on the base class of the object.</span></span> <span data-ttu-id="be5b8-115">따라서 종료자 호출은 다음 코드로 암시적으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="be5b8-115">Therefore, a call to a finalizer is implicitly translated to the following code:</span></span>  
  
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
  
 <span data-ttu-id="be5b8-116">즉, `Finalize` 메서드가 상속 체인의 모든 인스턴스에 대해 최다 파생에서 최소 파생까지 재귀적으로 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="be5b8-116">This means that the `Finalize` method is called recursively for all instances in the inheritance chain, from the most-derived to the least-derived.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="be5b8-117">빈 종료자는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="be5b8-117">Empty finalizers should not be used.</span></span> <span data-ttu-id="be5b8-118">클래스에 종료자가 포함되어 있으면 `Finalize` 큐에서 항목이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="be5b8-118">When a class contains a finalizer, an entry is created in the `Finalize` queue.</span></span> <span data-ttu-id="be5b8-119">종료자를 호출하면 가비지 수집기가 호출되어 큐를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="be5b8-119">When the finalizer is called, the garbage collector is invoked to process the queue.</span></span> <span data-ttu-id="be5b8-120">종료자가 비어 있으면 성능이 불필요하게 저하됩니다.</span><span class="sxs-lookup"><span data-stu-id="be5b8-120">An empty finalizer just causes a needless loss of performance.</span></span>  
  
 <span data-ttu-id="be5b8-121">종료자가 호출되는 시기는 가비지 수집기에 의해 결정되기 때문에 프로그래머가 제어할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="be5b8-121">The programmer has no control over when the finalizer is called because this is determined by the garbage collector.</span></span> <span data-ttu-id="be5b8-122">가비지 수집기는 응용 프로그램에서 더 이상 사용되지 않는 개체를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="be5b8-122">The garbage collector checks for objects that are no longer being used by the application.</span></span> <span data-ttu-id="be5b8-123">개체를 종료할 수 있는 것으로 판단되면 종료자(있는 경우)를 호출하고 개체를 저장하는 데 사용된 메모리를 회수합니다.</span><span class="sxs-lookup"><span data-stu-id="be5b8-123">If it considers an object eligible for finalization, it calls the finalizer (if any) and reclaims the memory used to store the object.</span></span> <span data-ttu-id="be5b8-124">종료자는 프로그램이 종료될 때도 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="be5b8-124">Finalizers are also called when the program exits.</span></span>  
  
 <span data-ttu-id="be5b8-125"><xref:System.GC.Collect%2A>를 호출하여 강제로 가비지 수집할 수 있지만 대부분의 경우 성능 문제가 발생할 수 있으므로 방지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be5b8-125">It is possible to force garbage collection by calling <xref:System.GC.Collect%2A>, but most of the time, this should be avoided because it may create performance issues.</span></span>  
  
## <a name="using-finalizers-to-release-resources"></a><span data-ttu-id="be5b8-126">종료자를 사용하여 리소스 해제</span><span class="sxs-lookup"><span data-stu-id="be5b8-126">Using Finalizers to Release Resources</span></span>  
 <span data-ttu-id="be5b8-127">일반적으로 C#에서는 가비지 수집을 사용하는 런타임을 대상으로 하지 않는 언어로 개발할 때 필요한 만큼 많은 메모리 관리가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be5b8-127">In general, C# does not require as much memory management as is needed when you develop with a language that does not target a runtime with garbage collection.</span></span> <span data-ttu-id="be5b8-128">이는 .NET Framework 가비지 수집기에서 개체에 대한 메모리 할당 및 해제를 암시적으로 관리하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="be5b8-128">This is because the .NET Framework garbage collector implicitly manages the allocation and release of memory for your objects.</span></span> <span data-ttu-id="be5b8-129">그러나 응용 프로그램에서 창, 파일 및 네트워크 연결 등의 관리되지 않는 리소스를 캡슐화하는 경우 종료자를 사용하여 해당 리소스를 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be5b8-129">However, when your application encapsulates unmanaged resources such as windows, files, and network connections, you should use finalizers to free those resources.</span></span> <span data-ttu-id="be5b8-130">개체를 종료할 수 있으면 가비지 수집기에서 개체의 `Finalize` 메서드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="be5b8-130">When the object is eligible for finalization, the garbage collector runs the `Finalize` method of the object.</span></span>  
  
## <a name="explicit-release-of-resources"></a><span data-ttu-id="be5b8-131">리소스의 명시적 해제</span><span class="sxs-lookup"><span data-stu-id="be5b8-131">Explicit Release of Resources</span></span>  
 <span data-ttu-id="be5b8-132">응용 프로그램에서 비용이 많이 드는 외부 리소스를 사용하는 경우 가비지 수집기에서 개체를 해제하기 전에 리소스를 명시적으로 해제하는 방법을 제공하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="be5b8-132">If your application is using an expensive external resource, we also recommend that you provide a way to explicitly release the resource before the garbage collector frees the object.</span></span> <span data-ttu-id="be5b8-133">이렇게 하려면 <xref:System.IDisposable> 인터페이스에서 개체에 필요한 정리를 수행하는 `Dispose` 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="be5b8-133">You do this by implementing a `Dispose` method from the <xref:System.IDisposable> interface that performs the necessary cleanup for the object.</span></span> <span data-ttu-id="be5b8-134">이렇게 하면 응용 프로그램의 성능을 상당히 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be5b8-134">This can considerably improve the performance of the application.</span></span> <span data-ttu-id="be5b8-135">이렇게 리소스를 명시적으로 제어하는 경우에도 종료자는 `Dispose` 메서드 호출에 실패할 경우 리소스를 정리하는 안전한 방법이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be5b8-135">Even with this explicit control over resources, the finalizer becomes a safeguard to clean up resources if the call to the `Dispose` method failed.</span></span>  
  
 <span data-ttu-id="be5b8-136">리소스 정리에 대한 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="be5b8-136">For more details about cleaning up resources, see the following topics:</span></span>  
  
-   [<span data-ttu-id="be5b8-137">관리되지 않는 리소스 정리</span><span class="sxs-lookup"><span data-stu-id="be5b8-137">Cleaning Up Unmanaged Resources</span></span>](../../../standard/garbage-collection/unmanaged.md)  
  
-   [<span data-ttu-id="be5b8-138">Dispose 메서드 구현</span><span class="sxs-lookup"><span data-stu-id="be5b8-138">Implementing a Dispose Method</span></span>](../../../standard/garbage-collection/implementing-dispose.md)  
  
-   [<span data-ttu-id="be5b8-139">using 문</span><span class="sxs-lookup"><span data-stu-id="be5b8-139">using Statement</span></span>](../../../csharp/language-reference/keywords/using-statement.md)  
  
## <a name="example"></a><span data-ttu-id="be5b8-140">예제</span><span class="sxs-lookup"><span data-stu-id="be5b8-140">Example</span></span>  
 <span data-ttu-id="be5b8-141">다음 예제에서는 상속 체인을 구성하는 세 가지 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="be5b8-141">The following example creates three classes that make a chain of inheritance.</span></span> <span data-ttu-id="be5b8-142">`First` 클래스는 기본 클래스이고, `Second`는 `First`에서 파생되며, `Third`는 `Second`에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="be5b8-142">The class `First` is the base class, `Second` is derived from `First`, and `Third` is derived from `Second`.</span></span> <span data-ttu-id="be5b8-143">세 클래스 모두 종료자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be5b8-143">All three have finalizers.</span></span> <span data-ttu-id="be5b8-144">`Main`에서 최다 파생 클래스의 인스턴스가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="be5b8-144">In `Main`, an instance of the most-derived class is created.</span></span> <span data-ttu-id="be5b8-145">프로그램이 실행되면 세 클래스에 대한 종료자가 최다 파생부터 최소 파생까지 순서대로 자동으로 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="be5b8-145">When the program runs, notice that the finalizers for the three classes are called automatically, and in order, from the most-derived to the least-derived.</span></span>  
  
 [!code-csharp[csProgGuideObjects#85](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/destructors_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="be5b8-146">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="be5b8-146">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="be5b8-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="be5b8-147">See Also</span></span>  
 <xref:System.IDisposable>  
 [<span data-ttu-id="be5b8-148">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="be5b8-148">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="be5b8-149">생성자</span><span class="sxs-lookup"><span data-stu-id="be5b8-149">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
 [<span data-ttu-id="be5b8-150">가비지 수집</span><span class="sxs-lookup"><span data-stu-id="be5b8-150">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
