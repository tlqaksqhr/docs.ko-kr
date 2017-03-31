---
title: "방법: 특성 컬렉션 검색(LINQ to XML)(C#) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: a49ee7a3-b2c2-4d49-9b5c-b7c6c41f4f13
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 646e012392c3c49de1f89b170416fc00f24e5dae
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-retrieve-a-collection-of-attributes-linq-to-xml-c"></a>방법: 특성 컬렉션 검색(LINQ to XML)(C#)
이 항목에서는 <xref:System.Xml.Linq.XElement.Attributes%2A> 메서드를 소개합니다. 이 메서드는 요소의 특성을 검색합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 요소의 특성 컬렉션을 반복하는 방법을 보여 줍니다.  
  
```csharp  
XElement val = new XElement("Value",  
    new XAttribute("ID", "1243"),  
    new XAttribute("Type", "int"),  
    new XAttribute("ConvertableTo", "double"),  
    "100");  
IEnumerable<XAttribute> listOfAttributes =  
    from att in val.Attributes()  
    select att;  
foreach (XAttribute a in listOfAttributes)  
    Console.WriteLine(a);  
```  
  
 이 코드의 결과는 다음과 같습니다.  
  
```  
ID="1243"  
Type="int"  
ConvertableTo="double"  
```  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to XML 축(C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)
