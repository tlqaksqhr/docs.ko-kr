---
title: "LINQ to XML Annotations2 | Microsoft 문서"
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
ms.assetid: c3e8b3ff-fceb-4428-b0ca-1ed6f128aac8
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 1f2e5bea1cde74548daa1697b6a0a819e3eba3e4
ms.lasthandoff: 03/13/2017


---
# <a name="linq-to-xml-annotations"></a>LINQ to XML 주석
주석을 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 임의의 형식 중 임의의 개체를 XML 트리의 XML 구성 요소와 연결할 수 있도록 합니다.  
  
 와 같은 XML 구성 요소에 주석을 추가 하려면는 <xref:System.Xml.Linq.XElement>또는 <xref:System.Xml.Linq.XAttribute>를 호출 하면는 <xref:System.Xml.Linq.XObject.AddAnnotation%2A>메서드.</xref:System.Xml.Linq.XObject.AddAnnotation%2A> </xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement> 형식별로 주석을 검색할 수 있습니다.  
  
 주석은 XML infoset의 일부가 아니므로 serialize되거나 deserialize되지 않습니다.  
  
## <a name="methods"></a>메서드  
 주석 작업을 할 때 다음 메서드를 사용할 수 있습니다.  
  
|메서드|설명|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XObject.AddAnnotation%2A></xref:System.Xml.Linq.XObject.AddAnnotation%2A>|개체를 <xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject> 의 주석 목록에 추가|  
|<xref:System.Xml.Linq.XObject.Annotation%2A></xref:System.Xml.Linq.XObject.Annotation%2A>|<xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject> 에서 지정 된 형식의 첫 번째 주석 개체를 가져옵니다.|  
|<xref:System.Xml.Linq.XObject.Annotations%2A></xref:System.Xml.Linq.XObject.Annotations%2A>|<xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject> 에 대 한 지정 된 형식의 주석 컬렉션을 가져옵니다.|  
|<xref:System.Xml.Linq.XObject.RemoveAnnotations%2A></xref:System.Xml.Linq.XObject.RemoveAnnotations%2A>|<xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject> 에서 지정 된 형식의 주석을 제거합니다|  
  
## <a name="see-also"></a>참고 항목  
 [고급 LINQ to XML 프로그래밍 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
