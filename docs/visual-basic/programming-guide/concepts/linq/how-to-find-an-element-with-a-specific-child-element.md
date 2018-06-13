---
title: '방법: 특정 자식 요소 (Visual Basic)으로 요소 찾기'
ms.date: 07/20/2015
ms.assetid: b0d0a463-6a85-46c3-8453-ad25b0ecf93c
ms.openlocfilehash: 9ebc7fd826e2245cea661b2441fa9989b0aee8b8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33644014"
---
# <a name="how-to-find-an-element-with-a-specific-child-element-visual-basic"></a><span data-ttu-id="c7909-102">방법: 특정 자식 요소 (Visual Basic)으로 요소 찾기</span><span class="sxs-lookup"><span data-stu-id="c7909-102">How to: Find an Element with a Specific Child Element (Visual Basic)</span></span>
<span data-ttu-id="c7909-103">이 항목에서는 지정된 값을 가진 자식 요소가 포함된 특정 요소를 찾는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c7909-103">This topic shows how to find a particular element that has a child element with a specific value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7909-104">예제</span><span class="sxs-lookup"><span data-stu-id="c7909-104">Example</span></span>  
 <span data-ttu-id="c7909-105">이 예제에서는 값이 "Examp2.EXE"인 `Test` 자식 요소가 포함된 `CommandLine` 요소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c7909-105">The example finds the `Test` element that has a `CommandLine` child element with the value of "Examp2.EXE".</span></span>  
  
 <span data-ttu-id="c7909-106">이 예제에서는 XML 문서 [샘플 XML 파일: 테스트 구성(LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c7909-106">This example uses the following XML document: [Sample XML File: Test Configuration (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).</span></span>  
  
```vb  
Dim root As XElement = XElement.Load("TestConfig.xml")  
Dim tests As IEnumerable(Of XElement) = _  
    From el In root.<Test> _  
    Where el.<CommandLine>.Value = "Examp2.EXE" _  
    Select el  
For Each el as XElement In tests  
    Console.WriteLine(el.@TestId)  
Next  
```  
  
 <span data-ttu-id="c7909-107">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c7909-107">This code produces the following output:</span></span>  
  
```  
0002  
0006  
```  
  
 <span data-ttu-id="c7909-108">사용 하 여이 예제는 [XML 자식 축 속성](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md), [XML 특성 축 속성](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md), 및 [XML Value 속성](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c7909-108">Note that this example uses the [XML Child axis property](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md), the [XML Attribute axis property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md), and the [XML Value property](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7909-109">예제</span><span class="sxs-lookup"><span data-stu-id="c7909-109">Example</span></span>  
 <span data-ttu-id="c7909-110">다음 예제에서는 네임스페이스에 있는 XML에 대한 동일한 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c7909-110">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="c7909-111">자세한 내용은 참조 [XML 네임 스페이스 (Visual Basic) 작업](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c7909-111">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="c7909-112">이 예제에서는 XML 문서 [샘플 XML 파일: 네임스페이스에서 테스트 구성](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-in-a-namespace.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c7909-112">This example uses the following XML document: [Sample XML File: Test Configuration in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-in-a-namespace.md).</span></span>  
  
```vb  
Imports <xmlns='http://www.adatum.com'>  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = XElement.Load("TestConfigInNamespace.xml")  
        Dim tests As IEnumerable(Of XElement) = _  
            From el In root.<Test> _  
            Where el.<CommandLine>.Value = "Examp2.EXE" _  
            Select el  
        For Each el As XElement In tests  
            Console.WriteLine(el.@TestId)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="c7909-113">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c7909-113">This code produces the following output:</span></span>  
  
```  
0002  
0006  
```  
  
## <a name="see-also"></a><span data-ttu-id="c7909-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c7909-114">See Also</span></span>  
 <xref:System.Xml.Linq.XElement.Attribute%2A>  
 <xref:System.Xml.Linq.XContainer.Elements%2A>  
 [<span data-ttu-id="c7909-115">기본 쿼리 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c7909-115">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)  
 [<span data-ttu-id="c7909-116">표준 쿼리 연산자 개요(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c7909-116">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="c7909-117">프로젝션 작업 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c7909-117">Projection Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projection-operations.md)
