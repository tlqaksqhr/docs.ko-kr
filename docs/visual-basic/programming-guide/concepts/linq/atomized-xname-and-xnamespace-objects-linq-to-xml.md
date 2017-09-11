---
title: "원자화 XName 및 XNamespace 개체 (LINQ to XML) (Visual Basic) | Microsoft 문서"
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
ms.assetid: 21ee7585-7df9-40b4-8c76-a12bb5f29bb3
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: a32f50ce8a92fa22d9627a1510a4b3ec1087364e
ms.openlocfilehash: 1303d0be3715bb6462ef28b1b2286b999661d240
ms.contentlocale: ko-kr
ms.lasthandoff: 06/01/2017


---
# <a name="atomized-xname-and-xnamespace-objects-linq-to-xml-visual-basic"></a><span data-ttu-id="0f0c8-102">원자화 XName 및 XNamespace 개체 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f0c8-102">Atomized XName and XNamespace Objects (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="0f0c8-103"><xref:System.Xml.Linq.XName>및 <xref:System.Xml.Linq.XNamespace>개체는 *원자화*; 즉, 동일한 정규화 된 이름을 포함 하는 경우 개체를 참조 하는 동일한.</xref:System.Xml.Linq.XNamespace></xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="0f0c8-103"><xref:System.Xml.Linq.XName> and <xref:System.Xml.Linq.XNamespace> objects are *atomized*; that is, if they contain the same qualified name, they refer to the same object.</span></span> <span data-ttu-id="0f0c8-104">이를 통해 쿼리 성능이 향상될 수 있습니다. 두 개의 원자화된 이름이 같은지 비교하는 경우 기본 중간 언어에서 이 두 개의 참조가 같은 개체를 가리키는지 여부만 확인하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f0c8-104">This yields performance benefits for queries: When you compare two atomized names for equality, the underlying intermediate language only has to determine whether the two references point to the same object.</span></span> <span data-ttu-id="0f0c8-105">기본 코드는 시간이 많이 걸리는 문자열 비교를 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f0c8-105">The underlying code does not have to do string comparisons, which would be time consuming.</span></span>  
  
## <a name="atomization-semantics"></a><span data-ttu-id="0f0c8-106">원자화 의미 체계</span><span class="sxs-lookup"><span data-stu-id="0f0c8-106">Atomization Semantics</span></span>  
 <span data-ttu-id="0f0c8-107">원자화 하는 경우 두 개의 <xref:System.Xml.Linq.XName>개체는 동일한 로컬 이름 및 동일한 네임 스페이스에는, 같은 인스턴스를 공유 합니다.</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="0f0c8-107">Atomization means that if two <xref:System.Xml.Linq.XName> objects have the same local name, and they are in the same namespace, they share the same instance.</span></span> <span data-ttu-id="0f0c8-108">마찬가지로, 두 경우에서 <xref:System.Xml.Linq.XNamespace>개체에 같은 네임 스페이스 URI, 같은 인스턴스를 공유 합니다.</xref:System.Xml.Linq.XNamespace></span><span class="sxs-lookup"><span data-stu-id="0f0c8-108">In the same way, if two <xref:System.Xml.Linq.XNamespace> objects have the same namespace URI, they share the same instance.</span></span>  
  
 <span data-ttu-id="0f0c8-109">클래스가 원자화된 개체를 사용하려면 클래스에 대한 생성자가 public이 아니라 private이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f0c8-109">For a class to enable atomized objects, the constructor for the class must be private, not public.</span></span> <span data-ttu-id="0f0c8-110">이는 생성자가 public인 경우 원자화되지 않은 개체를 생성할 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="0f0c8-110">This is because if the constructor were public, you could create a non-atomized object.</span></span> <span data-ttu-id="0f0c8-111"><xref:System.Xml.Linq.XName> <xref:System.Xml.Linq.XNamespace>클래스를 <xref:System.Xml.Linq.XName>나 <xref:System.Xml.Linq.XNamespace>.</xref:System.Xml.Linq.XNamespace> </xref:System.Xml.Linq.XName> 문자열을 변환 하는 암시적 변환 연산자를 구현</xref:System.Xml.Linq.XNamespace> 하 고</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="0f0c8-111">The <xref:System.Xml.Linq.XName> and <xref:System.Xml.Linq.XNamespace> classes implement an implicit conversion operator to convert a string into an <xref:System.Xml.Linq.XName> or <xref:System.Xml.Linq.XNamespace>.</span></span> <span data-ttu-id="0f0c8-112">이를 통해 이러한 개체의 인스턴스를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f0c8-112">This is how you get an instance of these objects.</span></span> <span data-ttu-id="0f0c8-113">생성자는 액세스할 수 없으므로 생성자를 사용하여 인스턴스를 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f0c8-113">You cannot get an instance by using a constructor, because the constructor is inaccessible.</span></span>  
  
 <span data-ttu-id="0f0c8-114"><xref:System.Xml.Linq.XName>및 <xref:System.Xml.Linq.XNamespace>도 두 개의 비교 되는 개체가 참조 하는지 동일한 인스턴스를 확인 하는 같음 및 같지 않음 연산자를 구현 합니다.</xref:System.Xml.Linq.XNamespace></xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="0f0c8-114"><xref:System.Xml.Linq.XName> and <xref:System.Xml.Linq.XNamespace> also implement the equality and inequality operators, to determine whether the two objects being compared are references to the same instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f0c8-115">예제</span><span class="sxs-lookup"><span data-stu-id="0f0c8-115">Example</span></span>  
 <span data-ttu-id="0f0c8-116">다음 코드에서는 일부 <xref:System.Xml.Linq.XElement>개체와 동일한 이름이 같은 인스턴스를 공유 하는 방법을 보여 줍니다.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="0f0c8-116">The following code creates some <xref:System.Xml.Linq.XElement> objects and demonstrates that identical names share the same instance.</span></span>  
  
