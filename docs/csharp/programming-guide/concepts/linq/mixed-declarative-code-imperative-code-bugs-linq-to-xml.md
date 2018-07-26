---
title: 혼합된 선언적 코드-명령적 코드 버그(LINQ to XML)(C#)
ms.date: 07/20/2015
ms.assetid: fada62d0-0680-4e73-945a-2b00d7a507af
ms.openlocfilehash: efc58aac69c53cda724e5fe348560a99311e8d4c
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/25/2018
ms.locfileid: "39244074"
---
# <a name="mixed-declarative-codeimperative-code-bugs-linq-to-xml-c"></a><span data-ttu-id="7ba9a-102">혼합된 선언적 코드-명령적 코드 버그(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="7ba9a-102">Mixed Declarative Code/Imperative Code Bugs (LINQ to XML) (C#)</span></span>
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="7ba9a-103">에는 XML 트리를 직접 수정하는 데 사용할 수 있는 다양한 메서드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-103"> contains various methods that allow you to modify an XML tree directly.</span></span> <span data-ttu-id="7ba9a-104">요소를 추가 및 삭제하고, 요소의 내용을 변경하고, 특성을 추가하는 등의 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-104">You can add elements, delete elements, change the contents of an element, add attributes, and so on.</span></span> <span data-ttu-id="7ba9a-105">이 프로그래밍 인터페이스는 [XML 트리 수정(LINQ to XML)(C#)](../../../../csharp/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-105">This programming interface is described in [Modifying XML Trees (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md).</span></span> <span data-ttu-id="7ba9a-106"><xref:System.Xml.Linq.XContainer.Elements%2A>와 같은 축 중 하나를 반복하면서 XML 트리를 수정하면 이상한 버그가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-106">If you are iterating through one of the axes, such as <xref:System.Xml.Linq.XContainer.Elements%2A>, and you are modifying the XML tree as you iterate through the axis, you can end up with some strange bugs.</span></span>  
  
 <span data-ttu-id="7ba9a-107">이 문제를 "할로윈 문제"라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-107">This problem is sometimes known as "The Halloween Problem".</span></span>  
  
## <a name="definition-of-the-problem"></a><span data-ttu-id="7ba9a-108">문제에 대한 정의</span><span class="sxs-lookup"><span data-stu-id="7ba9a-108">Definition of the Problem</span></span>  
 <span data-ttu-id="7ba9a-109">LINQ를 사용하여 컬렉션을 반복하는 코드를 작성하는 경우 선언적 스타일로 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-109">When you write some code using LINQ that iterates through a collection, you are writing code in a declarative style.</span></span> <span data-ttu-id="7ba9a-110">이는 작업을 수행하는 *방법*이 아니라 원하는 *작업*을 설명하는 것과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-110">It is more akin to describing *what* you want, rather that *how* you want to get it done.</span></span> <span data-ttu-id="7ba9a-111">1) 첫 번째 요소를 가져오고 2) 특정 조건에 대해 테스트한 다음 3) 요소를 수정하고 4) 요소를 다시 목록에 배치하는 코드를 작성하는 경우 코드는 명령적 코드일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-111">If you write code that 1) gets the first element, 2) tests it for some condition, 3) modifies it, and 4) puts it back into the list, then this would be imperative code.</span></span> <span data-ttu-id="7ba9a-112">즉, 작업을 수행할 *방법*을 컴퓨터에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-112">You are telling the computer *how* to do what you want done.</span></span>  
  
 <span data-ttu-id="7ba9a-113">이러한 스타일의 코드를 동일한 작업에서 혼합하면 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-113">Mixing these styles of code in the same operation is what leads to problems.</span></span> <span data-ttu-id="7ba9a-114">다음을 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-114">Consider the following:</span></span>  
  
 <span data-ttu-id="7ba9a-115">세 항목(a, b 및 c)이 포함된 연결된 목록이 있는 경우를 생각해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-115">Suppose you have a linked list with three items in it (a, b, and c):</span></span>  
  
 `a -> b -> c`  
  
 <span data-ttu-id="7ba9a-116">이제 연결된 목록을 이동하여 세 항목(a', b' 및 c')을 새로 추가한다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-116">Now, suppose that you want to move through the linked list, adding three new items (a', b', and c').</span></span> <span data-ttu-id="7ba9a-117">다음과 같은 연결된 목록을 생성하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-117">You want the resulting linked list to look like this:</span></span>  
  
 `a -> a' -> b -> b' -> c -> c'`  
  
 <span data-ttu-id="7ba9a-118">따라서 목록을 반복하고 각 항목의 바로 뒤에 새 항목을 추가하는 코드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-118">So you write code that iterates through the list, and for every item, adds a new item right after it.</span></span> <span data-ttu-id="7ba9a-119">코드에서는 먼저 `a` 요소를 찾고 그 뒤에 `a'`를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-119">What happens is that your code will first see the `a` element, and insert `a'` after it.</span></span> <span data-ttu-id="7ba9a-120">그런 다음 목록의 다음 노드로 이동합니다. 하지만 다음 노드는 이제 `a'`입니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-120">Now, your code will move to the next node in the list, which is now `a'`!</span></span> <span data-ttu-id="7ba9a-121">코드에서는 새 항목 `a''`를 목록에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-121">It happily adds a new item to the list, `a''`.</span></span>  
  
 <span data-ttu-id="7ba9a-122">실제 상황에서 이 문제를 어떻게 해결하시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="7ba9a-122">How would you solve this in the real world?</span></span> <span data-ttu-id="7ba9a-123">연결된 원래 목록의 복사본을 만들고 완전히 새로운 목록을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-123">Well, you might make a copy of the original linked list, and create a completely new list.</span></span> <span data-ttu-id="7ba9a-124">또는 순전히 명령적 코드를 작성하는 경우 첫 번째 항목을 찾고 새 항목을 추가한 다음 연결된 목록에서 두 차례 이동하여 방금 추가한 요소를 건너뛸 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-124">Or if you are writing purely imperative code, you might find the first item, add the new item, and then advance twice in the linked list, advancing over the element that you just added.</span></span>  
  
