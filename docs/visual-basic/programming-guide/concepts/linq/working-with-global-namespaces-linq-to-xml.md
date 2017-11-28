---
title: "전역 네임스페이스 작업(Visual Basic)(LINQ to XML)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0a8064d5-e02f-4315-ad48-6deaa443a2f0
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 376a6d2dfbca22fb8efc6395f478839d716e14d4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="working-with-global-namespaces-visual-basic-linq-to-xml"></a><span data-ttu-id="a68b2-102">전역 네임스페이스 작업(Visual Basic)(LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="a68b2-102">Working with Global Namespaces (Visual Basic) (LINQ to XML)</span></span>
<span data-ttu-id="a68b2-103">사용 하 여 XML 네임 스페이스를 선언 하는 기능에는 Visual Basic에서 XML 리터럴의 주요 기능 중 하나는 `Imports` 문.</span><span class="sxs-lookup"><span data-stu-id="a68b2-103">One of the key features of XML literals in Visual Basic is the capability to declare XML namespaces by using the `Imports` statement.</span></span> <span data-ttu-id="a68b2-104">이 기능을 사용하여 접두사를 사용하는 XML 네임스페이스를 선언하거나 기본 XML 네임스페이스를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a68b2-104">Using this feature, you can declare an XML namespace that uses a prefix, or you can declare a default XML namespace.</span></span>  
  
 <span data-ttu-id="a68b2-105">이 기능은 두 가지 상황에서 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="a68b2-105">This capability is useful in two situations.</span></span> <span data-ttu-id="a68b2-106">첫째, XML 리터럴에서 선언된 네임스페이스는 포함 식에까지 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a68b2-106">First, namespaces declared in XML literals do not carry over into embedded expressions.</span></span> <span data-ttu-id="a68b2-107">전역 네임스페이스를 선언하면 네임스페이스와 함께 포함 식을 사용하기 위해 수행해야 하는 작업량이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="a68b2-107">Declaring global namespaces reduces the amount of work that you have to do to use embedded expressions with namespaces.</span></span> <span data-ttu-id="a68b2-108">둘째, XML 속성과 함께 네임스페이스를 사용하기 위해 전역 네임스페이스를 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a68b2-108">Second, you must declare global namespaces in order to use namespaces with XML properties.</span></span>  
  
 <span data-ttu-id="a68b2-109">프로젝트 수준에서 전역 네임스페이스를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a68b2-109">You can declare global namespaces at the project level.</span></span> <span data-ttu-id="a68b2-110">또한 모듈 수준에서 전역 네임스페이스를 선언할 수도 있습니다. 모듈 수준 전역 네임스페이스는 프로젝트 수준 전역 네임스페이스를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="a68b2-110">You can also declare global namespaces at the module level, which overrides the project-level global namespaces.</span></span> <span data-ttu-id="a68b2-111">마지막으로 XML 리터럴에서 전역 네임스페이스를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a68b2-111">Finally, you can override global namespaces in an XML literal.</span></span>  
  
 <span data-ttu-id="a68b2-112">전역적으로 선언된 네임스페이스에 있는 XML 속성이나 XML 리터럴을 사용하는 경우 Visual Studio에서 XML 속성이나 XML 리터럴을 마우스로 가리키면 확장된 이름을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a68b2-112">When using XML literals or XML properties that are in globally-declared namespaces, you can see the expanded name of XML literals or properties by hovering over them in Visual Studio.</span></span> <span data-ttu-id="a68b2-113">도구 설명에 확장된 이름이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a68b2-113">You will see the expanded name in a tooltip.</span></span>  
  
 <span data-ttu-id="a68b2-114"><xref:System.Xml.Linq.XNamespace> 메서드를 사용하여 전역 네임스페이스에 해당하는 `GetXmlNamespace` 개체를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a68b2-114">You can get an <xref:System.Xml.Linq.XNamespace> object that corresponds to a global namespace using the `GetXmlNamespace` method.</span></span>  
  
## <a name="examples-of-global-namespaces"></a><span data-ttu-id="a68b2-115">전역 네임스페이스의 예제</span><span class="sxs-lookup"><span data-stu-id="a68b2-115">Examples of Global Namespaces</span></span>  
 <span data-ttu-id="a68b2-116">다음 예제에서는 `Imports` 문을 사용하여 기본 전역 네임스페이스를 선언한 다음 XML 리터럴을 사용하여 해당 네임스페이스에서 <xref:System.Xml.Linq.XElement> 개체를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="a68b2-116">The following example declares a default global namespace by using the `Imports` statement, and then uses an XML literal to initialize an <xref:System.Xml.Linq.XElement> object in that namespace:</span></span>  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <Root/>  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="a68b2-117">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a68b2-117">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com" />  
```  
  
 <span data-ttu-id="a68b2-118">다음 예제에서는 접두사가 포함된 전역 네임스페이스를 선언한 다음 XML 리터럴을 사용하여 요소를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="a68b2-118">The following example declares a global namespace with a prefix, and then uses an XML literal to initialize an element:</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <aw:Root/>  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="a68b2-119">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a68b2-119">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com" />  
```  
  
## <a name="global-namespaces-and-embedded-expressions"></a><span data-ttu-id="a68b2-120">전역 네임스페이스 및 포함 식</span><span class="sxs-lookup"><span data-stu-id="a68b2-120">Global Namespaces and Embedded Expressions</span></span>  
 <span data-ttu-id="a68b2-121">XML 리터럴에서 선언된 네임스페이스는 포함 식에까지 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a68b2-121">Namespaces that are declared in XML literals do not carry over into embedded expressions.</span></span> <span data-ttu-id="a68b2-122">다음 예제에서는 기본 네임스페이스를 선언한 다음</span><span class="sxs-lookup"><span data-stu-id="a68b2-122">The following example declares a default namespace.</span></span> <span data-ttu-id="a68b2-123">`Child` 요소에 대한 포함 식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a68b2-123">It then uses an embedded expression for the `Child` element.</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root xmlns="http://www.adventure-works.com">  
        <%= <Child/> %>  
    </Root>  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="a68b2-124">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a68b2-124">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com">  
  <Child xmlns="" />  
</Root>  
```  
  
 <span data-ttu-id="a68b2-125">보다시피 생성되는 XML에는 기본 네임스페이스의 선언이 포함됩니다. 따라서 `Child` 요소는 네임스페이스에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a68b2-125">As you can see, the resulting XML includes a declaration of a default namespace so that the `Child` element is in no namespace.</span></span>  
  
 <span data-ttu-id="a68b2-126">포함 식에서 다음과 같이 네임스페이스를 다시 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a68b2-126">You could re-declare the namespace in the embedded expression, as follows:</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root xmlns="http://www.adventure-works.com">  
        <%= <Child xmlns="http://www.adventure-works.com"/> %>  
    </Root>  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="a68b2-127">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a68b2-127">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com">  
  <Child xmlns="http://www.adventure-works.com" />  
</Root>  
```  
  
 <span data-ttu-id="a68b2-128">그러나 이 방법은 전역 기본 네임스페이스보다 사용하기가 더 불편합니다. 따라서 전역 기본 네임스페이스를 사용하는 것이 더 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a68b2-128">However, this is more cumbersome to use than the global default namespace, which is a better approach.</span></span> <span data-ttu-id="a68b2-129">전역 기본 네임스페이스를 사용하면 네임스페이스를 선언하지 않고 XML 리터럴을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a68b2-129">With the global default namespace, you can use XML literals without declaring namespaces.</span></span> <span data-ttu-id="a68b2-130">생성되는 XML은 전역적으로 선언된 기본 네임스페이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a68b2-130">The resulting XML will be in the globally-declared default namespace.</span></span>  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <Root>  
                                   <%= <Child/> %>  
                               </Root>  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="a68b2-131">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a68b2-131">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com">  
  <Child />  
</Root>  
```  
  
## <a name="using-namespaces-with-xml-properties"></a><span data-ttu-id="a68b2-132">XML 속성과 함께 네임스페이스 사용</span><span class="sxs-lookup"><span data-stu-id="a68b2-132">Using Namespaces with XML Properties</span></span>  
 <span data-ttu-id="a68b2-133">네임스페이스에 있는 XML 트리로 작업하는 경우 XML 속성을 사용하고 있으면 XML 속성도 올바른 네임스페이스에 있도록 전역 네임스페이스를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a68b2-133">If you are working with an XML tree that is in a namespace, and you use XML properties, then you must use a global namespace so that the XML properties will also be in the correct namespace.</span></span> <span data-ttu-id="a68b2-134">다음 예제에서는 네임스페이스에 XML 트리를 선언한 다음</span><span class="sxs-lookup"><span data-stu-id="a68b2-134">The following example declares an XML tree in a namespace.</span></span> <span data-ttu-id="a68b2-135">`Child` 요소의 수를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="a68b2-135">It then prints the count of `Child` elements.</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root xmlns="http://www.adventure-works.com">  
        <Child>content</Child>  
    </Root>  
Console.WriteLine(root.<Child>.Count())  
```  
  
 <span data-ttu-id="a68b2-136">이 예제는 `Child` 요소가 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a68b2-136">This example indicates that there are no `Child` elements.</span></span> <span data-ttu-id="a68b2-137">이 예제의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a68b2-137">It produces the following output:</span></span>  
  
```  
0  
```  
  
 <span data-ttu-id="a68b2-138">그러나 기본 전역 네임스페이스를 선언하는 경우 XML 리터럴과 XML 속성이 모두 기본 전역 네임스페이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a68b2-138">If, however, you declare a default global namespace, then both the XML literal and the XML property are in the default global namespace:</span></span>  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root>  
                <Child>content</Child>  
            </Root>  
        Console.WriteLine(root.<Child>.Count())  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="a68b2-139">이 예제는 `Child` 요소가 하나 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a68b2-139">This example indicates that there is one `Child` element.</span></span> <span data-ttu-id="a68b2-140">이 예제의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a68b2-140">It produces the following output:</span></span>  
  
```  
1  
```  
  
 <span data-ttu-id="a68b2-141">접두사가 포함된 전역 네임스페이스를 선언하면 XML 리터럴과 XML 속성 모두에 접두사를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a68b2-141">If you declare a global namespace that has a prefix, you can use the prefix for both XML literals and XML properties:</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <aw:Child>content</aw:Child>  
            </aw:Root>  
        Console.WriteLine(root.<aw:Child>.Count())  
    End Sub  
End Module  
```  
  
## <a name="xnamespace-and-global-namespaces"></a><span data-ttu-id="a68b2-142">XNamespace 및 전역 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="a68b2-142">XNamespace and Global Namespaces</span></span>  
 <span data-ttu-id="a68b2-143"><xref:System.Xml.Linq.XNamespace> 메서드를 사용하여 `GetXmlNamespace` 개체를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a68b2-143">You can get an <xref:System.Xml.Linq.XNamespace> object by using the `GetXmlNamespace` method:</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <aw:Root/>  
        Dim xn As XNamespace = GetXmlNamespace(aw)  
        Console.WriteLine(xn)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="a68b2-144">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a68b2-144">This example produces the following output:</span></span>  
  
```  
http://www.adventure-works.com  
```  
  
## <a name="see-also"></a><span data-ttu-id="a68b2-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a68b2-145">See Also</span></span>  
 [<span data-ttu-id="a68b2-146">XML 네임 스페이스 (Visual Basic) 작업</span><span class="sxs-lookup"><span data-stu-id="a68b2-146">Working with XML Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
