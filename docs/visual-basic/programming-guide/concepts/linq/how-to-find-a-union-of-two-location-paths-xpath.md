---
title: "방법: 두 위치 경로 (XPath 및 LINQ to XML)의 공용 구조체 찾기 (Visual Basic) | Microsoft 문서"
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
ms.assetid: c82c09b4-cb0a-47ec-8cc3-a124144c2788
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 90fe1bd9a7992c5e3f4c57f5596a88e5be506917
ms.contentlocale: ko-kr
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-find-a-union-of-two-location-paths-xpath-linq-to-xml-visual-basic"></a>방법: 두 위치 경로 (XPath 및 LINQ to XML)의 공용 구조체 찾기 (Visual Basic)
XPath를 사용하여 두 XPath 위치 경로의 통합을 찾을 수 있습니다.  
  
 XPath 식은 다음과 같습니다.  
  
 `//Category|//Price`  
  
 사용 하 여 동일한 결과 얻을 수는 <xref:System.Linq.Enumerable.Concat%2A>표준 쿼리 연산자.</xref:System.Linq.Enumerable.Concat%2A>  
  
## <a name="example"></a>예제  
 이 예제에서는 모든 `Category` 요소와 모든 `Price` 요소를 찾은 다음 단일 컬렉션으로 연결합니다. [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 호출 쿼리 <xref:System.Xml.Linq.Extensions.InDocumentOrder%2A>결과를 정렬 합니다.</xref:System.Xml.Linq.Extensions.InDocumentOrder%2A> XPath 식 계산의 결과도 문서 순서로 되어 있습니다.  
  
 이 예제에서는 다음 XML 문서: [샘플 XML 파일: 숫자 데이터 (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md)합니다.  
  
```vb  
Dim data As XDocument = XDocument.Load("Data.xml")  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XElement) = _  
    data...<Category>.Concat(data...<Price>).InDocumentOrder()  
  
' XPath expression  
Dim list2 As IEnumerable(Of XElement) = _  
    data.XPathSelectElements("//Category|//Price")  
  
If list1.Count() = list2.Count() And _  
        list1.Intersect(list2).Count() = list1.Count() Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
For Each el As XElement In list1  
    Console.WriteLine(el)  
Next  
```  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```  
Results are identical  
<Category>A</Category>  
<Price>24.50</Price>  
<Category>B</Category>  
<Price>89.99</Price>  
<Category>A</Category>  
<Price>4.95</Price>  
<Category>A</Category>  
<Price>66.00</Price>  
<Category>B</Category>  
<Price>.99</Price>  
<Category>A</Category>  
<Price>29.00</Price>  
<Category>B</Category>  
<Price>6.99</Price>  
```  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to XML에 대 한 XPath 사용자 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)