## <a name="adding-while-iterating"></a><span data-ttu-id="7ba9a-125">반복하는 동안 추가</span><span class="sxs-lookup"><span data-stu-id="7ba9a-125">Adding While Iterating</span></span>  
 <span data-ttu-id="7ba9a-126">예를 들어, 트리의 모든 요소에 대한 중복 요소를 만드는 코드를 작성하는 경우를 생각해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-126">For example, suppose you want to write some code that for every element in a tree, you want to create a duplicate element:</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("A", "1"),  
    new XElement("B", "2"),  
    new XElement("C", "3")  
);  
foreach (XElement e in root.Elements())  
    root.Add(new XElement(e.Name, (string)e));  
```  
  
 <span data-ttu-id="7ba9a-127">이 코드는 무한 루프에 들어갑니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-127">This code goes into an infinite loop.</span></span> <span data-ttu-id="7ba9a-128">`foreach` 문은 `Elements()` 축을 반복하여 새 요소를 `doc` 요소에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-128">The `foreach` statement iterates through the `Elements()` axis, adding new elements to the `doc` element.</span></span> <span data-ttu-id="7ba9a-129">따라서 방금 추가한 요소도 반복하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-129">It ends up iterating also through the elements it just added.</span></span> <span data-ttu-id="7ba9a-130">루프를 반복할 때마다 새 개체를 할당하기 때문에 결국 사용 가능한 모든 메모리를 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-130">And because it allocates new objects with every iteration of the loop, it will eventually consume all available memory.</span></span>  
  
 <span data-ttu-id="7ba9a-131">다음과 같이 <xref:System.Linq.Enumerable.ToList%2A> 표준 쿼리 연산자를 사용하여 컬렉션을 메모리에 가져오는 방법으로 이 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-131">You can fix this problem by pulling the collection into memory using the <xref:System.Linq.Enumerable.ToList%2A> standard query operator, as follows:</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("A", "1"),  
    new XElement("B", "2"),  
    new XElement("C", "3")  
);  
foreach (XElement e in root.Elements().ToList())  
    root.Add(new XElement(e.Name, (string)e));  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="7ba9a-132">이제 코드가 제대로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-132">Now the code works.</span></span> <span data-ttu-id="7ba9a-133">생성되는 XML 트리는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-133">The resulting XML tree is the following:</span></span>  
  
```xml  
<Root>  
  <A>1</A>  
  <B>2</B>  
  <C>3</C>  
  <A>1</A>  
  <B>2</B>  
  <C>3</C>  
