---
title: "XAttribute 클래스 개요(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 5a630f24-f9ad-400e-831e-c14ebfc9e142
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e9cfedb476f44ef8c3eaeb45bac571d17802d525
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="xattribute-class-overview-c"></a><span data-ttu-id="d23cd-102">XAttribute 클래스 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="d23cd-102">XAttribute Class Overview (C#)</span></span>
<span data-ttu-id="d23cd-103">특성은 요소와 연결된 이름/값 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="d23cd-103">Attributes are name/value pairs that are associated with an element.</span></span> <span data-ttu-id="d23cd-104"><xref:System.Xml.Linq.XAttribute> 클래스는 XML 특성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d23cd-104">The <xref:System.Xml.Linq.XAttribute> class represents XML attributes.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="d23cd-105">개요</span><span class="sxs-lookup"><span data-stu-id="d23cd-105">Overview</span></span>  
 <span data-ttu-id="d23cd-106">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]에서 특성 작업은 요소 작업과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="d23cd-106">Working with attributes in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is similar to working with elements.</span></span> <span data-ttu-id="d23cd-107">특성과 요소의 생성자는 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="d23cd-107">Their constructors are similar.</span></span> <span data-ttu-id="d23cd-108">특성과 요소의 컬렉션을 검색하는 데 사용하는 메서드는 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="d23cd-108">The methods that you use to retrieve collections of them are similar.</span></span> <span data-ttu-id="d23cd-109">특성 컬렉션의 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리 식은 요소 컬렉션의 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리 식과 매우 유사하게 보입니다.</span><span class="sxs-lookup"><span data-stu-id="d23cd-109">A [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expression for a collection of attributes looks very similar to a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expression for a collection of elements.</span></span>  
  
 <span data-ttu-id="d23cd-110">특성이 요소에 추가된 순서는 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="d23cd-110">The order in which attributes were added to an element is preserved.</span></span> <span data-ttu-id="d23cd-111">즉, 특성을 반복하는 경우 특성은 추가된 동일한 순서로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d23cd-111">That is, when you iterate through the attributes, you see them in the same order that they were added.</span></span>  
  
## <a name="the-xattribute-constructor"></a><span data-ttu-id="d23cd-112">XAttribute 생성자</span><span class="sxs-lookup"><span data-stu-id="d23cd-112">The XAttribute Constructor</span></span>  
 <span data-ttu-id="d23cd-113"><xref:System.Xml.Linq.XAttribute> 클래스의 다음 생성자는 가장 일반적으로 사용하는 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="d23cd-113">The following constructor of the <xref:System.Xml.Linq.XAttribute> class is the one that you will most commonly use:</span></span>  
  
|<span data-ttu-id="d23cd-114">생성자</span><span class="sxs-lookup"><span data-stu-id="d23cd-114">Constructor</span></span>|<span data-ttu-id="d23cd-115">설명</span><span class="sxs-lookup"><span data-stu-id="d23cd-115">Description</span></span>|  
|-----------------|-----------------|  
|`XAttribute(XName name, object content)`|<span data-ttu-id="d23cd-116"><xref:System.Xml.Linq.XAttribute> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d23cd-116">Creates an <xref:System.Xml.Linq.XAttribute> object.</span></span> <span data-ttu-id="d23cd-117">`name` 인수는 특성의 이름을 지정하고, `content`는 특성의 내용을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d23cd-117">The `name` argument specifies the name of the attribute; `content` specifies the content of the attribute.</span></span>|  
  
### <a name="creating-an-element-with-an-attribute"></a><span data-ttu-id="d23cd-118">특성을 사용하여 요소 만들기</span><span class="sxs-lookup"><span data-stu-id="d23cd-118">Creating an Element with an Attribute</span></span>  
 <span data-ttu-id="d23cd-119">다음 코드에서는 특성이 포함된 요소를 만드는 일반적인 작업을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d23cd-119">The following code shows the common task of creating an element that contains an attribute:</span></span>  
  
```csharp  
XElement phone = new XElement("Phone",  
    new XAttribute("Type", "Home"),  
    "555-555-5555");  
Console.WriteLine(phone);  
```  
  
 <span data-ttu-id="d23cd-120">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d23cd-120">This example produces the following output:</span></span>  
  
```xml  
<Phone Type="Home">555-555-5555</Phone>  
```  
  
### <a name="functional-construction-of-attributes"></a><span data-ttu-id="d23cd-121">특성의 함수 생성</span><span class="sxs-lookup"><span data-stu-id="d23cd-121">Functional Construction of Attributes</span></span>  
 <span data-ttu-id="d23cd-122"><xref:System.Xml.Linq.XAttribute> 개체의 생성과 함께 다음과 같이 <xref:System.Xml.Linq.XElement> 개체를 인라인으로 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d23cd-122">You can construct <xref:System.Xml.Linq.XAttribute> objects in-line with the construction of <xref:System.Xml.Linq.XElement> objects, as follows:</span></span>  
  
```csharp  
XElement c = new XElement("Customers",  
    new XElement("Customer",  
        new XElement("Name", "John Doe"),  
        new XElement("PhoneNumbers",  
            new XElement("Phone",  
                new XAttribute("type", "home"),  
                "555-555-5555"),  
            new XElement("Phone",  
                new XAttribute("type", "work"),  
                "666-666-6666")  
        )  
    )  
);  
Console.WriteLine(c);  
```  
  
 <span data-ttu-id="d23cd-123">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d23cd-123">This example produces the following output:</span></span>  
  
```xml  
<Customers>  
  <Customer>  
    <Name>John Doe</Name>  
    <PhoneNumbers>  
      <Phone type="home">555-555-5555</Phone>  
      <Phone type="work">666-666-6666</Phone>  
    </PhoneNumbers>  
  </Customer>  
</Customers>  
```  
  
### <a name="attributes-are-not-nodes"></a><span data-ttu-id="d23cd-124">특성은 노드가 아님</span><span class="sxs-lookup"><span data-stu-id="d23cd-124">Attributes Are Not Nodes</span></span>  
 <span data-ttu-id="d23cd-125">특성과 요소 사이에는 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d23cd-125">There are some differences between attributes and elements.</span></span> <span data-ttu-id="d23cd-126"><xref:System.Xml.Linq.XAttribute> 개체는 XML 트리의 노드가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d23cd-126"><xref:System.Xml.Linq.XAttribute> objects are not nodes in the XML tree.</span></span> <span data-ttu-id="d23cd-127">특성은 XML 요소와 연결된 이름/값 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="d23cd-127">They are name/value pairs associated with an XML element.</span></span> <span data-ttu-id="d23cd-128">DOM(문서 개체 모델)과 대조적으로 이는 XML의 구조를 더욱 충실하게 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="d23cd-128">In contrast to the Document Object Model (DOM), this more closely reflects the structure of XML.</span></span> <span data-ttu-id="d23cd-129"><xref:System.Xml.Linq.XAttribute> 개체가 실제로 XML 트리의 노드는 아니지만 <xref:System.Xml.Linq.XAttribute> 개체 작업은 <xref:System.Xml.Linq.XElement> 개체 작업과 매우 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="d23cd-129">Although <xref:System.Xml.Linq.XAttribute> objects are not actually nodes in the XML tree, working with <xref:System.Xml.Linq.XAttribute> objects is very similar to working with <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="d23cd-130">이 차이는 주로 노드 수준에서 XML 트리 작업을 하는 코드를 작성하는 개발자에게만 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="d23cd-130">This distinction is primarily important only to developers who are writing code that works with XML trees at the node level.</span></span> <span data-ttu-id="d23cd-131">대부분의 개발자는 이 차이에 대해 염려하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d23cd-131">Many developers will not be concerned with this distinction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d23cd-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d23cd-132">See Also</span></span>  
 [<span data-ttu-id="d23cd-133">LINQ to XML 프로그래밍 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="d23cd-133">LINQ to XML Programming Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
