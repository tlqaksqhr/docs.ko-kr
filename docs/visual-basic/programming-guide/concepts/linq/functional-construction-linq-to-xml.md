---
title: "함수 생성 (LINQ to XML) (Visual Basic) | Microsoft 문서"
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
ms.assetid: feac4273-39ab-43ae-bab7-4059c807a785
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
ms.openlocfilehash: b88b67aca337b893f9f276c8e4a6589b6946069b
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="functional-construction-linq-to-xml-visual-basic"></a><span data-ttu-id="b9b28-102">함수 생성 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b9b28-102">Functional Construction (LINQ to XML) (Visual Basic)</span></span>
[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="b9b28-103">호출 하는 XML 요소를 만드는 강력한 방법을 제공 *함수 생성*합니다.</span><span class="sxs-lookup"><span data-stu-id="b9b28-103"> provides a powerful way to create XML elements called *functional construction*.</span></span> <span data-ttu-id="b9b28-104">함수 생성은 단일 문으로 XML 트리를 만드는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="b9b28-104">Functional construction is the ability to create an XML tree in a single statement.</span></span>  
  
 <span data-ttu-id="b9b28-105">함수 생성을 가능하게 하는 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 프로그래밍 인터페이스의 몇 가지 주요 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b9b28-105">There are several key features of the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] programming interface that enable functional construction:</span></span>  
  
-   <span data-ttu-id="b9b28-106"><xref:System.Xml.Linq.XElement>생성자는 다양 한 유형의 콘텐츠에 대 한 인수를 사용 합니다.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="b9b28-106">The <xref:System.Xml.Linq.XElement> constructor takes various types of arguments for content.</span></span> <span data-ttu-id="b9b28-107">예를 들어 다른 전달할 수 있습니다 <xref:System.Xml.Linq.XElement>자식 요소가 있는 개체입니다.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="b9b28-107">For example, you can pass another <xref:System.Xml.Linq.XElement> object, which becomes a child element.</span></span> <span data-ttu-id="b9b28-108">전달할 수는 <xref:System.Xml.Linq.XAttribute>요소의 특성이 되는 개체입니다.</xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="b9b28-108">You can pass an <xref:System.Xml.Linq.XAttribute> object, which becomes an attribute of the element.</span></span> <span data-ttu-id="b9b28-109">또는 문자열로 변환되고 요소의 텍스트 내용이 되는 다른 모든 형식의 개체를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9b28-109">Or you can pass any other type of object, which is converted to a string and becomes the text content of the element.</span></span>  
  
-   <span data-ttu-id="b9b28-110"><xref:System.Xml.Linq.XElement>생성자는 `params` 형식의 배열을 <xref:System.Object>생성자에 임의 개수의 개체를 전달할 수 있도록,.</xref:System.Object> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="b9b28-110">The <xref:System.Xml.Linq.XElement> constructor takes a `params` array of type <xref:System.Object>, so that you can pass any number of objects to the constructor.</span></span> <span data-ttu-id="b9b28-111">따라서 복잡한 내용을 가진 요소를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9b28-111">This enables you to create an element that has complex content.</span></span>  
  
-   <span data-ttu-id="b9b28-112">개체를 구현 하는 경우 <xref:System.Collections.Generic.IEnumerable%601>, 개체의 컬렉션이 열거 되 고 컬렉션의 모든 항목이 추가 됩니다.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="b9b28-112">If an object implements <xref:System.Collections.Generic.IEnumerable%601>, the collection in the object is enumerated, and all items in the collection are added.</span></span> <span data-ttu-id="b9b28-113">컬렉션에 있으면 <xref:System.Xml.Linq.XElement>또는 <xref:System.Xml.Linq.XAttribute>개체를 컬렉션의 각 항목은 개별적으로 추가 됩니다.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="b9b28-113">If the collection contains <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, each item in the collection is added separately.</span></span> <span data-ttu-id="b9b28-114">이것은 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 쿼리의 결과를 생성자에 전달할 수 있도록 하기 때문에 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="b9b28-114">This is important because it lets you pass the results of a [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] query to the constructor.</span></span>  
  
 <span data-ttu-id="b9b28-115">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b9b28-115">The following is an example:</span></span>  
  
 <span data-ttu-id="b9b28-116">이러한 기능을 사용 하 여 XML 트리를 만드는 및의 결과 사용 하는 코드를 작성할 XML 리터럴을 사용 하는 코드를 작성할 수 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] XML 트리를 만들 때 쿼리:</span><span class="sxs-lookup"><span data-stu-id="b9b28-116">These features enable you to write code using XML literals to create an XML tree, and also to write code that uses the results of [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] queries when you create an XML tree:</span></span>  
  
```vb  
Dim srcTree As XElement = _  
    <Root>  
        <Element>1</Element>  
        <Element>2</Element>  
        <Element>3</Element>  
        <Element>4</Element>  
        <Element>5</Element>  
    </Root>  
Dim xmlTree As XElement = _  
    <Root>  
        <Child>1</Child>  
        <Child>2</Child>  
        <%= From el In srcTree.Elements() _  
            Where CInt(el) > 2 _  
            Select el %>  
    </Root>  
Console.WriteLine(xmlTree)  
```  
  
 <span data-ttu-id="b9b28-117">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b9b28-117">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b9b28-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b9b28-118">See Also</span></span>  
 [<span data-ttu-id="b9b28-119">XML 트리 (Visual Basic) 만들기</span><span class="sxs-lookup"><span data-stu-id="b9b28-119">Creating XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
