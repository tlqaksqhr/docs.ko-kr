---
title: "방법: 위치에 따라 자식 요소 찾기(XPath-LINQ to XML)(C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: e35bb269-ec86-4c96-8321-12491a0eb2c3
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 247cb8f2be3a005413045198443b132b25241775
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-find-child-elements-based-on-position-xpath-linq-to-xml-c"></a><span data-ttu-id="8b9ce-102">방법: 위치에 따라 자식 요소 찾기(XPath-LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="8b9ce-102">How to: Find Child Elements Based on Position (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="8b9ce-103">위치에 따라 요소를 찾으려는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b9ce-103">Sometimes you want to find elements based on their position.</span></span> <span data-ttu-id="8b9ce-104">두 번째 요소를 찾으려고 하거나 세 번째 요소부터 다섯 번째 요소까지 찾으려고 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b9ce-104">You might want to find the second element, or you might want to find the third through the fifth element.</span></span>  
  
 <span data-ttu-id="8b9ce-105">XPath 식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8b9ce-105">The XPath expression is:</span></span>  
  
 `Test[position() >= 2 and position() <= 4]`  
  
 <span data-ttu-id="8b9ce-106">지연 방식으로 이 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 쿼리를 작성하는 두 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b9ce-106">There are two approaches to writing this [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query in a lazy way.</span></span> <span data-ttu-id="8b9ce-107"><xref:System.Linq.Enumerable.Skip%2A> 및 <xref:System.Linq.Enumerable.Take%2A> 연산자를 사용하거나, 인덱스를 사용하는 <xref:System.Linq.Enumerable.Where%2A> 오버로드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b9ce-107">You can use the <xref:System.Linq.Enumerable.Skip%2A> and <xref:System.Linq.Enumerable.Take%2A> operators, or you can use the <xref:System.Linq.Enumerable.Where%2A> overload that takes an index.</span></span> <span data-ttu-id="8b9ce-108"><xref:System.Linq.Enumerable.Where%2A> 오버로드를 사용할 때 두 인수를 사용하는 람다 식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8b9ce-108">When you use the <xref:System.Linq.Enumerable.Where%2A> overload, you use a lambda expression that takes two arguments.</span></span> <span data-ttu-id="8b9ce-109">다음 예제에서는 위치에 따라 선택하는 두 메서드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8b9ce-109">The following example shows both methods of selecting based on position.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b9ce-110">예제</span><span class="sxs-lookup"><span data-stu-id="8b9ce-110">Example</span></span>  
 <span data-ttu-id="8b9ce-111">이 예제에서는 두 번째 `Test` 요소부터 네 번째 요소까지 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8b9ce-111">This example finds the second through the fourth `Test` element.</span></span> <span data-ttu-id="8b9ce-112">결과는 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="8b9ce-112">The result is a collection of elements.</span></span>  
  
 <span data-ttu-id="8b9ce-113">이 예제에서는 XML 문서 [샘플 XML 파일: 테스트 구성(LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8b9ce-113">This example uses the following XML document: [Sample XML File: Test Configuration (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).</span></span>  
  
```csharp  
XElement testCfg = XElement.Load("TestConfig.xml");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 =  
    testCfg  
    .Elements("Test")  
    .Skip(1)  
    .Take(3);  
  
// LINQ to XML query  
IEnumerable<XElement> list2 =  
    testCfg  
    .Elements("Test")  
    .Where((el, idx) => idx >= 1 && idx <= 3);  
  
// XPath expression  
IEnumerable<XElement> list3 =  
  testCfg.XPathSelectElements("Test[position() >= 2 and position() <= 4]");  
  
if (list1.Count() == list2.Count() &&  
    list1.Count() == list3.Count() &&  
    list1.Intersect(list2).Count() == list1.Count() &&  
    list1.Intersect(list3).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="8b9ce-114">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="8b9ce-114">This example produces the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8b9ce-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8b9ce-115">See Also</span></span>  
 [<span data-ttu-id="8b9ce-116">XPath 사용자를 위한 LINQ to XML(C#)</span><span class="sxs-lookup"><span data-stu-id="8b9ce-116">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)