</Root>  
```  
  
## <a name="deleting-while-iterating"></a><span data-ttu-id="7ba9a-134">반복하는 동안 삭제</span><span class="sxs-lookup"><span data-stu-id="7ba9a-134">Deleting While Iterating</span></span>  
 <span data-ttu-id="7ba9a-135">특정 수준의 노드를 모두 삭제하려는 경우 다음과 같은 코드를 작성하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-135">If you want to delete all nodes at a certain level, you might be tempted to write code like the following:</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("A", "1"),  
    new XElement("B", "2"),  
    new XElement("C", "3")  
);  
foreach (XElement e in root.Elements())  
    e.Remove();  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="7ba9a-136">그러나 이 코드는 원하는 작업을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-136">However, this does not do what you want.</span></span> <span data-ttu-id="7ba9a-137">이 상황에서 첫 번째 요소 A를 제거하면 루트에 포함된 XML 트리에서 이 요소가 제거되고 반복을 수행하는 Elements 메서드의 코드에서 다음 요소를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-137">In this situation, after you have removed the first element, A, it is removed from the XML tree contained in root, and the code in the Elements method that is doing the iterating cannot find the next element.</span></span>  
  
 <span data-ttu-id="7ba9a-138">위에 있는 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-138">The preceding code produces the following output:</span></span>  
  
```xml  
<Root>  
  <B>2</B>  
  <C>3</C>  
</Root>  
```  
  
 <span data-ttu-id="7ba9a-139">여기에서도 해결 방법은 다음과 같이 <xref:System.Linq.Enumerable.ToList%2A>을 호출하여 컬렉션을 구체화하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-139">The solution again is to call <xref:System.Linq.Enumerable.ToList%2A> to materialize the collection, as follows:</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("A", "1"),  
    new XElement("B", "2"),  
    new XElement("C", "3")  
);  
foreach (XElement e in root.Elements().ToList())  
    e.Remove();  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="7ba9a-140">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-140">This produces the following output:</span></span>  
  
```xml  
<Root />  
```  
  
 <span data-ttu-id="7ba9a-141">또는 부모 요소에 대해 <xref:System.Xml.Linq.XElement.RemoveAll%2A>을 호출하여 반복을 모두 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-141">Alternatively, you can eliminate the iteration altogether by calling <xref:System.Xml.Linq.XElement.RemoveAll%2A> on the parent element:</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("A", "1"),  
    new XElement("B", "2"),  
    new XElement("C", "3")  
);  
root.RemoveAll();  
Console.WriteLine(root);  
```  
  
## <a name="why-cant-linq-automatically-handle-this"></a><span data-ttu-id="7ba9a-142">LINQ를 사용하여 이 문제를 자동으로 처리할 수 없는 이유</span><span class="sxs-lookup"><span data-stu-id="7ba9a-142">Why Can't LINQ Automatically Handle This?</span></span>  
 <span data-ttu-id="7ba9a-143">한 가지 방법은 지연 계산을 수행하는 대신 항상 모든 항목을 메모리에 가져오는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-143">One approach would be to always bring everything into memory instead of doing lazy evaluation.</span></span> <span data-ttu-id="7ba9a-144">그러나 이 방법은 성능과 메모리 사용 측면에서 비용이 매우 많이 듭니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-144">However, it would be very expensive in terms of performance and memory use.</span></span> <span data-ttu-id="7ba9a-145">LINQ와 (LINQ to XML)이 이 방법을 사용한다면 실제 상황에서 제대로 작동하지 않을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-145">In fact, if LINQ and (LINQ to XML) were to take this approach, it would fail in real-world situations.</span></span>  
  
 <span data-ttu-id="7ba9a-146">또 다른 가능한 방법은 트랜잭션 구문을 LINQ에 삽입한 다음 컴파일러에서 코드를 분석하고 특정 컬렉션이 구체화되어야 했는지 확인하도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-146">Another possible approach would be to put in some sort of transaction syntax into LINQ, and have the compiler attempt to analyze the code and determine if any particular collection needed to be materialized.</span></span> <span data-ttu-id="7ba9a-147">그러나 의도하지 않은 결과를 발생시키는 모든 코드를 확인하는 작업은 상당히 복잡합니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-147">However, attempting to determine all code that has side-effects is incredibly complex.</span></span> <span data-ttu-id="7ba9a-148">다음 코드를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-148">Consider the following code:</span></span>  
  
