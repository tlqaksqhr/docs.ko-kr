---
title: "using 문(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- using statement [C#]
ms.assetid: afc355e6-f0b9-4240-94dd-0d93f17d9fc3
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1fdf37e1bfc57bf850b332f167e57d3e05d23e78
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="using-statement-c-reference"></a><span data-ttu-id="25791-102">using 문(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="25791-102">using Statement (C# Reference)</span></span>
<span data-ttu-id="25791-103"><xref:System.IDisposable> 개체의 올바른 사용을 보장하는 편리한 구문을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="25791-103">Provides a convenient syntax that ensures the correct use of <xref:System.IDisposable> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25791-104">예제</span><span class="sxs-lookup"><span data-stu-id="25791-104">Example</span></span>  
 <span data-ttu-id="25791-105">다음 예제에서는 using 문을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="25791-105">The following example shows how to use the using statement.</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_1.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="25791-106">설명</span><span class="sxs-lookup"><span data-stu-id="25791-106">Remarks</span></span>  
 <span data-ttu-id="25791-107"><xref:System.IO.File> 및 <xref:System.Drawing.Font>는 관리되지 않는 리소스에 액세스하는 관리되는 형식의 예입니다(이 경우 파일 핸들 및 장치 컨텍스트).</span><span class="sxs-lookup"><span data-stu-id="25791-107"><xref:System.IO.File> and <xref:System.Drawing.Font> are examples of managed types that access unmanaged resources (in this case file handles and device contexts).</span></span> <span data-ttu-id="25791-108">다른 많은 종류의 관리되지 않는 리소스 및 이를 캡슐화하는 클래스 라이브러리 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25791-108">There are many other kinds of unmanaged resources and class library types that encapsulate them.</span></span> <span data-ttu-id="25791-109">이러한 형식은 모두 <xref:System.IDisposable> 인터페이스를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25791-109">All such types must implement the <xref:System.IDisposable> interface.</span></span>  
  
<span data-ttu-id="25791-110">때의 수명을 `IDisposable` 개체는 단일 메서드를 제한, 선언 하 고에서 인스턴스화하는 `using` 문.</span><span class="sxs-lookup"><span data-stu-id="25791-110">When the lifetime of an `IDisposable` object is limited to a single method, you should declare and instantiate it in a `using` statement.</span></span> <span data-ttu-id="25791-111">`using` 문은 올바른 방법으로 개체에서 <xref:System.IDisposable.Dispose%2A> 메서드를 호출하며, (앞서 설명한 대로 사용하는 경우) <xref:System.IDisposable.Dispose%2A>가 호출되자마자 개체 자체가 범위를 벗어나도록 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="25791-111">The `using` statement calls the <xref:System.IDisposable.Dispose%2A> method on the object in the correct way, and (when you use it as shown earlier) it also causes the object itself to go out of scope as soon as <xref:System.IDisposable.Dispose%2A> is called.</span></span> <span data-ttu-id="25791-112">`using` 블록 내에서 개체는 읽기 전용이며 수정하거나 다시 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25791-112">Within the `using` block, the object is read-only and cannot be modified or reassigned.</span></span>  
  
 <span data-ttu-id="25791-113">`using` 문을 사용하면 개체에서 메서드를 호출하는 동안 예외가 발생하더라도 <xref:System.IDisposable.Dispose%2A>가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="25791-113">The `using` statement ensures that <xref:System.IDisposable.Dispose%2A> is called even if an exception occurs while you are calling methods on the object.</span></span> <span data-ttu-id="25791-114">try 블록 내부에 개체를 배치하고 finally 블록에서 <xref:System.IDisposable.Dispose%2A>를 호출해도 동일한 결과를 얻을 수 있습니다. 실제로 컴파일러는 이 방법으로 `using` 문을 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="25791-114">You can achieve the same result by putting the object inside a try block and then calling <xref:System.IDisposable.Dispose%2A> in a finally block; in fact, this is how the `using` statement is translated by the compiler.</span></span> <span data-ttu-id="25791-115">이전의 코드 예제는 컴파일 시 다음 코드로 확장됩니다(개체의 제한된 범위를 만드는 여분의 중괄호 참고).</span><span class="sxs-lookup"><span data-stu-id="25791-115">The code example earlier expands to the following code at compile time (note the extra curly braces to create the limited scope for the object):</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_2.cs)]  
  
 <span data-ttu-id="25791-116">다음 예제와 같이 `using` 문에서 한 형식의 여러 인스턴스를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25791-116">Multiple instances of a type can be declared in a `using` statement, as shown in the following example.</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_3.cs)]  
  
 <span data-ttu-id="25791-117">리소스 개체를 인스턴스화한 후 `using` 문에 변수를 전달할 수 있지만, 이 방법이 최선은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="25791-117">You can instantiate the resource object and then pass the variable to the `using` statement, but this is not a best practice.</span></span> <span data-ttu-id="25791-118">이 경우 관리되지 않는 리소스에 더 이상 액세스할 수 없더라도 제어가 `using` 블록을 벗어나면 개체는 범위에 남아 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25791-118">In this case, the object remains in scope after control leaves the `using` block even though it will probably no longer have access to its unmanaged resources.</span></span> <span data-ttu-id="25791-119">다시 말해, 더 이상 완전히 초기화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="25791-119">In other words, it will no longer be fully initialized.</span></span> <span data-ttu-id="25791-120">`using` 블록 외부에서 개체를 사용하려고 하면 예외가 throw될 위험이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25791-120">If you try to use the object outside the `using` block, you risk causing an exception to be thrown.</span></span> <span data-ttu-id="25791-121">따라서 일반적으로 `using` 문에서 개체를 인스턴스화하고 `using` 블록에서 범위를 제한하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="25791-121">For this reason, it is generally better to instantiate the object in the `using` statement and limit its scope to the `using` block.</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_4.cs)]  
  
<span data-ttu-id="25791-122">삭제에 대 한 자세한 내용은 `IDisposable` 개체 참조 [IDisposable을 구현 하는 개체를 사용 하 여](../../../standard/garbage-collection/using-objects.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="25791-122">For more information on disposing of `IDisposable` objects, see [Using objects that implement IDisposable](../../../standard/garbage-collection/using-objects.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="25791-123">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="25791-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="25791-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="25791-124">See Also</span></span>  
 [<span data-ttu-id="25791-125">C# 참조</span><span class="sxs-lookup"><span data-stu-id="25791-125">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="25791-126">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="25791-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="25791-127">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="25791-127">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="25791-128">using 지시문</span><span class="sxs-lookup"><span data-stu-id="25791-128">using Directive</span></span>](../../../csharp/language-reference/keywords/using-directive.md)  
 [<span data-ttu-id="25791-129">가비지 수집</span><span class="sxs-lookup"><span data-stu-id="25791-129">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)  
 [<span data-ttu-id="25791-130">IDisposable을 구현하는 개체 사용</span><span class="sxs-lookup"><span data-stu-id="25791-130">Using objects that implement IDisposable</span></span>](../../../standard/garbage-collection/using-objects.md)  
 [<span data-ttu-id="25791-131">IDisposable 인터페이스</span><span class="sxs-lookup"><span data-stu-id="25791-131">IDisposable interface</span></span>](xref:System.IDisposable)
