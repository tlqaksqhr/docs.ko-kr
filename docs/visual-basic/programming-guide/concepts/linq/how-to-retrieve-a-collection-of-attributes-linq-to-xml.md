---
title: '방법: 특성 (LINQ to XML)의 컬렉션을 검색 (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: a07e9645-b45b-403b-b698-f652f904c7d2
ms.openlocfilehash: fdb7f236339de242a887f3040e33b8d24eb114f4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33641169"
---
# <a name="how-to-retrieve-a-collection-of-attributes-linq-to-xml-visual-basic"></a><span data-ttu-id="a74ee-102">방법: 특성 (LINQ to XML)의 컬렉션을 검색 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a74ee-102">How to: Retrieve a Collection of Attributes (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="a74ee-103">이 항목에서는 <xref:System.Xml.Linq.XElement.Attributes%2A> 메서드에 대해 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="a74ee-103">This topic introduces the <xref:System.Xml.Linq.XElement.Attributes%2A> method.</span></span> <span data-ttu-id="a74ee-104">이 메서드는 요소의 특성을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="a74ee-104">This method retrieves the attributes of an element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a74ee-105">예제</span><span class="sxs-lookup"><span data-stu-id="a74ee-105">Example</span></span>  
 <span data-ttu-id="a74ee-106">다음 예제에서는 요소의 특성 컬렉션을 반복하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a74ee-106">The following example shows how to iterate through the collection of attributes of an element.</span></span>  
  
```vb  
Dim val = _  
    <Value ID="1243" Type="int" ConvertableTo="double">100</Value>  
Dim listOfAttributes As IEnumerable(Of XAttribute) = _  
    From att In val.Attributes() _  
    Select att  
For Each att As XAttribute In listOfAttributes  
    Console.WriteLine(att)  
Next  
```  
  
 <span data-ttu-id="a74ee-107">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a74ee-107">This code produces the following output:</span></span>  
  
```  
ID="1243"  
Type="int"  
ConvertableTo="double"  
```  
  
## <a name="see-also"></a><span data-ttu-id="a74ee-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a74ee-108">See Also</span></span>  
 [<span data-ttu-id="a74ee-109">LINQ to XML 축(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a74ee-109">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