```vb  
Dim r1 As New XElement("Root", "data1")  
Dim r2 As XElement = XElement.Parse("<Root>data2</Root>")  
  
If DirectCast(r1.Name, Object) = DirectCast(r2.Name, Object) Then  
    Console.WriteLine("r1 and r2 have names that refer to the same instance.")  
Else  
    Console.WriteLine("Different")  
End If  
  
Dim n As XName = "Root"  
  
If DirectCast(n, Object) = DirectCast(r1.Name, Object) Then  
    Console.WriteLine("The name of r1 and the name in 'n' refer to the same instance.")  
Else  
    Console.WriteLine("Different")  
End If  
```  
  
 <span data-ttu-id="0f0c8-117">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0f0c8-117">This example produces the following output:</span></span>  
  
```  
r1 and r2 have names that refer to the same instance.  
The name of r1 and the name in 'n' refer to the same instance.  
```  
  
 <span data-ttu-id="0f0c8-118">앞서 언급 했 듯이 원자화 된 개체의 이점은 사용 하는 축 메서드 중 하나를 사용 하는 경우는 <xref:System.Xml.Linq.XName>를 매개 변수로 축 메서드 여부만 확인 두 이름이 참조 하는지 원하는 요소를 선택 하는 같은 인스턴스.</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="0f0c8-118">As mentioned earlier, the benefit of atomized objects is that when you use one of the axis methods that take an <xref:System.Xml.Linq.XName> as a parameter, the axis method only has to determine that two names reference the same instance to select the desired elements.</span></span>  
  
 <span data-ttu-id="0f0c8-119">다음 예에서는 전달 된 <xref:System.Xml.Linq.XName>에 <xref:System.Xml.Linq.XContainer.Descendants%2A>원자화 패턴으로 인해 다음 더 나은 성능을 메서드 호출.</xref:System.Xml.Linq.XContainer.Descendants%2A> </xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="0f0c8-119">The following example passes an <xref:System.Xml.Linq.XName> to the <xref:System.Xml.Linq.XContainer.Descendants%2A> method call, which then has better performance because of the atomization pattern.</span></span>  
  
```vb  
Dim root As New XElement("Root", New XElement("C1", 1), New XElement("Z1", New XElement("C1", 2), New XElement("C1", 1)))  
  
Dim query = From e In root.Descendants("C1") Where CInt(e) = 1e  
  
For Each z As var In query  
    Console.WriteLine(z)  
Next  
```  
  
 <span data-ttu-id="0f0c8-120">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0f0c8-120">This example produces the following output:</span></span>  
  
```xml  
<C1>1</C1>  
<C1>1</C1>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0f0c8-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0f0c8-121">See Also</span></span>  
 [<span data-ttu-id="0f0c8-122">성능 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f0c8-122">Performance (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/performance-linq-to-xml.md)

