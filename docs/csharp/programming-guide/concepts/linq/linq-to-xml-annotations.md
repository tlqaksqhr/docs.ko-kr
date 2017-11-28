---
title: "LINQ to XML 주석3"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 54e7b9d0-07f5-488f-9065-b6e6b870f810
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: eadbc55ac6188fa3634745bf8bb222f07675a308
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="linq-to-xml-annotations"></a>LINQ to XML 주석
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]에서 주석을 사용하여 임의의 형식에 대한 임의의 개체를 XML 트리의 XML 구성 요소와 연결할 수 있습니다.  
  
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
