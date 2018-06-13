---
title: XAttribute 클래스 개요 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 7781580a-9583-4a1b-ae1e-91c5936eb0b1
ms.openlocfilehash: 08b8ebf31a39325c98023d4bb333f8e06bbdeb3f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33646967"
---
# <a name="xattribute-class-overview-visual-basic"></a><span data-ttu-id="f4ca3-102">XAttribute 클래스 개요 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f4ca3-102">XAttribute Class Overview (Visual Basic)</span></span>
<span data-ttu-id="f4ca3-103">특성은 요소와 연결된 이름/값 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="f4ca3-103">Attributes are name/value pairs that are associated with an element.</span></span> <span data-ttu-id="f4ca3-104"><xref:System.Xml.Linq.XAttribute> 클래스는 XML 특성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f4ca3-104">The <xref:System.Xml.Linq.XAttribute> class represents XML attributes.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="f4ca3-105">개요</span><span class="sxs-lookup"><span data-stu-id="f4ca3-105">Overview</span></span>  
 <span data-ttu-id="f4ca3-106">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]에서 특성 작업은 요소 작업과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="f4ca3-106">Working with attributes in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is similar to working with elements.</span></span> <span data-ttu-id="f4ca3-107">특성과 요소의 생성자는 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="f4ca3-107">Their constructors are similar.</span></span> <span data-ttu-id="f4ca3-108">특성과 요소의 컬렉션을 검색하는 데 사용하는 메서드는 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="f4ca3-108">The methods that you use to retrieve collections of them are similar.</span></span> <span data-ttu-id="f4ca3-109">특성 컬렉션의 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리 식은 요소 컬렉션의 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리 식과 매우 유사하게 보입니다.</span><span class="sxs-lookup"><span data-stu-id="f4ca3-109">A [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expression for a collection of attributes looks very similar to a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expression for a collection of elements.</span></span>  
  
 <span data-ttu-id="f4ca3-110">특성이 요소에 추가된 순서는 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4ca3-110">The order in which attributes were added to an element is preserved.</span></span> <span data-ttu-id="f4ca3-111">즉, 특성을 반복하는 경우 특성은 추가된 동일한 순서로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4ca3-111">That is, when you iterate through the attributes, you see them in the same order that they were added.</span></span>  
  
## <a name="the-xattribute-constructor"></a><span data-ttu-id="f4ca3-112">XAttribute 생성자</span><span class="sxs-lookup"><span data-stu-id="f4ca3-112">The XAttribute Constructor</span></span>  
 <span data-ttu-id="f4ca3-113"><xref:System.Xml.Linq.XAttribute> 클래스의 다음 생성자는 가장 일반적으로 사용하는 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="f4ca3-113">The following constructor of the <xref:System.Xml.Linq.XAttribute> class is the one that you will most commonly use:</span></span>  
  
|<span data-ttu-id="f4ca3-114">생성자</span><span class="sxs-lookup"><span data-stu-id="f4ca3-114">Constructor</span></span>|<span data-ttu-id="f4ca3-115">설명</span><span class="sxs-lookup"><span data-stu-id="f4ca3-115">Description</span></span>|  
|-----------------|-----------------|  
|`XAttribute(XName name, object content)`|<span data-ttu-id="f4ca3-116"><xref:System.Xml.Linq.XAttribute> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f4ca3-116">Creates an <xref:System.Xml.Linq.XAttribute> object.</span></span> <span data-ttu-id="f4ca3-117">`name` 인수는 특성의 이름을 지정하고, `content`는 특성의 내용을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f4ca3-117">The `name` argument specifies the name of the attribute; `content` specifies the content of the attribute.</span></span>|  
  
### <a name="creating-an-element-with-an-attribute"></a><span data-ttu-id="f4ca3-118">특성을 사용하여 요소 만들기</span><span class="sxs-lookup"><span data-stu-id="f4ca3-118">Creating an Element with an Attribute</span></span>  
 <span data-ttu-id="f4ca3-119">다음 코드는 XML 리터럴을 사용 하 여 Visual Basic의 특성을 포함 하는 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f4ca3-119">The following code shows an element that contains an attribute using XML literals in Visual Basic:</span></span>  
  
```vb  
Dim phone As XElement = <Phone Type="Home">555-555-5555</Phone>  
Console.WriteLine(phone)  
```  
  
 <span data-ttu-id="f4ca3-120">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f4ca3-120">This example produces the following output:</span></span>  
  
```xml  
<Phone Type="Home">555-555-5555</Phone>  
```  
  
### <a name="functional-construction-of-attributes"></a><span data-ttu-id="f4ca3-121">특성의 함수 생성</span><span class="sxs-lookup"><span data-stu-id="f4ca3-121">Functional Construction of Attributes</span></span>  
 <span data-ttu-id="f4ca3-122"><xref:System.Xml.Linq.XAttribute> 개체의 생성과 함께 다음과 같이 <xref:System.Xml.Linq.XElement> 개체를 인라인으로 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4ca3-122">You can construct <xref:System.Xml.Linq.XAttribute> objects in-line with the construction of <xref:System.Xml.Linq.XElement> objects, as follows:</span></span>  
  
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
  
 <span data-ttu-id="f4ca3-123">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f4ca3-123">This example produces the following output:</span></span>  
  
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
  
### <a name="attributes-are-not-nodes"></a><span data-ttu-id="f4ca3-124">특성은 노드가 아님</span><span class="sxs-lookup"><span data-stu-id="f4ca3-124">Attributes Are Not Nodes</span></span>  
 <span data-ttu-id="f4ca3-125">특성과 요소 사이에는 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4ca3-125">There are some differences between attributes and elements.</span></span> <span data-ttu-id="f4ca3-126"><xref:System.Xml.Linq.XAttribute> 개체는 XML 트리의 노드가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f4ca3-126"><xref:System.Xml.Linq.XAttribute> objects are not nodes in the XML tree.</span></span> <span data-ttu-id="f4ca3-127">특성은 XML 요소와 연결된 이름/값 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="f4ca3-127">They are name/value pairs associated with an XML element.</span></span> <span data-ttu-id="f4ca3-128">DOM(문서 개체 모델)과 대조적으로 이는 XML의 구조를 더욱 충실하게 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="f4ca3-128">In contrast to the Document Object Model (DOM), this more closely reflects the structure of XML.</span></span> <span data-ttu-id="f4ca3-129"><xref:System.Xml.Linq.XAttribute> 개체가 실제로 XML 트리의 노드는 아니지만 <xref:System.Xml.Linq.XAttribute> 개체 작업은 <xref:System.Xml.Linq.XElement> 개체 작업과 매우 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="f4ca3-129">Although <xref:System.Xml.Linq.XAttribute> objects are not actually nodes in the XML tree, working with <xref:System.Xml.Linq.XAttribute> objects is very similar to working with <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="f4ca3-130">이 차이는 주로 노드 수준에서 XML 트리 작업을 하는 코드를 작성하는 개발자에게만 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="f4ca3-130">This distinction is primarily important only to developers who are writing code that works with XML trees at the node level.</span></span> <span data-ttu-id="f4ca3-131">대부분의 개발자는 이 차이에 대해 염려하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f4ca3-131">Many developers will not be concerned with this distinction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4ca3-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f4ca3-132">See Also</span></span>  
 [<span data-ttu-id="f4ca3-133">LINQ to XML 프로그래밍 개요 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f4ca3-133">LINQ to XML Programming Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
