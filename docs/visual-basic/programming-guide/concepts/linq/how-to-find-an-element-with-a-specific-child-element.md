---
title: "방법: 특정 자식 요소 (Visual Basic)으로 요소 찾기"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b0d0a463-6a85-46c3-8453-ad25b0ecf93c
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e6ddb35e954d709548c6b32475f37454015e0a98
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-find-an-element-with-a-specific-child-element-visual-basic"></a><span data-ttu-id="abcbc-102">방법: 특정 자식 요소 (Visual Basic)으로 요소 찾기</span><span class="sxs-lookup"><span data-stu-id="abcbc-102">How to: Find an Element with a Specific Child Element (Visual Basic)</span></span>
<span data-ttu-id="abcbc-103">이 항목에서는 지정된 값을 가진 자식 요소가 포함된 특정 요소를 찾는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="abcbc-103">This topic shows how to find a particular element that has a child element with a specific value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="abcbc-104">예제</span><span class="sxs-lookup"><span data-stu-id="abcbc-104">Example</span></span>  
 <span data-ttu-id="abcbc-105">이 예제에서는 값이 "Examp2.EXE"인 `Test` 자식 요소가 포함된 `CommandLine` 요소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abcbc-105">The example finds the `Test` element that has a `CommandLine` child element with the value of "Examp2.EXE".</span></span>  
  
 <span data-ttu-id="abcbc-106">이 예제에서는 XML 문서 [샘플 XML 파일: 테스트 구성(LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="abcbc-106">This example uses the following XML document: [Sample XML File: Test Configuration (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="abcbc-107">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="abcbc-107">This code produces the following output:</span></span>  
  
```  
0002  
0006  
```  
  
 <span data-ttu-id="abcbc-108">사용 하 여이 예제는 [XML 자식 축 속성](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md), [XML 특성 축 속성](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md), 및 [XML Value 속성](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="abcbc-108">Note that this example uses the [XML Child axis property](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md), the [XML Attribute axis property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md), and the [XML Value property](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="abcbc-109">예제</span><span class="sxs-lookup"><span data-stu-id="abcbc-109">Example</span></span>  
 <span data-ttu-id="abcbc-110">다음 예제에서는 네임스페이스에 있는 XML에 대한 동일한 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="abcbc-110">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="abcbc-111">자세한 내용은 참조 [XML 네임 스페이스 (Visual Basic) 작업](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="abcbc-111">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="abcbc-112">이 예제에서는 XML 문서 [샘플 XML 파일: 네임스페이스에서 테스트 구성](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-in-a-namespace.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="abcbc-112">This example uses the following XML document: [Sample XML File: Test Configuration in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-in-a-namespace.md).</span></span>  
  
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
  
 <span data-ttu-id="abcbc-113">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="abcbc-113">This code produces the following output:</span></span>  
  
```  
0002  
0006  
```  
  
## <a name="see-also"></a><span data-ttu-id="abcbc-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="abcbc-114">See Also</span></span>  
 <xref:System.Xml.Linq.XElement.Attribute%2A>  
 <xref:System.Xml.Linq.XContainer.Elements%2A>  
 [<span data-ttu-id="abcbc-115">기본 쿼리 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="abcbc-115">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)  
 [<span data-ttu-id="abcbc-116">표준 쿼리 연산자 개요(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="abcbc-116">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="abcbc-117">프로젝션 작업 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="abcbc-117">Projection Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projection-operations.md)