```csharp  
var z =  
    from e in root.Elements()  
    where TestSomeCondition(e)  
    select DoMyProjection(e);  
```  
  
 <span data-ttu-id="7ba9a-149">이러한 분석 코드에서는 TestSomeCondition 및 DoMyProjection 메서드를 분석하고 이러한 메서드가 호출한 모든 메서드를 분석하여 의도하지 않은 결과를 발생시킨 코드가 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-149">Such analysis code would need to analyze the methods TestSomeCondition and DoMyProjection, and all methods that those methods called, to determine if any code had side-effects.</span></span> <span data-ttu-id="7ba9a-150">그러나 이 분석 코드에서는 의도하지 않은 결과를 발생시킨 코드를 찾기만 할 수는 없으며</span><span class="sxs-lookup"><span data-stu-id="7ba9a-150">But the analysis code could not just look for any code that had side-effects.</span></span> <span data-ttu-id="7ba9a-151">이 상황에서 `root`의 자식 요소에 의도하지 않은 결과를 발생시킨 코드를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-151">It would need to select for just the code that had side-effects on the child elements of `root` in this situation.</span></span>  
  
 <span data-ttu-id="7ba9a-152">LINQ to XML에서는 이러한 분석을 수행하려고 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-152">LINQ to XML does not attempt to do any such analysis.</span></span>  
  
 <span data-ttu-id="7ba9a-153">이러한 문제를 방지하는 것은 사용자의 책임입니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-153">It is up to you to avoid these problems.</span></span>  
  
## <a name="guidance"></a><span data-ttu-id="7ba9a-154">지침</span><span class="sxs-lookup"><span data-stu-id="7ba9a-154">Guidance</span></span>  
 <span data-ttu-id="7ba9a-155">첫째, 선언적 코드와 명령적 코드를 혼합하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-155">First, do not mix declarative and imperative code.</span></span>  
  
 <span data-ttu-id="7ba9a-156">컬렉션의 의미와 XML 트리를 수정하는 메서드의 의미를 정확히 파악하고 이러한 범주의 문제를 방지하는 효과적인 코드를 작성하는 경우에도 향후 다른 개발자가 해당 코드를 유지 관리해야 할 때 이 문제를 명확히 이해하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-156">Even if you know exactly the semantics of your collections and the semantics of the methods that modify the XML tree, if you write some clever code that avoids these categories of problems, your code will need to be maintained by other developers in the future, and they may not be as clear on the issues.</span></span> <span data-ttu-id="7ba9a-157">선언적 코딩 스타일과 명령적 코딩 스타일을 혼합하면 코드가 더욱 불안정해집니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-157">If you mix declarative and imperative coding styles, your code will be more brittle.</span></span>  
  
 <span data-ttu-id="7ba9a-158">이러한 문제가 방지되도록 컬렉션을 구체화하는 코드를 작성하는 경우 코드에 이 문제에 대한 주석을 삽입하여 유지 관리 프로그래머가 이 문제를 이해하도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-158">If you write code that materializes a collection so that these problems are avoided, note it with comments as appropriate in your code, so that maintenance programmers will understand the issue.</span></span>  
  
 <span data-ttu-id="7ba9a-159">둘째, 성능과 다른 고려 사항이 허용하는 경우 선언적 코드만 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-159">Second, if performance and other considerations allow, use only declarative code.</span></span> <span data-ttu-id="7ba9a-160">기존 XML 트리는 수정하지 말고</span><span class="sxs-lookup"><span data-stu-id="7ba9a-160">Don't modify your existing XML tree.</span></span> <span data-ttu-id="7ba9a-161">새 XML 트리를 생성하세요.</span><span class="sxs-lookup"><span data-stu-id="7ba9a-161">Generate a new one.</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("A", "1"),  
    new XElement("B", "2"),  
    new XElement("C", "3")  
);  
XElement newRoot = new XElement("Root",  
    root.Elements(),  
    root.Elements()  
);  
Console.WriteLine(newRoot);  
```  
  
## <a name="see-also"></a><span data-ttu-id="7ba9a-162">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7ba9a-162">See Also</span></span>  
 [<span data-ttu-id="7ba9a-163">고급 LINQ to XML 프로그래밍(C#)</span><span class="sxs-lookup"><span data-stu-id="7ba9a-163">Advanced LINQ to XML Programming (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
