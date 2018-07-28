---
title: '방법: 단일 특성 (LINQ to XML)을 검색 (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 11b938d7-c011-4048-900e-8b9183c41c94
ms.openlocfilehash: e9e4dce95e9c3202b1cd2a53c186126deac0913c
ms.sourcegitcommit: 869b5832b667915ac4a5dd8c86b1109ed26b6c08
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2018
ms.locfileid: "39332690"
---
# <a name="how-to-retrieve-a-single-attribute-linq-to-xml-visual-basic"></a><span data-ttu-id="b9785-102">방법: 단일 특성 (LINQ to XML)을 검색 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b9785-102">How to: Retrieve a Single Attribute (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="b9785-103">이 항목에서는 특성 이름이 제공되는 경우 요소의 단일 특성을 검색하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b9785-103">This topic explains how to retrieve a single attribute of an element, given the attribute name.</span></span> <span data-ttu-id="b9785-104">이 방법은 특정 특성을 가진 요소를 찾으려는 경우 쿼리 식을 작성하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="b9785-104">This is useful for writing query expressions where you want to find an element that has a particular attribute.</span></span>  
  
 <span data-ttu-id="b9785-105"><xref:System.Xml.Linq.XElement.Attribute%2A> 클래스의 <xref:System.Xml.Linq.XElement> 메서드는 지정된 이름을 가진 <xref:System.Xml.Linq.XAttribute>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b9785-105">The <xref:System.Xml.Linq.XElement.Attribute%2A> method of the <xref:System.Xml.Linq.XElement> class returns the <xref:System.Xml.Linq.XAttribute> with the specified name.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9785-106">예</span><span class="sxs-lookup"><span data-stu-id="b9785-106">Example</span></span>  
 <span data-ttu-id="b9785-107">다음 예제에서는 <xref:System.Xml.Linq.XElement.Attribute%2A> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b9785-107">The following example uses the <xref:System.Xml.Linq.XElement.Attribute%2A> method.</span></span>  
  
```vb  
Dim cust As XElement = <PhoneNumbers>  
                           <Phone type="home">555-555-5555</Phone>  
                           <Phone type="work">555-555-6666</Phone>  
                       </PhoneNumbers>  
Dim elList = From el In cust...<Phone>  
For Each e As XElement In elList  
    Console.WriteLine(e.@type)  
Next  
```  
  
 <span data-ttu-id="b9785-108">이 예제에서는 트리에서 이름이 `Phone`인 하위 요소를 모두 찾은 다음 이름이 `type`인 특성을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b9785-108">This example finds all the descendants in the tree named `Phone`, and then finds the attribute named `type`.</span></span>  
  
 <span data-ttu-id="b9785-109">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b9785-109">This code produces the following output:</span></span>  
  
```  
home  
work  
```  
  
## <a name="example"></a><span data-ttu-id="b9785-110">예</span><span class="sxs-lookup"><span data-stu-id="b9785-110">Example</span></span>  
 <span data-ttu-id="b9785-111">특성의 값을 검색하려면 <xref:System.Xml.Linq.XElement> 개체의 경우와 마찬가지로 특성을 캐스팅하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9785-111">If you want to retrieve the value of the attribute, you can cast it, just as you do for with <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="b9785-112">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="b9785-112">The following example demonstrates this.</span></span>  
  
```vb  
Dim cust As XElement = <PhoneNumbers>  
                           <Phone type="home">555-555-5555</Phone>  
                           <Phone type="work">555-555-6666</Phone>  
                       </PhoneNumbers>  
Dim elList As IEnumerable(Of XElement) = _  
    From el In cust...<Phone> _  
    Select el  
For Each el As XElement In elList  
    Console.WriteLine(el.@type)  
Next  
```  
  
 <span data-ttu-id="b9785-113">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b9785-113">This code produces the following output:</span></span>  
  
```  
home  
work  
```  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="b9785-114">에서는 <xref:System.Xml.Linq.XAttribute> 클래스를 `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`, `GUID?`로 캐스팅할 수 있는 명시적 캐스트 연산자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b9785-114"> provides explicit cast operators for the <xref:System.Xml.Linq.XAttribute> class to `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`, and `GUID?`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9785-115">예</span><span class="sxs-lookup"><span data-stu-id="b9785-115">Example</span></span>  
 <span data-ttu-id="b9785-116">다음 예제에서는 네임스페이스에 있는 특성에 대한 동일한 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b9785-116">The following example shows the same code for an attribute that is in a namespace.</span></span> <span data-ttu-id="b9785-117">자세한 내용은 [XML 네임 스페이스 (Visual Basic)를 사용 하 여 작업](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b9785-117">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim cust As XElement = _  
            <aw:PhoneNumbers>  
                <aw:Phone aw:type="home">555-555-5555</aw:Phone>  
                <aw:Phone aw:type="work">555-555-6666</aw:Phone>  
            </aw:PhoneNumbers>  
        Dim elList As IEnumerable(Of XElement) = _  
            From el In cust...<aw:Phone> _  
            Select el  
        For Each el As XElement In elList  
            Console.WriteLine(el.@aw:type)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="b9785-118">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b9785-118">This code produces the following output:</span></span>  
  
```  
home  
work  
```  
  
## <a name="see-also"></a><span data-ttu-id="b9785-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b9785-119">See Also</span></span>  
 [<span data-ttu-id="b9785-120">LINQ to XML 축(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b9785-120">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
