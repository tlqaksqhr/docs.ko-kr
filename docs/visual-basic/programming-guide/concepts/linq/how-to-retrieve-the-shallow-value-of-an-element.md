---
title: "방법: 요소 (Visual Basic)의 단순 값 검색 | Microsoft 문서"
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
ms.assetid: 730a6670-fb8c-41fc-8a1b-eb97a837e432
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: a32f50ce8a92fa22d9627a1510a4b3ec1087364e
ms.openlocfilehash: c313f1f13e2dc3cc42d182b3c9542a46f2f4d831
ms.contentlocale: ko-kr
ms.lasthandoff: 06/01/2017


---
# <a name="how-to-retrieve-the-shallow-value-of-an-element-visual-basic"></a><span data-ttu-id="d6db5-102">방법: 요소 (Visual Basic)의 단순 값 검색</span><span class="sxs-lookup"><span data-stu-id="d6db5-102">How to: Retrieve the Shallow Value of an Element (Visual Basic)</span></span>
<span data-ttu-id="d6db5-103">이 항목에서는 요소의 부분 값을 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d6db5-103">This topic shows how to get the shallow value of an element.</span></span> <span data-ttu-id="d6db5-104">단일 문자열로 연결된 모든 하위 요소의 값을 포함하는 상세 값과 달리 부분 값은 특정 요소의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d6db5-104">The shallow value is the value of the specific element only, as opposed to the deep value, which includes the values of all descendent elements concatenated into a single string.</span></span>  
  
 <span data-ttu-id="d6db5-105">요소 값 캐스팅을 사용 하 여 검색 하는 경우 또는 <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName>속성을 전체 값을 검색 합니다.</xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d6db5-105">When you retrieve an element value by using either casting or the <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName> property, you retrieve the deep value.</span></span> <span data-ttu-id="d6db5-106">부분 값을 검색하려면 다음 예제와 같이 `ShallowValue` 확장 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d6db5-106">To retrieve the shallow value, you can use the `ShallowValue` extension method, as shown in the follwing example.</span></span> <span data-ttu-id="d6db5-107">요소의 내용을 기준으로 요소를 선택하려는 경우에는 부분 값을 검색하는 것이 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="d6db5-107">Retrieving the shallow value is useful when you want to select elements based on their content.</span></span>  
  
 <span data-ttu-id="d6db5-108">다음 예제에서는 요소의 부분 값을 검색하는 확장 메서드를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="d6db5-108">The following example declares an extension method that retrieves the shallow value of an element.</span></span> <span data-ttu-id="d6db5-109">그런 다음 쿼리에 해당 확장명 메서드를 사용하여 계산된 값을 포함하는 모든 요소를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="d6db5-109">It then uses the extension method in a query to list all elements that contain a calculated value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6db5-110">예제</span><span class="sxs-lookup"><span data-stu-id="d6db5-110">Example</span></span>  
 <span data-ttu-id="d6db5-111">아래에 있는 Report.xml 텍스트 파일은 이 예제의 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="d6db5-111">The following text file, Report.xml, is the source for this example.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<Report>  
  <Section>  
    <Heading>  
      <Column Name="CustomerId">=Customer.CustomerId.Heading</Column>  
      <Column Name="Name">=Customer.Name.Heading</Column>  
    </Heading>  
    <Detail>  
      <Column Name="CustomerId">=Customer.CustomerId</Column>  
      <Column Name="Name">=Customer.Name</Column>  
    </Detail>  
  </Section>  
</Report>  
```  
  
```vb  
Module Module1  
    <System.Runtime.CompilerServices.Extension()> _  
    Public Function ShallowValue(ByVal xe As XElement)  
        Return xe _  
               .Nodes() _  
               .OfType(Of XText)() _  
               .Aggregate(New StringBuilder(), _  
                              Function(s, c) s.Append(c), _  
                              Function(s) s.ToString())  
    End Function  
  
    Sub Main()  
        Dim root As XElement = XElement.Load("Report.xml")  
  
        Dim query As IEnumerable(Of XElement) = _  
            From el In root.Descendants() _  
            Where (el.ShallowValue().StartsWith("=")) _  
            Select el  
  
        For Each q As XElement In query  
            Console.WriteLine("{0}{1}{2}", _  
                q.Name.ToString().PadRight(8), _  
                q.Attribute("Name").ToString().PadRight(20), _  
                q.ShallowValue())  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="d6db5-112">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d6db5-112">This example produces the following output:</span></span>  
  
```  
Column  Name="CustomerId"   =Customer.CustomerId.Heading  
Column  Name="Name"         =Customer.Name.Heading  
Column  Name="CustomerId"   =Customer.CustomerId  
Column  Name="Name"         =Customer.Name  
```  
  
## <a name="see-also"></a><span data-ttu-id="d6db5-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d6db5-113">See Also</span></span>  
 [<span data-ttu-id="d6db5-114">LINQ to XML 축 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d6db5-114">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
