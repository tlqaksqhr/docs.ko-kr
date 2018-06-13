---
title: 원자화된 XName 및 XNamespace 개체(LINQ to XML)(C#)
ms.date: 07/20/2015
ms.assetid: a5b21433-b49d-415c-b00e-bcbfb0d267d7
ms.openlocfilehash: 85799741246f484bcb17a1ae7e320bd477872238
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33323211"
---
# <a name="atomized-xname-and-xnamespace-objects-linq-to-xml-c"></a><span data-ttu-id="5abf8-102">원자화된 XName 및 XNamespace 개체(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="5abf8-102">Atomized XName and XNamespace Objects (LINQ to XML) (C#)</span></span>
<span data-ttu-id="5abf8-103"><xref:System.Xml.Linq.XName> 및 <xref:System.Xml.Linq.XNamespace> 개체는 *원자화*됩니다. 즉, 이들 개체의 정규화된 이름이 같으면 같은 개체를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="5abf8-103"><xref:System.Xml.Linq.XName> and <xref:System.Xml.Linq.XNamespace> objects are *atomized*; that is, if they contain the same qualified name, they refer to the same object.</span></span> <span data-ttu-id="5abf8-104">이를 통해 쿼리 성능이 향상될 수 있습니다. 두 개의 원자화된 이름이 같은지 비교하는 경우 기본 중간 언어에서 이 두 개의 참조가 같은 개체를 가리키는지 여부만 확인하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5abf8-104">This yields performance benefits for queries: When you compare two atomized names for equality, the underlying intermediate language only has to determine whether the two references point to the same object.</span></span> <span data-ttu-id="5abf8-105">기본 코드는 시간이 많이 걸리는 문자열 비교를 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5abf8-105">The underlying code does not have to do string comparisons, which would be time consuming.</span></span>  
  
## <a name="atomization-semantics"></a><span data-ttu-id="5abf8-106">원자화 의미 체계</span><span class="sxs-lookup"><span data-stu-id="5abf8-106">Atomization Semantics</span></span>  
 <span data-ttu-id="5abf8-107">원자화는 두 <xref:System.Xml.Linq.XName> 개체가 같은 로컬 이름을 갖고 있고 동일한 네임스페이스에 있는 경우 동일한 인스턴스를 공유함을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="5abf8-107">Atomization means that if two <xref:System.Xml.Linq.XName> objects have the same local name, and they are in the same namespace, they share the same instance.</span></span> <span data-ttu-id="5abf8-108">마찬가지로 두 <xref:System.Xml.Linq.XNamespace> 개체가 같은 네임스페이스 URI를 갖고 있으면 같은 인스턴스를 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="5abf8-108">In the same way, if two <xref:System.Xml.Linq.XNamespace> objects have the same namespace URI, they share the same instance.</span></span>  
  
 <span data-ttu-id="5abf8-109">클래스가 원자화된 개체를 사용하려면 클래스에 대한 생성자가 public이 아니라 private이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5abf8-109">For a class to enable atomized objects, the constructor for the class must be private, not public.</span></span> <span data-ttu-id="5abf8-110">이는 생성자가 public인 경우 원자화되지 않은 개체를 생성할 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="5abf8-110">This is because if the constructor were public, you could create a non-atomized object.</span></span> <span data-ttu-id="5abf8-111"><xref:System.Xml.Linq.XName> 및 <xref:System.Xml.Linq.XNamespace> 클래스는 문자열을 <xref:System.Xml.Linq.XName> 또는 <xref:System.Xml.Linq.XNamespace>로 변환하는 암시적 변환 연산자를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="5abf8-111">The <xref:System.Xml.Linq.XName> and <xref:System.Xml.Linq.XNamespace> classes implement an implicit conversion operator to convert a string into an <xref:System.Xml.Linq.XName> or <xref:System.Xml.Linq.XNamespace>.</span></span> <span data-ttu-id="5abf8-112">이를 통해 이러한 개체의 인스턴스를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5abf8-112">This is how you get an instance of these objects.</span></span> <span data-ttu-id="5abf8-113">생성자는 액세스할 수 없으므로 생성자를 사용하여 인스턴스를 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5abf8-113">You cannot get an instance by using a constructor, because the constructor is inaccessible.</span></span>  
  
 <span data-ttu-id="5abf8-114"><xref:System.Xml.Linq.XName> 및 <xref:System.Xml.Linq.XNamespace>는 비교하는 두 개체가 같은 인스턴스를 참조하는지 확인하기 위해 같음 연산자 및 같지 않음 연산자도 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="5abf8-114"><xref:System.Xml.Linq.XName> and <xref:System.Xml.Linq.XNamespace> also implement the equality and inequality operators, to determine whether the two objects being compared are references to the same instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5abf8-115">예</span><span class="sxs-lookup"><span data-stu-id="5abf8-115">Example</span></span>  
 <span data-ttu-id="5abf8-116">다음 코드에서는 몇 가지 <xref:System.Xml.Linq.XElement> 개체를 만들어 동일한 이름이 같은 인스턴스를 공유함을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5abf8-116">The following code creates some <xref:System.Xml.Linq.XElement> objects and demonstrates that identical names share the same instance.</span></span>  
  
```csharp  
XElement r1 = new XElement("Root", "data1");  
XElement r2 = XElement.Parse("<Root>data2</Root>");  
  
if ((object)r1.Name == (object)r2.Name)  
    Console.WriteLine("r1 and r2 have names that refer to the same instance.");  
else  
    Console.WriteLine("Different");  
  
XName n = "Root";  
  
if ((object)n == (object)r1.Name)  
    Console.WriteLine("The name of r1 and the name in 'n' refer to the same instance.");  
else  
    Console.WriteLine("Different");  
```  
  
 <span data-ttu-id="5abf8-117">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="5abf8-117">This example produces the following output:</span></span>  
  
```  
r1 and r2 have names that refer to the same instance.  
The name of r1 and the name in 'n' refer to the same instance.  
```  
  
 <span data-ttu-id="5abf8-118">앞에서 설명했듯이 원자화된 개체의 이점은 <xref:System.Xml.Linq.XName>을 매개 변수로 사용하는 축 메서드를 사용하는 경우 축 메서드에서 두 이름이 원하는 요소를 선택하는 같은 인스턴스를 참조하는지 여부만 확인하면 된다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5abf8-118">As mentioned earlier, the benefit of atomized objects is that when you use one of the axis methods that take an <xref:System.Xml.Linq.XName> as a parameter, the axis method only has to determine that two names reference the same instance to select the desired elements.</span></span>  
  
 <span data-ttu-id="5abf8-119">다음 예제에서는 <xref:System.Xml.Linq.XName>을 <xref:System.Xml.Linq.XContainer.Descendants%2A> 메서드 호출로 전달합니다. 그러면 원자화 패턴으로 인해 성능이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="5abf8-119">The following example passes an <xref:System.Xml.Linq.XName> to the <xref:System.Xml.Linq.XContainer.Descendants%2A> method call, which then has better performance because of the atomization pattern.</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("C1", 1),  
    new XElement("Z1",  
        new XElement("C1", 2),  
        new XElement("C1", 1)  
    )  
);  
  
var query = from e in root.Descendants("C1")  
            where (int)e == 1  
            select e;  
  
foreach (var z in query)  
    Console.WriteLine(z);  
```  
  
 <span data-ttu-id="5abf8-120">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="5abf8-120">This example produces the following output:</span></span>  
  
```xml  
<C1>1</C1>  
<C1>1</C1>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5abf8-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5abf8-121">See Also</span></span>  
 [<span data-ttu-id="5abf8-122">성능(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="5abf8-122">Performance (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/performance-linq-to-xml.md)
