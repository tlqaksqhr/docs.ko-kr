---
title: "방법: 특성 (LINQ to XML)의 컬렉션을 검색 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a07e9645-b45b-403b-b698-f652f904c7d2
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 934559b5c27d243930c191dd3d601fbf8c5beb65
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-retrieve-a-collection-of-attributes-linq-to-xml-visual-basic"></a>방법: 특성 (LINQ to XML)의 컬렉션을 검색 (Visual Basic)
이 항목에서는 <xref:System.Xml.Linq.XElement.Attributes%2A> 메서드에 대해 소개합니다. 이 메서드는 요소의 특성을 검색합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 요소의 특성 컬렉션을 반복하는 방법을 보여 줍니다.  
  
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
  
 이 코드의 결과는 다음과 같습니다.  
  
```  
ID="1243"  
Type="int"  
ConvertableTo="double"  
```  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to XML 축(Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
