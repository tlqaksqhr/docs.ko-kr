---
title: "XAttribute 클래스 개요 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 7781580a-9583-4a1b-ae1e-91c5936eb0b1
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 741e73987a9339a320114d74187c0056c7150924
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="xattribute-class-overview-visual-basic"></a><span data-ttu-id="73e14-102">XAttribute 클래스 개요 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="73e14-102">XAttribute Class Overview (Visual Basic)</span></span>
<span data-ttu-id="73e14-103">특성은 요소와 연결된 이름/값 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="73e14-103">Attributes are name/value pairs that are associated with an element.</span></span> <span data-ttu-id="73e14-104"><xref:System.Xml.Linq.XAttribute>클래스는 XML 특성을 나타냅니다.</xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="73e14-104">The <xref:System.Xml.Linq.XAttribute> class represents XML attributes.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="73e14-105">개요</span><span class="sxs-lookup"><span data-stu-id="73e14-105">Overview</span></span>  
 <span data-ttu-id="73e14-106">[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]에서 특성 작업은 요소 작업과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="73e14-106">Working with attributes in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] is similar to working with elements.</span></span> <span data-ttu-id="73e14-107">특성과 요소의 생성자는 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="73e14-107">Their constructors are similar.</span></span> <span data-ttu-id="73e14-108">특성과 요소의 컬렉션을 검색하는 데 사용하는 메서드는 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="73e14-108">The methods that you use to retrieve collections of them are similar.</span></span> <span data-ttu-id="73e14-109">특성 컬렉션의 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 쿼리 식은 요소 컬렉션의 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 쿼리 식과 매우 유사하게 보입니다.</span><span class="sxs-lookup"><span data-stu-id="73e14-109">A [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] query expression for a collection of attributes looks very similar to a [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] query expression for a collection of elements.</span></span>  
  
 <span data-ttu-id="73e14-110">특성이 요소에 추가된 순서는 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="73e14-110">The order in which attributes were added to an element is preserved.</span></span> <span data-ttu-id="73e14-111">즉, 특성을 반복하는 경우 특성은 추가된 동일한 순서로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="73e14-111">That is, when you iterate through the attributes, you see them in the same order that they were added.</span></span>  
  
## <a name="the-xattribute-constructor"></a><span data-ttu-id="73e14-112">XAttribute 생성자</span><span class="sxs-lookup"><span data-stu-id="73e14-112">The XAttribute Constructor</span></span>  
 <span data-ttu-id="73e14-113">다음 생성자는 <xref:System.Xml.Linq.XAttribute>클래스는 가장 일반적으로 사용 합니다:</xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="73e14-113">The following constructor of the <xref:System.Xml.Linq.XAttribute> class is the one that you will most commonly use:</span></span>  
  
|<span data-ttu-id="73e14-114">생성자</span><span class="sxs-lookup"><span data-stu-id="73e14-114">Constructor</span></span>|<span data-ttu-id="73e14-115">설명</span><span class="sxs-lookup"><span data-stu-id="73e14-115">Description</span></span>|  
|-----------------|-----------------|  
|`XAttribute(XName name, object content)`|<span data-ttu-id="73e14-116">만듭니다는 <xref:System.Xml.Linq.XAttribute>개체.</xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="73e14-116">Creates an <xref:System.Xml.Linq.XAttribute> object.</span></span> <span data-ttu-id="73e14-117">`name` 인수는 특성의 이름을 지정하고, `content`는 특성의 내용을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="73e14-117">The `name` argument specifies the name of the attribute; `content` specifies the content of the attribute.</span></span>|  
  
### <a name="creating-an-element-with-an-attribute"></a><span data-ttu-id="73e14-118">특성을 사용하여 요소 만들기</span><span class="sxs-lookup"><span data-stu-id="73e14-118">Creating an Element with an Attribute</span></span>  
 <span data-ttu-id="73e14-119">다음 코드에서는 Visual Basic에서 XML 리터럴을 사용 하 여 특성을 포함 하는 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="73e14-119">The following code shows an element that contains an attribute using XML literals in Visual Basic:</span></span>  
  
```vb  
Dim phone As XElement = <Phone Type="Home">555-555-5555</Phone>  
Console.WriteLine(phone)  
```  
  
 <span data-ttu-id="73e14-120">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="73e14-120">This example produces the following output:</span></span>  
  
```xml  
<Phone Type="Home">555-555-5555</Phone>  
```  
  
### <a name="functional-construction-of-attributes"></a><span data-ttu-id="73e14-121">특성의 함수 생성</span><span class="sxs-lookup"><span data-stu-id="73e14-121">Functional Construction of Attributes</span></span>  
 <span data-ttu-id="73e14-122">생성할 수 있습니다 <xref:System.Xml.Linq.XAttribute>의 생성과 함께 인라인으로 <xref:System.Xml.Linq.XElement>개체를 다음과 같이:</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="73e14-122">You can construct <xref:System.Xml.Linq.XAttribute> objects in-line with the construction of <xref:System.Xml.Linq.XElement> objects, as follows:</span></span>  
  
```vb  
Dim c As XElement = _  
    <Customers>  
        <Customer>  
            <Name>John Doe</Name>  
            <PhoneNumbers>  
                <Phone type="home">555-555-5555</Phone>  
                <Phone type="work">666-666-6666</Phone>  
            </PhoneNumbers>  
        </Customer>  
    </Customers>  
Console.WriteLine(c)  
```  
  
 <span data-ttu-id="73e14-123">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="73e14-123">This example produces the following output:</span></span>  
  
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
  
### <a name="attributes-are-not-nodes"></a><span data-ttu-id="73e14-124">특성은 노드가 아님</span><span class="sxs-lookup"><span data-stu-id="73e14-124">Attributes Are Not Nodes</span></span>  
 <span data-ttu-id="73e14-125">특성과 요소 사이에는 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73e14-125">There are some differences between attributes and elements.</span></span> <span data-ttu-id="73e14-126"><xref:System.Xml.Linq.XAttribute>개체 노드를 XML 트리에 않습니다.</xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="73e14-126"><xref:System.Xml.Linq.XAttribute> objects are not nodes in the XML tree.</span></span> <span data-ttu-id="73e14-127">특성은 XML 요소와 연결된 이름/값 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="73e14-127">They are name/value pairs associated with an XML element.</span></span> <span data-ttu-id="73e14-128">DOM(문서 개체 모델)과 대조적으로 이는 XML의 구조를 더욱 충실하게 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="73e14-128">In contrast to the Document Object Model (DOM), this more closely reflects the structure of XML.</span></span> <span data-ttu-id="73e14-129">하지만 <xref:System.Xml.Linq.XAttribute>개체와 작동 하는 XML 트리 노드 실제로 <xref:System.Xml.Linq.XAttribute>개체 작업과 매우 비슷합니다 <xref:System.Xml.Linq.XElement>개체.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="73e14-129">Although <xref:System.Xml.Linq.XAttribute> objects are not actually nodes in the XML tree, working with <xref:System.Xml.Linq.XAttribute> objects is very similar to working with <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="73e14-130">이 차이는 주로 노드 수준에서 XML 트리 작업을 하는 코드를 작성하는 개발자에게만 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="73e14-130">This distinction is primarily important only to developers who are writing code that works with XML trees at the node level.</span></span> <span data-ttu-id="73e14-131">대부분의 개발자는 이 차이에 대해 염려하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73e14-131">Many developers will not be concerned with this distinction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73e14-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="73e14-132">See Also</span></span>  
 [<span data-ttu-id="73e14-133">LINQ to XML 프로그래밍 개요 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="73e14-133">LINQ to XML Programming Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
