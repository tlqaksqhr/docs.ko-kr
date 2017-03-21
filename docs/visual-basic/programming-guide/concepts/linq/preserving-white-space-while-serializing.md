---
title: "공백을 유지 하는 동안 Serializing2 | Microsoft 문서"
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
ms.assetid: 2d7abbd4-37f4-422b-89dd-0a694b5edc17
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9efa2940af9321401e7f9c01d6fb9d1f48616711
ms.lasthandoff: 03/13/2017

---
# <a name="preserving-white-space-while-serializing"></a>serialize할 때 공백 유지
이 항목에서는 XML 트리를 serialize할 때 공백을 제어하는 방법에 대해 설명합니다.  
  
 일반적인 시나리오는 들여쓴 XML을 읽고 공백 텍스트 노드 없이 메모리 내 XML 트리를 만든 다음(공백을 유지하지 않음) XML에 대한 작업을 수행하고 들여쓰기를 사용하여 XML을 저장하는 것입니다. 서식이 있는 XML을 serialize하는 경우 XML 트리의 유효 공백만 유지됩니다. 이것이 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]의 기본 동작입니다.  
  
 다른 일반적인 시나리오는 이미 의도적으로 들여쓴 XML을 읽고 수정하는 것입니다. 이 들여쓰기를 변경하려고 하지 않을 수 있습니다. [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]에서는 XML을 로드하거나 구문 분석할 때 공백을 유지하고 XML을 serialize할 때 서식을 해제하는 경우 이렇게 할 수 있습니다.  
  
## <a name="white-space-behavior-of-methods-that-serialize-xml-trees"></a>XML 트리를 serialize하는 메서드의 공백 동작  
 다음 메서드는 <xref:System.Xml.Linq.XElement>및 <xref:System.Xml.Linq.XDocument>클래스는 XML 트리를 serialize 합니다.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> 파일에 XML 트리를 serialize 할 수는 <xref:System.IO.TextReader>, 또는 <xref:System.Xml.XmlReader>.</xref:System.Xml.XmlReader> </xref:System.IO.TextReader> `ToString` 메서드는 문자열로 serialize합니다.  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XElement.ToString%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.ToString%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XDocument.ToString%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.ToString%2A?displayProperty=fullName>  
  
 메서드를 사용 하지 않는 경우 <xref:System.Xml.Linq.SaveOptions>를 인수로 다음 메서드가 됩니다 형식을 (들여쓰는) serialize 된 XML.</xref:System.Xml.Linq.SaveOptions> 이 경우 XML 트리의 모든 무효 공백이 삭제됩니다.  
  
 메서드가 경우 <xref:System.Xml.Linq.SaveOptions>를 인수로 지정할 수 있습니다 메서드가 하지 형식을 (들여쓰는) serialize 된 XML.</xref:System.Xml.Linq.SaveOptions> 이 경우 XML 트리의 모든 공백이 유지됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [XML 트리 (Visual Basic)를 직렬화 하는 작업](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
