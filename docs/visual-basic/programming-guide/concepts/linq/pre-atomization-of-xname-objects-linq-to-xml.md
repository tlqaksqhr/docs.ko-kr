---
title: "XName 개체 (LINQ to XML)의 사전 원자화 (Visual Basic) | Microsoft 문서"
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
ms.assetid: 06ea104b-f44c-4bb2-9c34-889ae025c80d
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4871fab18d04ce9d715299fd06138c493e666466
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017


---
# <a name="pre-atomization-of-xname-objects-linq-to-xml-visual-basic"></a><span data-ttu-id="fe9f2-102">XName 개체 (LINQ to XML)의 사전 원자화 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fe9f2-102">Pre-Atomization of XName Objects (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="fe9f2-103">LINQ to XML의에서 성능을 향상 시키는 한 가지 방법은 미리 원자화 하는 <xref:System.Xml.Linq.XName>개체.</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="fe9f2-103">One way to improve performance in LINQ to XML is to pre-atomize <xref:System.Xml.Linq.XName> objects.</span></span> <span data-ttu-id="fe9f2-104">사전 원자화에 대 한 문자열을 할당 하는 의미는 <xref:System.Xml.Linq.XName>개체의 생성자를 사용 하 여 XML 트리를 만들기 전에 <xref:System.Xml.Linq.XElement>및 <xref:System.Xml.Linq.XAttribute>클래스.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="fe9f2-104">Pre-atomization means that you assign a string to an <xref:System.Xml.Linq.XName> object before you create the XML tree by using the constructors of the <xref:System.Xml.Linq.XElement> and  <xref:System.Xml.Linq.XAttribute> classes.</span></span> <span data-ttu-id="fe9f2-105">그런 다음 문자열을 생성자에 전달 하는 대신는 사용 하는 문자열에서 암시적으로 변환 <xref:System.Xml.Linq.XName>를 전달 하는 초기화 된 <xref:System.Xml.Linq.XName>개체.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="fe9f2-105">Then, instead of passing a string to the constructor, which would use the implicit conversion from string to <xref:System.Xml.Linq.XName>, you pass the initialized <xref:System.Xml.Linq.XName> object.</span></span>  
  
 <span data-ttu-id="fe9f2-106">이렇게 하면 특정 이름이 반복되는 대형 XML 트리를 만드는 경우 성능이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-106">This improves performance when you create a large XML tree in which specific names are repeated.</span></span> <span data-ttu-id="fe9f2-107">이 위해 선언 하 고 초기화 <xref:System.Xml.Linq.XName>XML 트리를 생성 하 고 사용 하기 전에 개체는 <xref:System.Xml.Linq.XName>요소 및 특성 이름에 대 한 문자열을 지정 하는 대신 개체.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="fe9f2-107">To do this, you declare and initialize <xref:System.Xml.Linq.XName> objects before you construct the XML tree, and then use the <xref:System.Xml.Linq.XName> objects instead of specifying strings for the element and attribute names.</span></span> <span data-ttu-id="fe9f2-108">이 방법을 사용하면 같은 이름으로 매우 많은 요소 또는 특성을 만드는 경우 상당한 성능상의 이점을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-108">This technique can yield significant performance gains if you are creating a large number of elements (or attributes) with the same name.</span></span>  
  
 <span data-ttu-id="fe9f2-109">이 방법을 사용할지 여부를 결정하려면 사용자 시나리오를 사전 원자화해 보는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-109">You should test pre-atomization with your scenario to decide if you should use it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe9f2-110">예제</span><span class="sxs-lookup"><span data-stu-id="fe9f2-110">Example</span></span>  
 <span data-ttu-id="fe9f2-111">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-111">The following example demonstrates this.</span></span>  
  
