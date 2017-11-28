---
title: "방법: 요소 값 검색(LINQ to XML)(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 4228c007-07c9-4cf2-a45b-e7074c109581
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ceb803eff68f72378ca195120ed96990d62d3593
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-retrieve-the-value-of-an-element-linq-to-xml-c"></a><span data-ttu-id="6b82f-102">방법: 요소 값 검색(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="6b82f-102">How to: Retrieve the Value of an Element (LINQ to XML) (C#)</span></span>
<span data-ttu-id="6b82f-103">이 항목에서는 요소의 값을 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6b82f-103">This topic shows how to get the value of elements.</span></span> <span data-ttu-id="6b82f-104">두 가지 주요 방법으로 요소의 값을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b82f-104">There are two main ways to do this.</span></span> <span data-ttu-id="6b82f-105">한 가지 방법은 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XAttribute>를 원하는 형식으로 캐스팅하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6b82f-105">One way is to cast an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XAttribute> to the desired type.</span></span> <span data-ttu-id="6b82f-106">명시적 변환 연산자는 요소나 특성의 내용을 지정된 형식으로 변환하고 변수에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6b82f-106">The explicit conversion operator then converts the contents of the element or attribute to the specified type and assigns it to your variable.</span></span> <span data-ttu-id="6b82f-107">또는 <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> 속성이나 <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType> 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b82f-107">Alternatively, you can use the <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> property or the <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="6b82f-108">그러나 C#에서는 캐스팅이 대개 더 나은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="6b82f-108">With C#, however, casting is generally the better approach.</span></span> <span data-ttu-id="6b82f-109">요소나 특성을 nullable 형식으로 캐스팅하면 존재하지 않을 수도 있는 요소나 특성의 값을 검색하는 경우 코드를 더 간단하게 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b82f-109">If you cast the element or attribute to a nullable type, the code is simpler to write when retrieving the value of an element (or attribute) that might or might not exist.</span></span> <span data-ttu-id="6b82f-110">이 항목의 마지막 예제에서는 이에 대해 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6b82f-110">The last example in this topic demonstrates this.</span></span> <span data-ttu-id="6b82f-111">그러나 <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> 속성을 통해 설정할 수 있는 것처럼 캐스팅을 통해 요소의 내용을 설정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6b82f-111">However, you cannot set the contents of an element through casting, as you can through <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b82f-112">예제</span><span class="sxs-lookup"><span data-stu-id="6b82f-112">Example</span></span>  
 <span data-ttu-id="6b82f-113">요소의 값을 검색하려면 <xref:System.Xml.Linq.XElement> 개체를 원하는 형식으로 캐스팅하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b82f-113">To retrieve the value of an element, you just cast the <xref:System.Xml.Linq.XElement> object to your desired type.</span></span> <span data-ttu-id="6b82f-114">다음과 같이 요소를 문자열로 항상 캐스팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b82f-114">You can always cast an element to a string, as follows:</span></span>  
  
```csharp  
XElement e = new XElement("StringElement", "abcde");  
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + (string)e);  
```  
  
 <span data-ttu-id="6b82f-115">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6b82f-115">This example produces the following output:</span></span>  
  
```  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="example"></a><span data-ttu-id="6b82f-116">예제</span><span class="sxs-lookup"><span data-stu-id="6b82f-116">Example</span></span>  
 <span data-ttu-id="6b82f-117">또한 요소를 문자열 이외의 형식으로 캐스팅할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b82f-117">You can also cast elements to types other than string.</span></span> <span data-ttu-id="6b82f-118">예를 들어, 정수가 포함된 요소가 있는 경우 다음 코드에서와 같이 요소를 `int`로 캐스팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b82f-118">For example, if you have an element that contains an integer, you can cast it to `int`, as shown in the following code:</span></span>  
  
```csharp  
XElement e = new XElement("Age", "44");  
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + (int)e);  
```  
  
 <span data-ttu-id="6b82f-119">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6b82f-119">This example produces the following output:</span></span>  
  
```  
<Age>44</Age>  
Value of e:44  
```  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="6b82f-120">에서는 `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID` 및 `GUID?` 데이터 형식에 대해 명시적 캐스트 연산자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6b82f-120"> provides explicit cast operators for the following data types: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`, and `GUID?`.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="6b82f-121">에서는 <xref:System.Xml.Linq.XAttribute> 개체에 대해 동일한 캐스트 연산자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6b82f-121"> provides the same cast operators for <xref:System.Xml.Linq.XAttribute> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b82f-122">예제</span><span class="sxs-lookup"><span data-stu-id="6b82f-122">Example</span></span>  
 <span data-ttu-id="6b82f-123"><xref:System.Xml.Linq.XElement.Value%2A> 속성을 사용하여 요소의 내용을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b82f-123">You can use the <xref:System.Xml.Linq.XElement.Value%2A> property to retrieve the contents of an element:</span></span>  
  
