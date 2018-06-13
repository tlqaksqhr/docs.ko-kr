---
title: '방법: 네임스페이스에서 XML로 쿼리 작성(C#)'
ms.date: 07/20/2015
ms.assetid: 7c54df81-15e4-4091-8c81-a87637029130
ms.openlocfilehash: a5de5ffdafc2dd191a35860150e48a86a3603f3c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33320332"
---
# <a name="how-to-write-queries-on-xml-in-namespaces-c"></a><span data-ttu-id="1e4fc-102">방법: 네임스페이스에서 XML로 쿼리 작성(C#)</span><span class="sxs-lookup"><span data-stu-id="1e4fc-102">How to: Write Queries on XML in Namespaces (C#)</span></span>
<span data-ttu-id="1e4fc-103">네임스페이스에 있는 XML에 대한 쿼리를 작성하려면 올바른 네임스페이스를 가진 <xref:System.Xml.Linq.XName> 개체를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e4fc-103">To write a query on XML that is in a namespace, you must use <xref:System.Xml.Linq.XName> objects that have the correct namespace.</span></span>  
  
 <span data-ttu-id="1e4fc-104">C#의 경우 가장 일반적인 방법은 URI가 포함된 문자열을 사용하여 <xref:System.Xml.Linq.XNamespace>를 초기화한 다음 추가 연산자 오버로드를 사용하여 네임스페이스를 로컬 이름과 결합하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1e4fc-104">For C#, the most common approach is to initialize an <xref:System.Xml.Linq.XNamespace> using a string that contains the URI, then use the addition operator overload to combine the namespace with the local name.</span></span>  
  
 <span data-ttu-id="1e4fc-105">이 항목의 첫 번째 예제 집합에서는 기본 네임스페이스에 XML 트리를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1e4fc-105">The first set of examples in this topic shows how to create an XML tree in a default namespace.</span></span> <span data-ttu-id="1e4fc-106">두 번째 예제 집합에서는 접두사가 포함된 네임스페이스에 XML 트리를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1e4fc-106">The second set shows how to create an XML tree in a namespace with a prefix.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e4fc-107">예</span><span class="sxs-lookup"><span data-stu-id="1e4fc-107">Example</span></span>  
 <span data-ttu-id="1e4fc-108">다음 예제에서는 기본 네임스페이스에 있는 XML 트리를 만든 다음</span><span class="sxs-lookup"><span data-stu-id="1e4fc-108">The following example creates an XML tree that is in a default namespace.</span></span> <span data-ttu-id="1e4fc-109">요소의 컬렉션을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="1e4fc-109">It then retrieves a collection of elements.</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = XElement.Parse(  
@"<Root xmlns='http://www.adventure-works.com'>  
    <Child>1</Child>  
    <Child>2</Child>  
    <Child>3</Child>  
    <AnotherChild>4</AnotherChild>  
    <AnotherChild>5</AnotherChild>  
    <AnotherChild>6</AnotherChild>  
</Root>");  
IEnumerable<XElement> c1 =  
    from el in root.Elements(aw + "Child")  
    select el;  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
```  
  
 <span data-ttu-id="1e4fc-110">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="1e4fc-110">This example produces the following output:</span></span>  
  
```  
1  
2  
3  
```  
  
## <a name="example"></a><span data-ttu-id="1e4fc-111">예</span><span class="sxs-lookup"><span data-stu-id="1e4fc-111">Example</span></span>  
 <span data-ttu-id="1e4fc-112">C#의 경우 쿼리를 작성하는 대상이 접두사가 포함된 네임스페이스를 사용하는 XML 트리인지 기본 네임스페이스를 사용하는 XML 트리인지에 관계없이 동일한 방식으로 쿼리를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="1e4fc-112">In C#, you write queries in the same way regardless of whether you are writing queries on an XML tree that uses a namespace with a prefix or on an XML tree with a default namespace.</span></span>  
  
 <span data-ttu-id="1e4fc-113">다음 예제에서는 접두사가 포함된 네임스페이스에 있는 XML 트리를 만든 다음</span><span class="sxs-lookup"><span data-stu-id="1e4fc-113">The following example creates an XML tree that is in a namespace with a prefix.</span></span> <span data-ttu-id="1e4fc-114">요소의 컬렉션을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="1e4fc-114">It then retrieves a collection of elements.</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = XElement.Parse(  
@"<aw:Root xmlns:aw='http://www.adventure-works.com'>  
    <aw:Child>1</aw:Child>  
    <aw:Child>2</aw:Child>  
    <aw:Child>3</aw:Child>  
    <aw:AnotherChild>4</aw:AnotherChild>  
    <aw:AnotherChild>5</aw:AnotherChild>  
    <aw:AnotherChild>6</aw:AnotherChild>  
</aw:Root>");  
IEnumerable<XElement> c1 =  
    from el in root.Elements(aw + "Child")  
    select el;  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
```  
  
 <span data-ttu-id="1e4fc-115">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="1e4fc-115">This example produces the following output:</span></span>  
  
```  
1  
2  
3  
```  
  
## <a name="see-also"></a><span data-ttu-id="1e4fc-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1e4fc-116">See Also</span></span>  
 [<span data-ttu-id="1e4fc-117">XML 네임스페이스 작업(C#)</span><span class="sxs-lookup"><span data-stu-id="1e4fc-117">Working with XML Namespaces (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)
