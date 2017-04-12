---
title: "Files, TextWriters 및 XmlWriters3로 | Microsoft 문서"
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
ms.assetid: 7a0c24df-79ef-41a0-87f5-e6cf79382da9
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
ms.openlocfilehash: 98662b8d84459ed051d048084c2755fa7aaf8247
ms.lasthandoff: 03/13/2017

---
# <a name="serializing-to-files-textwriters-and-xmlwriters"></a>Files, TextWriters 및 XmlWriters로 serialization
XML 트리를 serialize 할 수는 <xref:System.IO.File>, <xref:System.IO.TextWriter>, 또는 <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.IO.TextWriter> </xref:System.IO.File>  
  
 XML 구성 요소를 serialize 할 수 있습니다 포함 하 여 <xref:System.Xml.Linq.XDocument>및 <xref:System.Xml.Linq.XElement>를 사용 하 여 문자열에는 `ToString` 메서드.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument>  
  
 문자열로 직렬화 할 때 서식 지정을 방지 하려는 경우 사용할 수 있습니다는 <xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=fullName>메서드.</xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=fullName>  
  
 (들여쓰기)는 결과 XML 문서 서식을 지정 하는 파일에 직렬화 할 때 모드용 기본 동작이입니다. 들여쓰는 경우 XML 트리의 무효 공백은 유지되지 않습니다. 서식을 사용 하 여 serialize 할 사용 하지 않는 다음 메서드의 오버 로드 중 하나를 사용 <xref:System.Xml.Linq.SaveOptions>인수로:</xref:System.Xml.Linq.SaveOptions>  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName>  
  
 XML 트리에서 무효 공백을 유지 하려면 옵션을 들여쓸를 하려는 경우 사용 하는 다음 메서드의 오버 로드 중 하나를 사용 <xref:System.Xml.Linq.SaveOptions>인수로:</xref:System.Xml.Linq.SaveOptions>  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName>  
  
 예제를 보려면 적절한 참조 항목을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [XML 트리 (Visual Basic)를 직렬화 하는 작업](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
