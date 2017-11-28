---
title: "방법: 특성 값 검색(LINQ to XML)(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 817bbe89-5979-4234-bf0c-46f63692ac8c
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 12720ca8bd1937d37f8d30400e0b25afa22a40cc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-retrieve-the-value-of-an-attribute-linq-to-xml-c"></a><span data-ttu-id="e74fb-102">방법: 특성 값 검색(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="e74fb-102">How to: Retrieve the Value of an Attribute (LINQ to XML) (C#)</span></span>
<span data-ttu-id="e74fb-103">이 항목에서는 특성의 값을 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e74fb-103">This topic shows how to obtain the value of attributes.</span></span> <span data-ttu-id="e74fb-104">두 가지 주요 방법이 있습니다. <xref:System.Xml.Linq.XAttribute>를 원하는 형식으로 캐스팅할 수 있습니다. 그러면 명시적 변환 연산자가 요소나 특성의 내용을 지정된 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="e74fb-104">There are two main ways: You can cast an <xref:System.Xml.Linq.XAttribute> to the desired type; the explicit conversion operator then converts the contents of the element or attribute to the specified type.</span></span> <span data-ttu-id="e74fb-105">또는 <xref:System.Xml.Linq.XAttribute.Value%2A> 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e74fb-105">Alternatively, you can use the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span> <span data-ttu-id="e74fb-106">그러나 일반적으로 캐스팅이 더 나은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="e74fb-106">However, casting is generally the better approach.</span></span> <span data-ttu-id="e74fb-107">특성을 nullable 형식으로 캐스팅하면 존재하지 않을 수도 있는 특성의 값을 검색하는 경우 코드를 더 간단하게 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e74fb-107">If you cast the attribute to a nullable type, the code is simpler to write when retrieving the value of an attribute that might or might not exist.</span></span> <span data-ttu-id="e74fb-108">이 방법의 예제는 [방법: 요소 값 검색(LINQ to XML)(C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e74fb-108">For examples of this technique, see [How to: Retrieve the Value of an Element (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e74fb-109">예제</span><span class="sxs-lookup"><span data-stu-id="e74fb-109">Example</span></span>  
 <span data-ttu-id="e74fb-110">특성의 값을 검색하려면 <xref:System.Xml.Linq.XAttribute> 개체를 원하는 형식으로 캐스팅하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e74fb-110">To retrieve the value of an attribute, you just cast the <xref:System.Xml.Linq.XAttribute> object to your desired type.</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
                    new XAttribute("Attr", "abcde")  
                );  
Console.WriteLine(root);  
string str = (string)root.Attribute("Attr");  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="e74fb-111">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e74fb-111">This example produces the following output:</span></span>  
  
```  
<Root Attr="abcde" />  
abcde  
```  
  
## <a name="example"></a><span data-ttu-id="e74fb-112">예제</span><span class="sxs-lookup"><span data-stu-id="e74fb-112">Example</span></span>  
 <span data-ttu-id="e74fb-113">다음 예제에서는 특성이 네임스페이스에 있는 경우 특성의 값을 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e74fb-113">The following example shows how to retrieve the value of an attribute where the attribute is in a namespace.</span></span> <span data-ttu-id="e74fb-114">자세한 내용은 [XML 네임스페이스 작업(C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e74fb-114">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = new XElement(aw + "Root",  
                    new XAttribute(aw + "Attr", "abcde")  
                );  
string str = (string)root.Attribute(aw + "Attr");  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="e74fb-115">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e74fb-115">This example produces the following output:</span></span>  
  
```  
abcde  
```  
  
## <a name="see-also"></a><span data-ttu-id="e74fb-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e74fb-116">See Also</span></span>  
 [<span data-ttu-id="e74fb-117">LINQ to XML 축(C#)</span><span class="sxs-lookup"><span data-stu-id="e74fb-117">LINQ to XML Axes (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)
