---
title: "방법: 파일, 문자열 또는 스트림에 (Visual Basic)에서 XML을 로드 | Microsoft 문서"
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
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 242c8b79cbe1329b6f53e9fd4e5495d4a157e08c
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a>방법: 파일, 문자열 또는 스트림에서 XML 로드(Visual Basic)
만들 수 있습니다 [XML 리터럴을](../../../../visual-basic/language-reference/xml-literals/index.md) 몇 가지 메서드를 사용 하 여 파일, 문자열, 또는 스트림과 같은 외부 소스에서 내용으로 채웁니다. 이러한 메서드는 다음 예제에 표시 됩니다.  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-load-xml-from-a-file"></a>파일에서 XML을 로드 하려면  
  
-   와 같은 리터럴 XML을 채우는 데는 <xref:System.Xml.Linq.XElement>또는 <xref:System.Xml.Linq.XDocument>사용 하 여 파일에서 개체는 `Load` 메서드.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> 이 메서드는 파일 경로, 텍스트 스트림에 또는 XML 스트림을 입력으로 걸릴 수 있습니다.  
  
     다음 코드 예제에서는 <xref:System.Xml.Linq.XDocument.Load%28System.String%29>를 채우는 메서드는 <xref:System.Xml.Linq.XDocument>텍스트 파일에서 XML로 개체.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XDocument.Load%28System.String%29>  
  
     [!code-vb[VbXMLSamples #&43;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_1.vb)]  
  
### <a name="to-load-xml-from-a-string"></a>문자열에서 XML을 로드 하려면  
  
-   와 같은 리터럴 XML을 채우는 데는 <xref:System.Xml.Linq.XElement>또는 <xref:System.Xml.Linq.XDocument>개체는 문자열에서 사용할 수는 `Parse` 메서드.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement>  
  
     다음 코드 예제에서는 <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=fullName>를 채우는 메서드는 <xref:System.Xml.Linq.XDocument>문자열에서 XML로 개체.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=fullName>  
  
     [!code-vb[VbXMLSamples #&47;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_2.vb)]  
  
### <a name="to-load-xml-from-a-stream"></a>스트림에서 XML을 로드 하려면  
  
-   와 같은 리터럴 XML을 채우는 데는 <xref:System.Xml.Linq.XElement>또는 <xref:System.Xml.Linq.XDocument>개체는 스트림, 사용할 수는 `Load` 메서드 또는 <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=fullName>메서드.</xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=fullName> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement>  
  
 다음 코드 예제에서는 <xref:System.Xml.Linq.XNode.ReadFrom%2A>를 채우는 메서드는 <xref:System.Xml.Linq.XDocument>개체를 XML 스트림의 xml.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XNode.ReadFrom%2A>  
  
 [!code-vb[VbXMLSamples #&46;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_3.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>   
 <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>   
 <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>   
 <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName>   
 <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=fullName></xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=fullName>   
 [XML 리터럴](../../../../visual-basic/language-reference/xml-literals/index.md)   
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)   
 [Visual Basic에서 XML 조작](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)

