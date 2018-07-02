---
title: using 문(C# 참조)
ms.date: 07/20/2015
helpviewer_keywords:
- using statement [C#]
ms.assetid: afc355e6-f0b9-4240-94dd-0d93f17d9fc3
ms.openlocfilehash: 7bf9138721ecee63c65c2e39922aee96b1dfaa41
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207962"
---
# <a name="using-statement-c-reference"></a><span data-ttu-id="f172f-102">using 문(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="f172f-102">using Statement (C# Reference)</span></span>
<span data-ttu-id="f172f-103"><xref:System.IDisposable> 개체의 올바른 사용을 보장하는 편리한 구문을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f172f-103">Provides a convenient syntax that ensures the correct use of <xref:System.IDisposable> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f172f-104">예</span><span class="sxs-lookup"><span data-stu-id="f172f-104">Example</span></span>  
 <span data-ttu-id="f172f-105">다음 예제에서는 `using` 문을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f172f-105">The following example shows how to use the `using` statement.</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_1.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="f172f-106">설명</span><span class="sxs-lookup"><span data-stu-id="f172f-106">Remarks</span></span>  
 <span data-ttu-id="f172f-107"><xref:System.IO.File> 및 <xref:System.Drawing.Font>는 관리되지 않는 리소스에 액세스하는 관리되는 형식의 예입니다(이 경우 파일 핸들 및 장치 컨텍스트).</span><span class="sxs-lookup"><span data-stu-id="f172f-107"><xref:System.IO.File> and <xref:System.Drawing.Font> are examples of managed types that access unmanaged resources (in this case file handles and device contexts).</span></span> <span data-ttu-id="f172f-108">다른 많은 종류의 관리되지 않는 리소스 및 이를 캡슐화하는 클래스 라이브러리 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f172f-108">There are many other kinds of unmanaged resources and class library types that encapsulate them.</span></span> <span data-ttu-id="f172f-109">이러한 형식은 모두 <xref:System.IDisposable> 인터페이스를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f172f-109">All such types must implement the <xref:System.IDisposable> interface.</span></span>  
  
<span data-ttu-id="f172f-110">`IDisposable` 개체의 수명이 단일 메서드로 제한된 경우 `using` 문에서 선언하고 인스턴스화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f172f-110">When the lifetime of an `IDisposable` object is limited to a single method, you should declare and instantiate it in the `using` statement.</span></span> <span data-ttu-id="f172f-111">`using` 문은 올바른 방법으로 개체에서 <xref:System.IDisposable.Dispose%2A> 메서드를 호출하며, (앞서 설명한 대로 사용하는 경우) <xref:System.IDisposable.Dispose%2A>가 호출되자마자 개체 자체가 범위를 벗어나도록 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f172f-111">The `using` statement calls the <xref:System.IDisposable.Dispose%2A> method on the object in the correct way, and (when you use it as shown earlier) it also causes the object itself to go out of scope as soon as <xref:System.IDisposable.Dispose%2A> is called.</span></span> <span data-ttu-id="f172f-112">`using` 블록 내에서 개체는 읽기 전용이며 수정하거나 다시 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f172f-112">Within the `using` block, the object is read-only and cannot be modified or reassigned.</span></span>  
  
 <span data-ttu-id="f172f-113">`using` 문은 `using` 블록 내에서 예외가 발생하더라도 <xref:System.IDisposable.Dispose%2A>가 호출되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f172f-113">The `using` statement ensures that <xref:System.IDisposable.Dispose%2A> is called even if an exception occurs within the `using` block.</span></span> <span data-ttu-id="f172f-114">`try` 블록 내부에 개체를 배치한 다음, `finally` 블록에서 <xref:System.IDisposable.Dispose%2A>를 호출해도 동일한 결과를 얻을 수 있습니다. 실제로 컴파일러는 이 방법으로 `using` 문을 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="f172f-114">You can achieve the same result by putting the object inside a `try` block and then calling <xref:System.IDisposable.Dispose%2A> in a `finally` block; in fact, this is how the `using` statement is translated by the compiler.</span></span> <span data-ttu-id="f172f-115">이전의 코드 예제는 컴파일 시 다음 코드로 확장됩니다(개체의 제한된 범위를 만드는 여분의 중괄호 참고).</span><span class="sxs-lookup"><span data-stu-id="f172f-115">The code example earlier expands to the following code at compile time (note the extra curly braces to create the limited scope for the object):</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_2.cs)]  
 
 <span data-ttu-id="f172f-116">`try`-`finally` 문에 대한 자세한 내용은 [try-finally](try-finally.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f172f-116">For more information about the `try`-`finally` statement, see the [try-finally](try-finally.md) topic.</span></span>
  
 <span data-ttu-id="f172f-117">다음 예제와 같이 `using` 문에서 한 형식의 여러 인스턴스를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f172f-117">Multiple instances of a type can be declared in the `using` statement, as shown in the following example:</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_3.cs)]  
  
 <span data-ttu-id="f172f-118">리소스 개체를 인스턴스화한 후 `using` 문에 변수를 전달할 수 있지만, 이 방법이 최선은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f172f-118">You can instantiate the resource object and then pass the variable to the `using` statement, but this is not a best practice.</span></span> <span data-ttu-id="f172f-119">이 경우 컨트롤이 `using` 블록을 벗어난 후에도 개체가 범위 내에 있지만, 관리되지 않는 리소스에 액세스하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f172f-119">In this case, after control leaves the `using` block, the object remains in scope but probably has no access to its unmanaged resources.</span></span> <span data-ttu-id="f172f-120">즉, 더 이상 완전히 초기화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f172f-120">In other words, it's not fully initialized anymore.</span></span> <span data-ttu-id="f172f-121">`using` 블록 외부에서 개체를 사용하려고 하면 예외가 throw될 위험이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f172f-121">If you try to use the object outside the `using` block, you risk causing an exception to be thrown.</span></span> <span data-ttu-id="f172f-122">따라서 일반적으로 `using` 문에서 개체를 인스턴스화하고 `using` 블록에서 범위를 제한하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f172f-122">For this reason, it's generally better to instantiate the object in the `using` statement and limit its scope to the `using` block.</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_4.cs)]  
  
<span data-ttu-id="f172f-123">`IDisposable` 개체를 삭제하는 방법에 대한 자세한 내용은 [IDisposable을 구현하는 개체 사용](../../../standard/garbage-collection/using-objects.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f172f-123">For more information about disposing of `IDisposable` objects, see [Using objects that implement IDisposable](../../../standard/garbage-collection/using-objects.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f172f-124">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="f172f-124">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f172f-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f172f-125">See Also</span></span>  
 [<span data-ttu-id="f172f-126">C# 참조</span><span class="sxs-lookup"><span data-stu-id="f172f-126">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="f172f-127">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="f172f-127">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f172f-128">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="f172f-128">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="f172f-129">using 지시문</span><span class="sxs-lookup"><span data-stu-id="f172f-129">using Directive</span></span>](../../../csharp/language-reference/keywords/using-directive.md)  
 [<span data-ttu-id="f172f-130">가비지 수집</span><span class="sxs-lookup"><span data-stu-id="f172f-130">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)  
 [<span data-ttu-id="f172f-131">IDisposable을 구현하는 개체 사용</span><span class="sxs-lookup"><span data-stu-id="f172f-131">Using objects that implement IDisposable</span></span>](../../../standard/garbage-collection/using-objects.md)  
 [<span data-ttu-id="f172f-132">IDisposable 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f172f-132">IDisposable interface</span></span>](xref:System.IDisposable)
