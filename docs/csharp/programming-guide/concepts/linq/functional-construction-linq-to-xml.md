---
title: "함수 생성(LINQ to XML)(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 57a82bcf-de03-4f1c-a0c8-9a76e989d542
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f357de98fae60b3d0b6548ef195b462b4e2f6a5a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="functional-construction-linq-to-xml-c"></a><span data-ttu-id="cd1c7-102">함수 생성(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="cd1c7-102">Functional Construction (LINQ to XML) (C#)</span></span>
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="cd1c7-103">에서는 *함수 생성*이라는 XML 요소를 만드는 강력한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd1c7-103"> provides a powerful way to create XML elements called *functional construction*.</span></span> <span data-ttu-id="cd1c7-104">함수 생성은 단일 문으로 XML 트리를 만드는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="cd1c7-104">Functional construction is the ability to create an XML tree in a single statement.</span></span>  
  
 <span data-ttu-id="cd1c7-105">함수 생성을 가능하게 하는 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 프로그래밍 인터페이스의 몇 가지 주요 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cd1c7-105">There are several key features of the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] programming interface that enable functional construction:</span></span>  
  
-   <span data-ttu-id="cd1c7-106"><xref:System.Xml.Linq.XElement> 생성자는 내용에 대한 다양한 형식의 인수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cd1c7-106">The <xref:System.Xml.Linq.XElement> constructor takes various types of arguments for content.</span></span> <span data-ttu-id="cd1c7-107">예를 들어, 자식 요소가 되는 다른 <xref:System.Xml.Linq.XElement> 개체를 전달할 수 있으며</span><span class="sxs-lookup"><span data-stu-id="cd1c7-107">For example, you can pass another <xref:System.Xml.Linq.XElement> object, which becomes a child element.</span></span> <span data-ttu-id="cd1c7-108">요소의 특성이 되는 <xref:System.Xml.Linq.XAttribute> 개체를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd1c7-108">You can pass an <xref:System.Xml.Linq.XAttribute> object, which becomes an attribute of the element.</span></span> <span data-ttu-id="cd1c7-109">또는 문자열로 변환되고 요소의 텍스트 내용이 되는 다른 모든 형식의 개체를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd1c7-109">Or you can pass any other type of object, which is converted to a string and becomes the text content of the element.</span></span>  
  
-   <span data-ttu-id="cd1c7-110"><xref:System.Xml.Linq.XElement> 생성자는 `params` 형식의 <xref:System.Object> 배열을 사용하므로 생성자에 개수에 관계없이 개체를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd1c7-110">The <xref:System.Xml.Linq.XElement> constructor takes a `params` array of type <xref:System.Object>, so that you can pass any number of objects to the constructor.</span></span> <span data-ttu-id="cd1c7-111">따라서 복잡한 내용을 가진 요소를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd1c7-111">This enables you to create an element that has complex content.</span></span>  
  
-   <span data-ttu-id="cd1c7-112">개체가 <xref:System.Collections.Generic.IEnumerable%601>을 구현하는 경우 개체의 컬렉션이 열거되고 컬렉션의 모든 항목이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd1c7-112">If an object implements <xref:System.Collections.Generic.IEnumerable%601>, the collection in the object is enumerated, and all items in the collection are added.</span></span> <span data-ttu-id="cd1c7-113">컬렉션에 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XAttribute> 개체가 포함되어 있으면 컬렉션의 각 항목이 개별적으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd1c7-113">If the collection contains <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, each item in the collection is added separately.</span></span> <span data-ttu-id="cd1c7-114">이것은 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리의 결과를 생성자에 전달할 수 있도록 하기 때문에 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="cd1c7-114">This is important because it lets you pass the results of a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query to the constructor.</span></span>  
  
 <span data-ttu-id="cd1c7-115">이러한 기능을 사용하여 XML 트리를 만드는 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd1c7-115">These features enable you to write code to create an XML tree.</span></span> <span data-ttu-id="cd1c7-116">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cd1c7-116">The following is an example:</span></span>  
  
```csharp  
XElement contacts =  
    new XElement("Contacts",  
        new XElement("Contact",  
            new XElement("Name", "Patrick Hines"),  
            new XElement("Phone", "206-555-0144"),  
            new XElement("Address",  
                new XElement("Street1", "123 Main St"),  
                new XElement("City", "Mercer Island"),  
                new XElement("State", "WA"),  
                new XElement("Postal", "68042")  
            )  
        )  
    );  
```  
  
 <span data-ttu-id="cd1c7-117">또한 이러한 기능을 사용하여 XML 트리를 만들 때 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리의 결과를 사용하는 코드를 다음과 같이 작성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd1c7-117">These features also enable you to write code that uses the results of [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries when you create an XML tree, as follows:</span></span>  
  
```csharp  
XElement srcTree = new XElement("Root",  
    new XElement("Element", 1),  
    new XElement("Element", 2),  
    new XElement("Element", 3),  
    new XElement("Element", 4),  
    new XElement("Element", 5)  
);  
XElement xmlTree = new XElement("Root",  
    new XElement("Child", 1),  
    new XElement("Child", 2),  
    from el in srcTree.Elements()  
    where (int)el > 2  
    select el  
);  
Console.WriteLine(xmlTree);  
```  
  
 <span data-ttu-id="cd1c7-118">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="cd1c7-118">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cd1c7-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cd1c7-119">See Also</span></span>  
 [<span data-ttu-id="cd1c7-120">XML 트리 만들기(C#)</span><span class="sxs-lookup"><span data-stu-id="cd1c7-120">Creating XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md)
