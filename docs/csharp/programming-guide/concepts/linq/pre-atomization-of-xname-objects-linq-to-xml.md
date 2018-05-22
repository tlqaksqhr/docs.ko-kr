---
title: XName 개체의 사전 원자화(LINQ to XML)(C#)
ms.date: 07/20/2015
ms.assetid: e84fbbe7-f072-4771-bfbb-059d18e1ad15
ms.openlocfilehash: 8d793dcdfd2669fa96c92be0e0e3c3ebb8f38d0e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="pre-atomization-of-xname-objects-linq-to-xml-c"></a><span data-ttu-id="eba54-102">XName 개체의 사전 원자화(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="eba54-102">Pre-Atomization of XName Objects (LINQ to XML) (C#)</span></span>
<span data-ttu-id="eba54-103">LINQ to XML의 성능을 향상시키는 한 가지 방법은 <xref:System.Xml.Linq.XName> 개체를 사전 원자화하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="eba54-103">One way to improve performance in LINQ to XML is to pre-atomize <xref:System.Xml.Linq.XName> objects.</span></span> <span data-ttu-id="eba54-104">사전 원자화는 <xref:System.Xml.Linq.XName> 및 <xref:System.Xml.Linq.XElement> 클래스의 생성자를 사용하여 XML 트리를 만들기 전에 문자열을 <xref:System.Xml.Linq.XAttribute> 개체에 할당하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="eba54-104">Pre-atomization means that you assign a string to an <xref:System.Xml.Linq.XName> object before you create the XML tree by using the constructors of the <xref:System.Xml.Linq.XElement> and  <xref:System.Xml.Linq.XAttribute> classes.</span></span> <span data-ttu-id="eba54-105">그런 다음 문자열을 생성자에 전달하여 문자열을 <xref:System.Xml.Linq.XName>으로 암시적으로 변환하는 대신 초기화된 <xref:System.Xml.Linq.XName> 개체를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="eba54-105">Then, instead of passing a string to the constructor, which would use the implicit conversion from string to <xref:System.Xml.Linq.XName>, you pass the initialized <xref:System.Xml.Linq.XName> object.</span></span>  
  
 <span data-ttu-id="eba54-106">이렇게 하면 특정 이름이 반복되는 대형 XML 트리를 만드는 경우 성능이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="eba54-106">This improves performance when you create a large XML tree in which specific names are repeated.</span></span> <span data-ttu-id="eba54-107">이렇게 하려면 XML 트리를 만들기 전에 <xref:System.Xml.Linq.XName> 개체를 선언하고 초기화합니다. 그런 다음 요소 및 특성 이름에 대한 문자열을 지정하는 대신 이 <xref:System.Xml.Linq.XName> 개체를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="eba54-107">To do this, you declare and initialize <xref:System.Xml.Linq.XName> objects before you construct the XML tree, and then use the <xref:System.Xml.Linq.XName> objects instead of specifying strings for the element and attribute names.</span></span> <span data-ttu-id="eba54-108">이 방법을 사용하면 같은 이름으로 매우 많은 요소 또는 특성을 만드는 경우 상당한 성능상의 이점을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eba54-108">This technique can yield significant performance gains if you are creating a large number of elements (or attributes) with the same name.</span></span>  
  
 <span data-ttu-id="eba54-109">이 방법을 사용할지 여부를 결정하려면 사용자 시나리오를 사전 원자화해 보는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="eba54-109">You should test pre-atomization with your scenario to decide if you should use it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eba54-110">예제</span><span class="sxs-lookup"><span data-stu-id="eba54-110">Example</span></span>  
 <span data-ttu-id="eba54-111">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="eba54-111">The following example demonstrates this.</span></span>  
  
```csharp  
XName Root = "Root";  
XName Data = "Data";  
XName ID = "ID";  
  
XElement root = new XElement(Root,  
    new XElement(Data,  
        new XAttribute(ID, "1"),  
        "4,100,000"),  
    new XElement(Data,  
        new XAttribute(ID, "2"),  
        "3,700,000"),  
    new XElement(Data,  
        new XAttribute(ID, "3"),  
        "1,150,000")  
);  
  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="eba54-112">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="eba54-112">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Data ID="1">4,100,000</Data>  
  <Data ID="2">3,700,000</Data>  
  <Data ID="3">1,150,000</Data>  
</Root>  
```  
  
 <span data-ttu-id="eba54-113">다음 예제에서는 XML 문서가 네임스페이스에 있는 동일한 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eba54-113">The following example shows the same technique where the XML document is in a namespace:</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XName Root = aw + "Root";  
XName Data = aw + "Data";  
XName ID = "ID";  
  
XElement root = new XElement(Root,  
    new XAttribute(XNamespace.Xmlns + "aw", aw),  
    new XElement(Data,  
        new XAttribute(ID, "1"),  
        "4,100,000"),  
    new XElement(Data,  
        new XAttribute(ID, "2"),  
        "3,700,000"),  
    new XElement(Data,  
        new XAttribute(ID, "3"),  
        "1,150,000")  
);  
  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="eba54-114">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="eba54-114">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Data ID="1">4,100,000</aw:Data>  
  <aw:Data ID="2">3,700,000</aw:Data>  
  <aw:Data ID="3">1,150,000</aw:Data>  
</aw:Root>  
```  
  
 <span data-ttu-id="eba54-115">다음 예제는 실제로 사용될 수 있는 것과 더욱 유사한 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="eba54-115">The following example is more similar to what you will likely encounter in the real world.</span></span> <span data-ttu-id="eba54-116">이 예제에서 요소의 내용은 쿼리를 통해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="eba54-116">In this example, the content of the element is supplied by a query:</span></span>  
  
```csharp  
XName Root = "Root";  
XName Data = "Data";  
XName ID = "ID";  
  
DateTime t1 = DateTime.Now;  
XElement root = new XElement(Root,  
    from i in System.Linq.Enumerable.Range(1, 100000)  
    select new XElement(Data,  
        new XAttribute(ID, i),  
        i * 5)  
);  
DateTime t2 = DateTime.Now;  
  
Console.WriteLine("Time to construct:{0}", t2 - t1);  
```  
  
 <span data-ttu-id="eba54-117">위 예제는 이름이 사전 원자화되지 않은 다음 예제보다 더 나은 성능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="eba54-117">The previous example performs better than the following example, in which names are not pre-atomized:</span></span>  
  
```csharp  
DateTime t1 = DateTime.Now;  
XElement root = new XElement("Root",  
    from i in System.Linq.Enumerable.Range(1, 100000)  
    select new XElement("Data",  
        new XAttribute("ID", i),  
        i * 5)  
);  
DateTime t2 = DateTime.Now;  
  
Console.WriteLine("Time to construct:{0}", t2 - t1);  
```  
  
## <a name="see-also"></a><span data-ttu-id="eba54-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eba54-118">See Also</span></span>  
 [<span data-ttu-id="eba54-119">성능(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="eba54-119">Performance (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/performance-linq-to-xml.md)  
 [<span data-ttu-id="eba54-120">원자화된 XName 및 XNamespace 개체(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="eba54-120">Atomized XName and XNamespace Objects (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/atomized-xname-and-xnamespace-objects-linq-to-xml.md)
