---
title: "이름-값 쌍 (Visual Basic)를 유지 관리 | Microsoft 문서"
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
ms.assetid: 57ac2072-d9f5-432b-84f0-a889c62fd813
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 30e40c73430f385815b7a08a2507343db0fafd4f
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017


---
# <a name="maintaining-namevalue-pairs-visual-basic"></a><span data-ttu-id="c76bc-102">이름/값 쌍 (Visual Basic)를 유지 관리</span><span class="sxs-lookup"><span data-stu-id="c76bc-102">Maintaining Name/Value Pairs (Visual Basic)</span></span>
<span data-ttu-id="c76bc-103">대부분의 응용 프로그램은 이름/값 쌍으로 가장 잘 유지되는 정보를 유지 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c76bc-103">Many applications have to maintain information that is best kept as name/value pairs.</span></span> <span data-ttu-id="c76bc-104">이 정보는 구성 정보이거나 전역 설정일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c76bc-104">This information might be configuration information or global settings.</span></span> [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="c76bc-105">에는 이름/값 쌍의 집합을 쉽게 유지하는 데 사용할 수 있는 몇몇 메서드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c76bc-105"> contains some methods that make it easy to keep a set of name/value pairs.</span></span> <span data-ttu-id="c76bc-106">정보를 특성이나 자식 요소의 집합으로 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c76bc-106">You can either keep the information as attributes or as a set of child elements.</span></span>  
  
 <span data-ttu-id="c76bc-107">정보를 특성으로 유지하는 경우와 자식 요소로 유지하는 경우의 차이점은 특성에 제약 조건이 있다는 것입니다. 즉, 한 요소에 특정 이름을 가진 특성이 하나만 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c76bc-107">One difference between keeping the information as attributes or as child elements is that attributes have the constraint that there can be only one attribute with a particular name for an element.</span></span> <span data-ttu-id="c76bc-108">이 제한은 자식 요소에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c76bc-108">This limitation does not apply to child elements.</span></span>  
  
## <a name="setattributevalue-and-setelementvalue"></a><span data-ttu-id="c76bc-109">SetAttributeValue 및 SetElementValue</span><span class="sxs-lookup"><span data-stu-id="c76bc-109">SetAttributeValue and SetElementValue</span></span>  
 <span data-ttu-id="c76bc-110">두 메서드는 원활 하 게 유지 이름/값 쌍은 <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>및 <xref:System.Xml.Linq.XElement.SetElementValue%2A>.</xref:System.Xml.Linq.XElement.SetElementValue%2A> </xref:System.Xml.Linq.XElement.SetAttributeValue%2A></span><span class="sxs-lookup"><span data-stu-id="c76bc-110">The two methods that facilitate keeping name/value pairs are <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> and <xref:System.Xml.Linq.XElement.SetElementValue%2A>.</span></span> <span data-ttu-id="c76bc-111">이러한 두 메서드의 의미는 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="c76bc-111">These two methods have similar semantics.</span></span>  
  
 <span data-ttu-id="c76bc-112"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A>추가, 수정 하거나 제거할 수는 요소의 특성입니다.</xref:System.Xml.Linq.XElement.SetAttributeValue%2A></span><span class="sxs-lookup"><span data-stu-id="c76bc-112"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A> can add, modify, or remove attributes of an element.</span></span>  
  
-   <span data-ttu-id="c76bc-113">호출 하는 경우 <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>존재 하지 않는 특성의 이름을 사용할 경우 메서드는 새 특성을 만들어 지정된 된 요소에 추가 합니다.</xref:System.Xml.Linq.XElement.SetAttributeValue%2A></span><span class="sxs-lookup"><span data-stu-id="c76bc-113">If you call <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> with a name of an attribute that does not exist, the method creates a new attribute and adds it to the specified element.</span></span>  
  
-   <span data-ttu-id="c76bc-114">호출 하는 경우 <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>콘텐츠, 기존 특성의 이름 및 지정 된 일부와 지정 된 콘텐츠로 특성의 내용을 대체 됩니다.</xref:System.Xml.Linq.XElement.SetAttributeValue%2A></span><span class="sxs-lookup"><span data-stu-id="c76bc-114">If you call <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> with a name of an existing attribute and with some specified content, the contents of the attribute are replaced with the specified content.</span></span>  
  
-   <span data-ttu-id="c76bc-115">호출 하는 경우 <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>기존 이름으로 특성을 지정 된 내용에 null을 특성이 부모에서 제거 됩니다.</xref:System.Xml.Linq.XElement.SetAttributeValue%2A></span><span class="sxs-lookup"><span data-stu-id="c76bc-115">If you call <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> with a name of an existing attribute, and specify null for the content, the attribute is removed from its parent.</span></span>  
  
 <span data-ttu-id="c76bc-116"><xref:System.Xml.Linq.XElement.SetElementValue%2A>추가, 수정 하거나 제거할 수는 요소의 자식 요소입니다.</xref:System.Xml.Linq.XElement.SetElementValue%2A></span><span class="sxs-lookup"><span data-stu-id="c76bc-116"><xref:System.Xml.Linq.XElement.SetElementValue%2A> can add, modify, or remove child elements of an element.</span></span>  
  
-   <span data-ttu-id="c76bc-117">호출 하는 경우 <xref:System.Xml.Linq.XElement.SetElementValue%2A>존재 하지 않는 자식 요소의 이름을 사용할 경우 메서드는 새 요소를 만들어 지정된 된 요소에 추가 합니다.</xref:System.Xml.Linq.XElement.SetElementValue%2A></span><span class="sxs-lookup"><span data-stu-id="c76bc-117">If you call <xref:System.Xml.Linq.XElement.SetElementValue%2A> with a name of a child element that does not exist, the method creates a new element and adds it to the specified element.</span></span>  
  
-   <span data-ttu-id="c76bc-118">호출 하는 경우 <xref:System.Xml.Linq.XElement.SetElementValue%2A>콘텐츠, 기존 요소 이름 및 지정 된 일부와 지정 된 콘텐츠로 요소의 내용을 대체 됩니다.</xref:System.Xml.Linq.XElement.SetElementValue%2A></span><span class="sxs-lookup"><span data-stu-id="c76bc-118">If you call <xref:System.Xml.Linq.XElement.SetElementValue%2A> with a name of an existing element and with some specified content, the contents of the element are replaced with the specified content.</span></span>  
  
-   <span data-ttu-id="c76bc-119">호출 하는 경우 <xref:System.Xml.Linq.XElement.SetElementValue%2A>기존 요소의 이름을 가진 고 내용에 null을 지정 하면 요소가 부모에서 제거 됩니다.</xref:System.Xml.Linq.XElement.SetElementValue%2A></span><span class="sxs-lookup"><span data-stu-id="c76bc-119">If you call <xref:System.Xml.Linq.XElement.SetElementValue%2A> with a name of an existing element, and specify null for the content, the element is removed from its parent.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c76bc-120">예제</span><span class="sxs-lookup"><span data-stu-id="c76bc-120">Example</span></span>  
 <span data-ttu-id="c76bc-121">다음 예제에서는 특성 없이 요소를 만든 다음</span><span class="sxs-lookup"><span data-stu-id="c76bc-121">The following example creates an element with no attributes.</span></span> <span data-ttu-id="c76bc-122">다음 사용 하 여는 <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>메서드를 만들어 이름/값 쌍의 목록을 유지 관리 합니다.</xref:System.Xml.Linq.XElement.SetAttributeValue%2A></span><span class="sxs-lookup"><span data-stu-id="c76bc-122">It then uses the <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> method to create and maintain a list of name/value pairs.</span></span>  
  
```vb  
' Create an element with no content.  
Dim root As XElement = <Root/>  
  
' Add a number of name/value pairs as attributes.  
root.SetAttributeValue("Top", 22)  
root.SetAttributeValue("Left", 20)  
root.SetAttributeValue("Bottom", 122)  
root.SetAttributeValue("Right", 300)  
root.SetAttributeValue("DefaultColor", "Color.Red")  
Console.WriteLine(root)  
  
' Replace the value of Top.  
root.SetAttributeValue("Top", 10)  
Console.WriteLine(root)  
  
' Remove DefaultColor.  
root.SetAttributeValue("DefaultColor", Nothing)  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="c76bc-123">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c76bc-123">This example produces the following output:</span></span>  
  
```  
<Root Top="22" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" />  
```  
  
## <a name="example"></a><span data-ttu-id="c76bc-124">예제</span><span class="sxs-lookup"><span data-stu-id="c76bc-124">Example</span></span>  
 <span data-ttu-id="c76bc-125">다음 예제에서는 자식 요소 없이 요소를 만든 다음</span><span class="sxs-lookup"><span data-stu-id="c76bc-125">The following example creates an element with no child elements.</span></span> <span data-ttu-id="c76bc-126">다음 사용 하 여는 <xref:System.Xml.Linq.XElement.SetElementValue%2A>메서드를 만들어 이름/값 쌍의 목록을 유지 관리 합니다.</xref:System.Xml.Linq.XElement.SetElementValue%2A></span><span class="sxs-lookup"><span data-stu-id="c76bc-126">It then uses the <xref:System.Xml.Linq.XElement.SetElementValue%2A> method to create and maintain a list of name/value pairs.</span></span>  
  
```vb  
' Create an element with no content.  
Dim root As XElement = <Root/>  
  
' Add a number of name/value pairs as elements.  
root.SetElementValue("Top", 22)  
root.SetElementValue("Left", 20)  
root.SetElementValue("Bottom", 122)  
root.SetElementValue("Right", 300)  
root.SetElementValue("DefaultColor", "Color.Red")  
Console.WriteLine(root)  
Console.WriteLine("----")  
  
' Replace the value of Top.  
root.SetElementValue("Top", 10)  
Console.WriteLine(root)  
Console.WriteLine("----")  
  
' Remove DefaultColor.  
root.SetElementValue("DefaultColor", Nothing)  
Console.WriteLine(root)  
  
```  
  
 <span data-ttu-id="c76bc-127">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c76bc-127">This example produces the following output:</span></span>  
  
```  
<Root>  
  <Top>22</Top>  
  <Left>20</Left>  
  <Bottom>122</Bottom>  
  <Right>300</Right>  
  <DefaultColor>Color.Red</DefaultColor>  
</Root>  
----  
<Root>  
  <Top>10</Top>  
  <Left>20</Left>  
  <Bottom>122</Bottom>  
  <Right>300</Right>  
  <DefaultColor>Color.Red</DefaultColor>  
</Root>  
----  
<Root>  
  <Top>10</Top>  
  <Left>20</Left>  
  <Bottom>122</Bottom>  
  <Right>300</Right>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c76bc-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c76bc-128">See Also</span></span>  
 <span data-ttu-id="c76bc-129"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A></xref:System.Xml.Linq.XElement.SetAttributeValue%2A></span><span class="sxs-lookup"><span data-stu-id="c76bc-129"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A></span></span>   
 <span data-ttu-id="c76bc-130"><xref:System.Xml.Linq.XElement.SetElementValue%2A></xref:System.Xml.Linq.XElement.SetElementValue%2A></span><span class="sxs-lookup"><span data-stu-id="c76bc-130"><xref:System.Xml.Linq.XElement.SetElementValue%2A></span></span>   
<span data-ttu-id="c76bc-131"> [XML 트리 수정 (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)</span><span class="sxs-lookup"><span data-stu-id="c76bc-131"> [Modifying XML Trees (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)</span></span>
