---
title: "로드 또는 XML2 구문 분석할 때 공백 유지 | Microsoft 문서"
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
ms.assetid: ef6518e0-2c8d-462c-8b92-a16e9dc737ad
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 39e4270acc0e9a9df5c3855f8c087f41d9612197
ms.lasthandoff: 03/13/2017

---
# <a name="preserving-white-space-while-loading-or-parsing-xml"></a>XML을 로드 또는 구문 분석할 때 공백 유지
이 항목에서는 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]의 공백 동작을 제어하는 방법에 대해 설명합니다.  
  
 일반적인 시나리오는 들여쓴 XML을 읽고 공백 텍스트 노드 없이 메모리 내 XML 트리를 만든 다음(공백을 유지하지 않음) XML에 대한 작업을 수행하고 들여쓰기를 사용하여 XML을 저장하는 것입니다. 서식이 있는 XML을 serialize하는 경우 XML 트리의 유효 공백만 유지됩니다. 이것이 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]의 기본 동작입니다.  
  
 다른 일반적인 시나리오는 이미 의도적으로 들여쓴 XML을 읽고 수정하는 것입니다. 이 들여쓰기를 변경하려고 하지 않을 수 있습니다. [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]에서는 XML을 로드하거나 구문 분석할 때 공백을 유지하고 XML을 serialize할 때 서식을 해제하는 경우 이렇게 할 수 있습니다.  
  
 이 항목에서는 XML 트리를 채우는 메서드의 공백 동작에 대해 설명합니다. XML 트리를 serialize 할 때 공백을 제어 하는 방법에 대 한 정보를 참조 하십시오. [유지 공백 동안 직렬화](../../../../visual-basic/programming-guide/concepts/linq/preserving-white-space-while-serializing.md)합니다.  
  
## <a name="behavior-of-methods-that-populate-xml-trees"></a>XML 트리를 채우는 메서드의 동작  
 다음 메서드는 <xref:System.Xml.Linq.XElement>및 <xref:System.Xml.Linq.XDocument>클래스는 XML 트리를 채웁니다.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> 파일에서 XML 트리를 채울 수는 <xref:System.IO.TextReader>, <xref:System.Xml.XmlReader>, 또는 문자열:</xref:System.Xml.XmlReader> </xref:System.IO.TextReader>  
  
-   <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName>  
  
 메서드를 사용 하지 않는 경우 <xref:System.Xml.Linq.LoadOptions>를 인수로 메서드에 불필요 한 공백을 유지 하지 것입니다.</xref:System.Xml.Linq.LoadOptions>  
  
 대부분의 경우, 메서드가 사용 <xref:System.Xml.Linq.LoadOptions>를 인수로 하면 선택적으로 유지할 수 무효 공백이 XML 트리의 텍스트 노드로.</xref:System.Xml.Linq.LoadOptions> 그러나 메서드는 XML을 로드 하는 경우는 <xref:System.Xml.XmlReader>, 그런 다음 <xref:System.Xml.XmlReader>여부 공백이 유지할지 여부를 결정 합니다.</xref:System.Xml.XmlReader> </xref:System.Xml.XmlReader> 설정 <xref:System.Xml.Linq.LoadOptions>아무런 효과가 없습니다.</xref:System.Xml.Linq.LoadOptions>  
  
 이러한 메서드를 통해 공백이 유지 됩니다 무효 공백이 삽입 됩니다 XML 트리에 <xref:System.Xml.Linq.XText>노드.</xref:System.Xml.Linq.XText> 공백이 유지되지 않으면 텍스트 노드가 삽입되지 않습니다.  
  
 <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> 를 사용 하 여 XML 트리를 만들 수 있습니다. 기록 되는 노드는 <xref:System.Xml.XmlWriter>트리에 채워집니다.</xref:System.Xml.XmlWriter> 그러나 이 메서드를 사용하여 XML 트리를 빌드하면 노드가 공백인지 여부나 유효한지 여부에 관계없이 모든 노드가 유지됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [(Visual Basic) XML 구문 분석](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