```vb  
Dim Root__1 As XName = "Root"  
Dim Data As XName = "Data"  
Dim ID As XName = "ID"  
  
Dim root__2 As New XElement(Root__1, New XElement(Data, New XAttribute(ID, "1"), "4,100,000"), New XElement(Data, New XAttribute(ID, "2"), "3,700,000"), New XElement(Data, New XAttribute(ID, "3"), "1,150,000"))  
  
Console.WriteLine(root__2)  
```  
  
 <span data-ttu-id="fe9f2-112">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-112">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Data ID="1">4,100,000</Data>  
  <Data ID="2">3,700,000</Data>  
  <Data ID="3">1,150,000</Data>  
</Root>  
```  
  
 <span data-ttu-id="fe9f2-113">다음 예제에서는 XML 문서가 네임스페이스에 있는 동일한 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-113">The following example shows the same technique where the XML document is in a namespace:</span></span>  
  
```vb  
Dim aw As XNamespace = "http://www.adventure-works.com"  
Dim Root__1 As XName = aw + "Root"  
Dim Data As XName = aw + "Data"  
Dim ID As XName = "ID"  
  
Dim root__2 As New XElement(Root__1, New XAttribute(XNamespace.Xmlns + "aw", aw), New XElement(Data, New XAttribute(ID, "1"), "4,100,000"), New XElement(Data, New XAttribute(ID, "2"), "3,700,000"), New XElement(Data, New XAttribute(ID, "3"), "1,150,000"))  
  
Console.WriteLine(root__2)  
```  
  
 <span data-ttu-id="fe9f2-114">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-114">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Data ID="1">4,100,000</aw:Data>  
  <aw:Data ID="2">3,700,000</aw:Data>  
  <aw:Data ID="3">1,150,000</aw:Data>  
</aw:Root>  
```  
  
 <span data-ttu-id="fe9f2-115">다음 예제는 실제로 사용될 수 있는 것과 더욱 유사한 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-115">The following example is more similar to what you will likely encounter in the real world.</span></span> <span data-ttu-id="fe9f2-116">이 예제에서 요소의 내용은 쿼리를 통해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-116">In this example, the content of the element is supplied by a query:</span></span>  
  
```vb  
Dim Root__1 As XName = "Root"  
Dim Data As XName = "Data"  
Dim ID As XName = "ID"  
  
Dim t1 As DateTime = DateTime.Now  
Dim root__2 As New XElement(Root__1, From i In System.Linq.Enumerable.Range(1, 100000)New XElement(Data, New XAttribute(ID, i), i * 5))  
Dim t2 As DateTime = DateTime.Now  
  
Console.WriteLine("Time to construct:{0}", t2 - t1)  
```  
  
 <span data-ttu-id="fe9f2-117">위 예제는 이름이 사전 원자화되지 않은 다음 예제보다 더 나은 성능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fe9f2-117">The previous example performs better than the following example, in which names are not pre-atomized:</span></span>  
  
```vb  
Dim t1 As DateTime = DateTime.Now  
Dim root As New XElement("Root", From i In System.Linq.Enumerable.Range(1, 100000)New XElement("Data", New XAttribute("ID", i), i * 5))  
Dim t2 As DateTime = DateTime.Now  
  
Console.WriteLine("Time to construct:{0}", t2 - t1)  
```  
  
## <a name="see-also"></a><span data-ttu-id="fe9f2-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fe9f2-118">See Also</span></span>  
 <span data-ttu-id="fe9f2-119">[성능 (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/performance-linq-to-xml.md) </span><span class="sxs-lookup"><span data-stu-id="fe9f2-119">[Performance (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/performance-linq-to-xml.md) </span></span>  
<span data-ttu-id="fe9f2-120"> [원자화 XName 및 XNamespace 개체 (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/atomized-xname-and-xnamespace-objects-linq-to-xml.md)</span><span class="sxs-lookup"><span data-stu-id="fe9f2-120"> [Atomized XName and XNamespace Objects (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/atomized-xname-and-xnamespace-objects-linq-to-xml.md)</span></span>