```csharp  
XElement e = new XElement("StringElement", "abcde");   
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + e.Value);  
```  
  
 <span data-ttu-id="6b82f-124">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6b82f-124">This example produces the following output:</span></span>  
  
```  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="example"></a><span data-ttu-id="6b82f-125">예제</span><span class="sxs-lookup"><span data-stu-id="6b82f-125">Example</span></span>  
 <span data-ttu-id="6b82f-126">요소가 있는지 확실하지 않은 경우에도 요소의 값을 검색하려는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b82f-126">Sometimes you try to retrieve the value of an element even though you are not sure it exists.</span></span> <span data-ttu-id="6b82f-127">이 경우 캐스팅된 요소를 nullable 형식(`string` 또는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]의 nullable 형식 중 하나)에 할당할 때 요소가 없으면 할당된 변수가 `null`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b82f-127">In this case, when you assign the casted element to a nullable type (either `string` or one of the nullable types in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]), if the element does not exist the assigned variable is just set to `null`.</span></span> <span data-ttu-id="6b82f-128">다음 코드에서는 요소가 존재하지 않을 수도 있을 때 <xref:System.Xml.Linq.XElement.Value%2A> 속성을 사용하는 것보다 캐스팅을 사용하는 것이 더 쉽다는 사실을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6b82f-128">The following code shows that when the element might or might not exist, it is easier to use casting than to use the <xref:System.Xml.Linq.XElement.Value%2A> property.</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child1", "child 1 content"),  
    new XElement("Child2", "2")  
);  
  
// The following assignments show why it is easier to use  
// casting when the element might or might not exist.  
  
string c1 = (string)root.Element("Child1");  
Console.WriteLine("c1:{0}", c1 == null ? "element does not exist" : c1);  
  
int? c2 = (int?)root.Element("Child2");  
Console.WriteLine("c2:{0}", c2 == null ? "element does not exist" : c2.ToString());  
  
string c3 = (string)root.Element("Child3");  
Console.WriteLine("c3:{0}", c3 == null ? "element does not exist" : c3);  
  
int? c4 = (int?)root.Element("Child4");  
Console.WriteLine("c4:{0}", c4 == null ? "element does not exist" : c4.ToString());  
  
Console.WriteLine();  
  
// The following assignments show the required code when using  
// the Value property when the element might or might not exist.  
// Notice that this is more difficult than the casting approach.  
  
XElement e1 = root.Element("Child1");  
string v1;  
if (e1 == null)  
    v1 = null;  
else  
    v1 = e1.Value;  
Console.WriteLine("v1:{0}", v1 == null ? "element does not exist" : v1);  
  
XElement e2 = root.Element("Child2");  
int? v2;  
if (e2 == null)  
    v2 = null;  
else  
    v2 = Int32.Parse(e2.Value);  
Console.WriteLine("v2:{0}", v2 == null ? "element does not exist" : v2.ToString());  
  
XElement e3 = root.Element("Child3");  
string v3;  
if (e3 == null)  
    v3 = null;  
else  
    v3 = e3.Value;  
Console.WriteLine("v3:{0}", v3 == null ? "element does not exist" : v3);  
  
XElement e4 = root.Element("Child4");  
int? v4;  
if (e4 == null)  
    v4 = null;  
else  
    v4 = Int32.Parse(e4.Value);  
Console.WriteLine("v4:{0}", v4 == null ? "element does not exist" : v4.ToString());  
```  
  
 <span data-ttu-id="6b82f-129">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6b82f-129">This code produces the following output:</span></span>  
  
```  
c1:child 1 content  
c2:2  
c3:element does not exist  
c4:element does not exist  
  
v1:child 1 content  
v2:2  
v3:element does not exist  
v4:element does not exist  
```  
  
 <span data-ttu-id="6b82f-130">일반적으로 요소 및 특성 내용을 검색하는 데 캐스팅을 사용하면 보다 간단한 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b82f-130">In general, you can write simpler code when using casting to retrieve the contents of elements and attributes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b82f-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6b82f-131">See Also</span></span>  
 [<span data-ttu-id="6b82f-132">LINQ to XML 축(C#)</span><span class="sxs-lookup"><span data-stu-id="6b82f-132">LINQ to XML Axes (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)
