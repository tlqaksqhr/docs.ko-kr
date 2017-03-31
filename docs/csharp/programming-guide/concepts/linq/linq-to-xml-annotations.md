---
title: "LINQ to XML 주석3 | Microsoft 문서"
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
ms.assetid: 54e7b9d0-07f5-488f-9065-b6e6b870f810
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 13718f509eee46853020cfe1dd27ee85437d2e6d
ms.lasthandoff: 03/13/2017


---
# <a name="linq-to-xml-annotations"></a>LINQ to XML 주석
[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]에서 주석을 사용하여 임의의 형식에 대한 임의의 개체를 XML 트리의 XML 구성 요소와 연결할 수 있습니다.  
  
 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XAttribute>와 같은 XML 구성 요소에 주석을 추가하려면 <xref:System.Xml.Linq.XObject.AddAnnotation%2A> 메서드를 호출합니다. 형식별로 주석을 검색할 수 있습니다.  
  
 주석은 XML infoset의 일부가 아니므로 serialize되거나 deserialize되지 않습니다.  
  
## <a name="methods"></a>메서드  
 주석 작업을 할 때 다음 메서드를 사용할 수 있습니다.  
  
|메서드|설명|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XObject.AddAnnotation%2A>|<xref:System.Xml.Linq.XObject>의 주석 목록에 개체를 추가합니다.|  
|<xref:System.Xml.Linq.XObject.Annotation%2A>|지정된 형식의 첫 번째 주석 개체를 <xref:System.Xml.Linq.XObject>에서 가져옵니다.|  
|<xref:System.Xml.Linq.XObject.Annotations%2A>|<xref:System.Xml.Linq.XObject>에 대한 지정된 형식의 주석 컬렉션을 가져옵니다.|  
|<xref:System.Xml.Linq.XObject.RemoveAnnotations%2A>|지정된 형식의 주석을 <xref:System.Xml.Linq.XObject>에서 제거합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [고급 LINQ to XML 프로그래밍(C#)](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
