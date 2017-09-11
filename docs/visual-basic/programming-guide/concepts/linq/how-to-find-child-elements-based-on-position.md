---
title: "방법: 위치 (XPath 및 LINQ to XML)에 따라 자식 요소 찾기 (Visual Basic) | Microsoft 문서"
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
ms.assetid: 6831e1db-5e97-444f-a7a1-d0a87104b005
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 5e42a12605eecc6633da45342ee0111dcc4b0cc1
ms.contentlocale: ko-kr
ms.lasthandoff: 05/23/2017


---
# <a name="how-to-find-child-elements-based-on-position-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="316e9-102">방법: 위치 (XPath 및 LINQ to XML)에 따라 자식 요소 찾기 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="316e9-102">How to: Find Child Elements Based on Position (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="316e9-103">위치에 따라 요소를 찾으려는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="316e9-103">Sometimes you want to find elements based on their position.</span></span> <span data-ttu-id="316e9-104">두 번째 요소를 찾으려고 하거나 세 번째 요소부터 다섯 번째 요소까지 찾으려고 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="316e9-104">You might want to find the second element, or you might want to find the third through the fifth element.</span></span>  
  
 <span data-ttu-id="316e9-105">XPath 식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="316e9-105">The XPath expression is:</span></span>  
  
 `Test[position() >= 2 and position() <= 4]`  
  
 <span data-ttu-id="316e9-106">지연 방식으로 이 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 쿼리를 작성하는 두 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="316e9-106">There are two approaches to writing this [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] query in a lazy way.</span></span> <span data-ttu-id="316e9-107">사용할 수는 <xref:System.Linq.Enumerable.Skip%2A>및 <xref:System.Linq.Enumerable.Take%2A>연산자 하거나 사용할 수 있습니다는 <xref:System.Linq.Enumerable.Where%2A>인덱스를 사용 하는 오버 로드.</xref:System.Linq.Enumerable.Where%2A> </xref:System.Linq.Enumerable.Take%2A> </xref:System.Linq.Enumerable.Skip%2A></span><span class="sxs-lookup"><span data-stu-id="316e9-107">You can use the <xref:System.Linq.Enumerable.Skip%2A> and <xref:System.Linq.Enumerable.Take%2A> operators, or you can use the <xref:System.Linq.Enumerable.Where%2A> overload that takes an index.</span></span> <span data-ttu-id="316e9-108">사용 하는 경우는 <xref:System.Linq.Enumerable.Where%2A>오버 로드는 두 개의 인수를 사용 하는 람다 식을 사용 합니다.</xref:System.Linq.Enumerable.Where%2A></span><span class="sxs-lookup"><span data-stu-id="316e9-108">When you use the <xref:System.Linq.Enumerable.Where%2A> overload, you use a lambda expression that takes two arguments.</span></span> <span data-ttu-id="316e9-109">다음 예제에서는 위치에 따라 선택하는 두 메서드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="316e9-109">The following example shows both methods of selecting based on position.</span></span>  
  
## <a name="example"></a><span data-ttu-id="316e9-110">예제</span><span class="sxs-lookup"><span data-stu-id="316e9-110">Example</span></span>  
 <span data-ttu-id="316e9-111">이 예제에서는 두 번째 `Test` 요소부터 네 번째 요소까지 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="316e9-111">This example finds the second through the fourth `Test` element.</span></span> <span data-ttu-id="316e9-112">결과는 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="316e9-112">The result is a collection of elements.</span></span>  
  
 <span data-ttu-id="316e9-113">이 예제에서는 다음 XML 문서: [샘플 XML 파일: 테스트 구성 (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="316e9-113">This example uses the following XML document: [Sample XML File: Test Configuration (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).</span></span>  
  
```vb  
Dim testCfg As XElement = XElement.Load("TestConfig.xml")  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XElement) = _  
    testCfg.Elements("Test").Skip(1).Take(3)  
  
'LINQ to XML query  
Dim list2 As IEnumerable(Of XElement) = _  
    testCfg.Elements("Test"). _  
    Where(Function(ByVal el, ByVal idx) idx >= 1 And idx <= 3)  
  
' XPath expression  
Dim list3 As IEnumerable(Of XElement) = _  
    testCfg.XPathSelectElements("Test[position() >= 2 and position() <= 4]")  
  
If list1.Count() = list2.Count() And _  
       list1.Count() = list3.Count() And _  
       list1.Intersect(list2).Count() = list1.Count() And _  
       list1.Intersect(list3).Count() = list1.Count() Then  
  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
  
For Each el As XElement In list1  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="316e9-114">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="316e9-114">This example produces the following output:</span></span>  
  
```  
Results are identical  
<Test TestId="0002" TestType="CMD">  
  <Name>Find succeeding characters</Name>  
  <CommandLine>Examp2.EXE</CommandLine>  
  <Input>abc</Input>  
  <Output>def</Output>  
</Test>  
<Test TestId="0003" TestType="GUI">  
  <Name>Convert multiple numbers to strings</Name>  
  <CommandLine>Examp2.EXE /Verbose</CommandLine>  
  <Input>123</Input>  
  <Output>One Two Three</Output>  
</Test>  
<Test TestId="0004" TestType="GUI">  
  <Name>Find correlated key</Name>  
  <CommandLine>Examp3.EXE</CommandLine>  
  <Input>a1</Input>  
  <Output>b1</Output>  
</Test>  
```  
  
## <a name="see-also"></a><span data-ttu-id="316e9-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="316e9-115">See Also</span></span>  
 [<span data-ttu-id="316e9-116">LINQ to XML에 대 한 XPath 사용자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="316e9-116">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)

