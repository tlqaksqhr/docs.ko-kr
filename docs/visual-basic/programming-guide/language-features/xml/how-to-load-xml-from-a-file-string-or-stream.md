---
title: '방법: 파일, 문자열 또는 스트림에서 XML 로드(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
ms.openlocfilehash: 241f6552e46d7689b42a409ba44bc747984773ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647633"
---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a>방법: 파일, 문자열 또는 스트림에서 XML 로드(Visual Basic)
만들 수 있습니다 [XML 리터럴을](../../../../visual-basic/language-reference/xml-literals/index.md) 여러 가지 방법을 사용 하 여 파일, 문자열 또는 스트림에 같은 외부 소스에서 내용으로 채웁니다. 이러한 메서드는 다음 예제에 표시 됩니다.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-load-xml-from-a-file"></a>파일에서 XML을 로드 하지  
  
-   XML과 같은 리터럴 채우려면는 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument> 을 사용 하 여 파일에서 개체는 `Load` 메서드. 이 메서드는 입력으로는 파일 경로, 텍스트 스트림에 또는 XML 스트림을 걸릴 수 있습니다.  
  
     다음 코드 예제에서는 사용을 보여 줍니다.는 <xref:System.Xml.Linq.XDocument.Load%28System.String%29> 를 채우는 메서드는 <xref:System.Xml.Linq.XDocument> 텍스트 파일에서 XML로 개체입니다.  
  
     [!code-vb[VbXMLSamples#43](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_1.vb)]  
  
### <a name="to-load-xml-from-a-string"></a>문자열에서 XML을 로드 하지  
  
-   XML과 같은 리터럴 채우려면는 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument> 개체는 문자열에서 사용할 수 있습니다는 `Parse` 메서드.  
  
     다음 코드 예제에서는 사용을 보여 줍니다.는 <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> 를 채우는 메서드는 <xref:System.Xml.Linq.XDocument> 문자열에서 XML로 개체입니다.  
  
     [!code-vb[VbXMLSamples#47](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_2.vb)]  
  
### <a name="to-load-xml-from-a-stream"></a>스트림에서 XML을 로드 하지  
  
-   XML과 같은 리터럴 채우려면는 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument> 개체 스트림, 사용할 수 있습니다는 `Load` 메서드 또는 <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> 메서드.  
  
 다음 코드 예제에서는 사용을 보여 줍니다.는 <xref:System.Xml.Linq.XNode.ReadFrom%2A> 를 채우는 메서드는 <xref:System.Xml.Linq.XDocument> XML 스트림에서 xml 개체입니다.  
  
 [!code-vb[VbXMLSamples#46](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_3.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>  
 [XML 리터럴](../../../../visual-basic/language-reference/xml-literals/index.md)  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [Visual Basic에서 XML 조작](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
