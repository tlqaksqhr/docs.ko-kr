---
title: "C#에서 XML 트리 만들기(LINQ to XML)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: cc74234a-0bac-4327-9c8c-5a2ead15b595
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ac95fcf49736b554c8a3d4d0061f63b3ac4d3f65
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="creating-xml-trees-in-c-linq-to-xml"></a><span data-ttu-id="517bf-102">C#에서 XML 트리 만들기(LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="517bf-102">Creating XML Trees in C# (LINQ to XML)</span></span>
<span data-ttu-id="517bf-103">이 단원에서는 C#에서 XML 트리를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-103">This section provides information about creating XML trees in C#.</span></span>  
  
 <span data-ttu-id="517bf-104">LINQ 쿼리의 결과를 <xref:System.Xml.Linq.XElement>의 내용으로 사용하는 방법에 대한 자세한 내용은 [함수 생성(LINQ to XML)(C#)](../../../../csharp/programming-guide/concepts/linq/functional-construction-linq-to-xml.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="517bf-104">For information about using the results of LINQ queries as the content for an <xref:System.Xml.Linq.XElement>, see [Functional Construction (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/functional-construction-linq-to-xml.md).</span></span>  
  
## <a name="constructing-elements"></a><span data-ttu-id="517bf-105">요소 생성</span><span class="sxs-lookup"><span data-stu-id="517bf-105">Constructing Elements</span></span>  
 <span data-ttu-id="517bf-106"><xref:System.Xml.Linq.XElement> 및 <xref:System.Xml.Linq.XAttribute> 생성자의 시그니처를 사용하여 요소나 특성의 내용을 생성자에 인수로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-106">The signatures of the <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XAttribute> constructors let you pass the contents of the element or attribute as arguments to the constructor.</span></span> <span data-ttu-id="517bf-107">생성자 중 하나의 인수 수가 고정되어 있지 않기 때문에 원하는 수의 자식 요소를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-107">Because one of the constructors takes a variable number of arguments, you can pass any number of child elements.</span></span> <span data-ttu-id="517bf-108">물론 이러한 각 자식 요소에는 자신의 자식 요소가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-108">Of course, each of those child elements can contain their own child elements.</span></span> <span data-ttu-id="517bf-109">각 요소에는 원하는 수의 특성을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-109">For any element, you can add any number of attributes.</span></span>  
  
 <span data-ttu-id="517bf-110"><xref:System.Xml.Linq.XNode>(<xref:System.Xml.Linq.XElement> 포함) 또는 <xref:System.Xml.Linq.XAttribute> 개체를 추가할 때 새 내용에 부모가 없으면 개체가 XML 트리에 추가되기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-110">When adding <xref:System.Xml.Linq.XNode> (including <xref:System.Xml.Linq.XElement>) or <xref:System.Xml.Linq.XAttribute> objects, if the new content has no parent, the objects are simply attached to the XML tree.</span></span> <span data-ttu-id="517bf-111">새 내용에 이미 부모가 있고 다른 XML 트리의 일부이면 새 내용이 복제되고 새로 복제된 내용이 XML 트리에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-111">If the new content already is parented, and is part of another XML tree, the new content is cloned, and the newly cloned content is attached to the XML tree.</span></span> <span data-ttu-id="517bf-112">이 항목의 마지막 예제에서는 이에 대해 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-112">The last example in this topic demonstrates this.</span></span>  
  
 <span data-ttu-id="517bf-113">`contacts`<xref:System.Xml.Linq.XElement>를 만들려면 다음 코드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-113">To create a `contacts`<xref:System.Xml.Linq.XElement>, you could use the following code:</span></span>  
  
```csharp  
XElement contacts =  
    new XElement("Contacts",  
        new XElement("Contact",  
            new XElement("Name", "Patrick Hines"),   
            new XElement("Phone", "206-555-0144"),  
            new XElement("Address",  
                new XElement("Street1", "123 Main St"),  
                new XElement("City", "Mercer Island"),  
                new XElement("State", "WA"),  
                new XElement("Postal", "68042")  
            )  
        )  
    );  
```  
  
 <span data-ttu-id="517bf-114">제대로 들여쓰는 경우 <xref:System.Xml.Linq.XElement> 개체를 생성하는 코드는 기본 XML의 구조와 매우 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-114">If indented properly, the code to construct <xref:System.Xml.Linq.XElement> objects closely resembles the structure of the underlying XML.</span></span>  
  
## <a name="xelement-constructors"></a><span data-ttu-id="517bf-115">XElement 생성자</span><span class="sxs-lookup"><span data-stu-id="517bf-115">XElement Constructors</span></span>  
 <span data-ttu-id="517bf-116"><xref:System.Xml.Linq.XElement> 클래스는 함수 생성을 위해 다음 생성자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-116">The <xref:System.Xml.Linq.XElement> class uses the following constructors for functional construction.</span></span> <span data-ttu-id="517bf-117"><xref:System.Xml.Linq.XElement>의 다른 생성자도 있지만 함수 생성에 사용되지 않기 때문에 여기에 나와 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-117">Note that there are some other constructors for <xref:System.Xml.Linq.XElement>, but because they are not used for functional construction they are not listed here.</span></span>  
  
|<span data-ttu-id="517bf-118">생성자</span><span class="sxs-lookup"><span data-stu-id="517bf-118">Constructor</span></span>|<span data-ttu-id="517bf-119">설명</span><span class="sxs-lookup"><span data-stu-id="517bf-119">Description</span></span>|  
|-----------------|-----------------|  
|`XElement(XName name, object content)`|<span data-ttu-id="517bf-120"><xref:System.Xml.Linq.XElement>를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-120">Creates an <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="517bf-121">`name` 매개 변수는 요소의 이름을 지정하고, `content`는 요소의 내용을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-121">The `name` parameter specifies the name of the element; `content` specifies the content of the element.</span></span>|  
|`XElement(XName name)`|<span data-ttu-id="517bf-122"><xref:System.Xml.Linq.XElement>을 지정된 이름으로 초기화하여 <xref:System.Xml.Linq.XName>를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-122">Creates an <xref:System.Xml.Linq.XElement> with its <xref:System.Xml.Linq.XName> initialized to the specified name.</span></span>|  
|`XElement(XName name, params object[] content)`|<span data-ttu-id="517bf-123"><xref:System.Xml.Linq.XElement>을 지정된 이름으로 초기화하여 <xref:System.Xml.Linq.XName>를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-123">Creates an <xref:System.Xml.Linq.XElement> with its <xref:System.Xml.Linq.XName> initialized to the specified name.</span></span> <span data-ttu-id="517bf-124">특성 및/또는 자식 요소는 매개 변수 목록의 내용에서 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-124">The attributes and/or child elements are created from the contents of the parameter list.</span></span>|  
  
 <span data-ttu-id="517bf-125">`content` 매개 변수는 융통성이 매우 크기 때문에</span><span class="sxs-lookup"><span data-stu-id="517bf-125">The `content` parameter is extremely flexible.</span></span> <span data-ttu-id="517bf-126"><xref:System.Xml.Linq.XElement>의 유효한 자식인 모든 형식의 개체를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-126">It supports any type of object that is a valid child of an <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="517bf-127">이 매개 변수로 전달되는 개체의 형식에 따라 다음과 같은 규칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-127">The following rules apply to different types of objects passed in this parameter:</span></span>  
  
-   <span data-ttu-id="517bf-128">문자열은 텍스트 내용으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-128">A string is added as text content.</span></span>  
  
-   <span data-ttu-id="517bf-129"><xref:System.Xml.Linq.XElement>는 자식 요소로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-129">An <xref:System.Xml.Linq.XElement> is added as a child element.</span></span>  
  
-   <span data-ttu-id="517bf-130"><xref:System.Xml.Linq.XAttribute>는 특성으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-130">An <xref:System.Xml.Linq.XAttribute> is added as an attribute.</span></span>  
  
-   <span data-ttu-id="517bf-131"><xref:System.Xml.Linq.XProcessingInstruction>, <xref:System.Xml.Linq.XComment> 또는 <xref:System.Xml.Linq.XText>는 자식 내용으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-131">An <xref:System.Xml.Linq.XProcessingInstruction>, <xref:System.Xml.Linq.XComment>, or <xref:System.Xml.Linq.XText> is added as child content.</span></span>  
  
-   <span data-ttu-id="517bf-132"><xref:System.Collections.IEnumerable>이 열거되고 이러한 규칙이 결과에 재귀적으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-132">An <xref:System.Collections.IEnumerable> is enumerated, and these rules are applied recursively to the results.</span></span>  
  
-   <span data-ttu-id="517bf-133">다른 모든 형식의 경우 `ToString` 메서드가 호출되고 결과가 텍스트 내용으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-133">For any other type, its `ToString` method is called and the result is added as text content.</span></span>  
  
### <a name="creating-an-xelement-with-content"></a><span data-ttu-id="517bf-134">내용을 사용하여 XElement 만들기</span><span class="sxs-lookup"><span data-stu-id="517bf-134">Creating an XElement with Content</span></span>  
 <span data-ttu-id="517bf-135">메서드를 한 번 호출하여 간단한 내용이 포함된 <xref:System.Xml.Linq.XElement>를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-135">You can create an <xref:System.Xml.Linq.XElement> that contains simple content with a single method call.</span></span> <span data-ttu-id="517bf-136">이렇게 하려면 다음과 같이 내용을 두 번째 매개 변수로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-136">To do this, specify the content as the second parameter, as follows:</span></span>  
  
```csharp  
XElement n = new XElement("Customer", "Adventure Works");  
Console.WriteLine(n);  
```  
  
 <span data-ttu-id="517bf-137">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-137">This example produces the following output:</span></span>  
  
```xml  
<Customer>Adventure Works</Customer>  
```  
  
 <span data-ttu-id="517bf-138">모든 형식의 개체를 내용으로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-138">You can pass any type of object as the content.</span></span> <span data-ttu-id="517bf-139">예를 들어, 다음 코드에서는 부동 소수점 숫자가 내용으로 포함된 요소를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-139">For example, the following code creates an element that contains a floating point number as content:</span></span>  
  
```csharp  
XElement n = new XElement("Cost", 324.50);  
Console.WriteLine(n);  
```  
  
 <span data-ttu-id="517bf-140">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-140">This example produces the following output:</span></span>  
  
```xml  
<Cost>324.5</Cost>  
```  
  
 <span data-ttu-id="517bf-141">부동 소수점 숫자는 boxing되어 생성자에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-141">The floating point number is boxed and passed in to the constructor.</span></span> <span data-ttu-id="517bf-142">boxed 숫자는 문자열로 변환되고 요소의 내용으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-142">The boxed number is converted to a string and used as the content of the element.</span></span>  
  
### <a name="creating-an-xelement-with-a-child-element"></a><span data-ttu-id="517bf-143">자식 요소를 사용하여 XElement 만들기</span><span class="sxs-lookup"><span data-stu-id="517bf-143">Creating an XElement with a Child Element</span></span>  
 <span data-ttu-id="517bf-144"><xref:System.Xml.Linq.XElement> 클래스의 인스턴스를 내용 인수로 전달하면 생성자가 자식 요소를 사용하여 요소를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-144">If you pass an instance of the <xref:System.Xml.Linq.XElement> class for the content argument, the constructor creates an element with a child element:</span></span>  
  
```csharp  
XElement shippingUnit = new XElement("ShippingUnit",  
    new XElement("Cost", 324.50)  
);  
Console.WriteLine(shippingUnit);  
```  
  
 <span data-ttu-id="517bf-145">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-145">This example produces the following output:</span></span>  
  
```xml  
<ShippingUnit>  
  <Cost>324.5</Cost>  
</ShippingUnit>  
```  
  
### <a name="creating-an-xelement-with-multiple-child-elements"></a><span data-ttu-id="517bf-146">여러 자식 요소를 사용하여 XElement 만들기</span><span class="sxs-lookup"><span data-stu-id="517bf-146">Creating an XElement with Multiple Child Elements</span></span>  
 <span data-ttu-id="517bf-147">많은 <xref:System.Xml.Linq.XElement> 개체를 내용으로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-147">You can pass in a number of <xref:System.Xml.Linq.XElement> objects for the content.</span></span> <span data-ttu-id="517bf-148">각 <xref:System.Xml.Linq.XElement> 개체는 자식 요소로 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-148">Each of the <xref:System.Xml.Linq.XElement> objects is included as a child element.</span></span>  
  
```csharp  
XElement address = new XElement("Address",  
    new XElement("Street1", "123 Main St"),  
    new XElement("City", "Mercer Island"),  
    new XElement("State", "WA"),  
    new XElement("Postal", "68042")  
);  
Console.WriteLine(address);  
```  
  
 <span data-ttu-id="517bf-149">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-149">This example produces the following output:</span></span>  
  
```xml  
<Address>  
  <Street1>123 Main St</Street1>  
  <City>Mercer Island</City>  
  <State>WA</State>  
  <Postal>68042</Postal>  
</Address>  
```  
  
 <span data-ttu-id="517bf-150">위의 예제를 확장하여 다음과 같이 전체 XML 트리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-150">By extending the above example, you can create an entire XML tree, as follows:</span></span>  
  
```csharp  
XElement contacts =  
    new XElement("Contacts",  
        new XElement("Contact",  
            new XElement("Name", "Patrick Hines"),                                                   
            new XElement("Phone", "206-555-0144"),  
            new XElement("Address",  
                new XElement("Street1", "123 Main St"),  
                new XElement("City", "Mercer Island"),  
                new XElement("State", "WA"),  
                new XElement("Postal", "68042")  
            )  
        )  
    );  
Console.WriteLine(contacts);  
```  
  
 <span data-ttu-id="517bf-151">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-151">This example produces the following output:</span></span>  
  
```xml  
<Contacts>  
  <Contact>  
    <Name>Patrick Hines</Name>  
    <Phone>206-555-0144</Phone>  
    <Address>  
      <Street1>123 Main St</Street1>  
      <City>Mercer Island</City>  
      <State>WA</State>  
      <Postal>68042</Postal>  
    </Address>  
  </Contact>  
</Contacts>  
```  
  
### <a name="creating-an-empty-element"></a><span data-ttu-id="517bf-152">빈 요소 만들기</span><span class="sxs-lookup"><span data-stu-id="517bf-152">Creating an Empty Element</span></span>  
 <span data-ttu-id="517bf-153">빈 <xref:System.Xml.Linq.XElement>를 만들려면 내용을 생성자에 전달하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-153">To create an empty <xref:System.Xml.Linq.XElement>, you do not pass any content to the constructor.</span></span> <span data-ttu-id="517bf-154">다음 예제에서는 빈 요소를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-154">The following example creates an empty element:</span></span>  
  
```csharp  
XElement n = new XElement("Customer");  
Console.WriteLine(n);  
```  
  
 <span data-ttu-id="517bf-155">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-155">This example produces the following output:</span></span>  
  
```xml  
<Customer />  
```  
  
### <a name="attaching-vs-cloning"></a><span data-ttu-id="517bf-156">추가와 복제 비교</span><span class="sxs-lookup"><span data-stu-id="517bf-156">Attaching vs. Cloning</span></span>  
 <span data-ttu-id="517bf-157">위에서 설명했듯이 <xref:System.Xml.Linq.XNode>(<xref:System.Xml.Linq.XElement> 포함) 또는 <xref:System.Xml.Linq.XAttribute> 개체를 추가할 때 새 내용에 부모가 없으면 개체가 XML 트리에 추가되기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-157">As mentioned previously, when adding <xref:System.Xml.Linq.XNode> (including <xref:System.Xml.Linq.XElement>) or <xref:System.Xml.Linq.XAttribute> objects, if the new content has no parent, the objects are simply attached to the XML tree.</span></span> <span data-ttu-id="517bf-158">새 내용에 이미 부모가 있고 다른 XML 트리의 일부이면 새 내용이 복제되고 새로 복제된 내용이 XML 트리에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-158">If the new content already is parented and is part of another XML tree, the new content is cloned, and the newly cloned content is attached to the XML tree.</span></span>  
  
```csharp  
// Create a tree with a child element.  
XElement xmlTree1 = new XElement("Root",  
    new XElement("Child1", 1)  
);  
  
// Create an element that is not parented.  
XElement child2 = new XElement("Child2", 2);  
  
// Create a tree and add Child1 and Child2 to it.  
XElement xmlTree2 = new XElement("Root",  
    xmlTree1.Element("Child1"),  
    child2  
);  
  
// Compare Child1 identity.  
Console.WriteLine("Child1 was {0}",  
    xmlTree1.Element("Child1") == xmlTree2.Element("Child1") ?  
    "attached" : "cloned");  
  
// Compare Child2 identity.  
Console.WriteLine("Child2 was {0}",  
    child2 == xmlTree2.Element("Child2") ?  
    "attached" : "cloned");  
```  
  
 <span data-ttu-id="517bf-159">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="517bf-159">This example produces the following output:</span></span>  
  
```  
Child1 was cloned  
Child2 was attached  
```  
  
## <a name="see-also"></a><span data-ttu-id="517bf-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="517bf-160">See Also</span></span>  
 [<span data-ttu-id="517bf-161">XML 트리 만들기(C#)</span><span class="sxs-lookup"><span data-stu-id="517bf-161">Creating XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md)

