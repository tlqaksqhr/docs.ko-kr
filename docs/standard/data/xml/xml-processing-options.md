---
title: "XML 처리 옵션"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 33ced8ee-1745-4e71-8dee-ebe70ec067c7
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 18f8f9c76a1842517340eaa3f74b4778f869403e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="xml-processing-options"></a>XML 처리 옵션
XML 데이터를 처리하는 데 사용할 수 있는 Microsoft 기술 목록은 다음 표를 참조하세요.  
  
## <a name="net-framework-options"></a>.NET Framework 옵션  
  
|**옵션**|**처리 유형**|**설명**|  
|----------------|-------------------------|---------------------|  
|[LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13) <br />(<xref:System.Xml.Linq> 네임스페이스)|메모리 내|-LINQ (language-integrated Query) 기술을 기반으로 합니다.<br />-개체, 관계형 데이터 및 XML 데이터에 대 한 SQL과 유사한 쿼리 환경을 제공 합니다.<br />-직관적인 문서 작성 및 변환 기능 제공합니다.<br />-새 코드를 작성 하는 경우이 옵션을 사용 합니다.|  
|<xref:System.Xml.XmlReader?displayProperty=nameWithType>|스트림 기반|-XML 데이터에 액세스 하는 빠르고 캐시 되지 않은, 앞 으로만 이동 가능한 방법을 제공합니다.<br />사용 하 여 개체를 만들 수-는 <xref:System.Xml.XmlReader.Create%2A?displayProperty=nameWithType> 메서드를 사용 하 여 개체에서 활성화할 기능 집합을 지정 하 고는 <xref:System.Xml.XmlReaderSettings> 클래스입니다.|  
|<xref:System.Xml.XmlWriter?displayProperty=nameWithType>|스트림 기반|-XML 데이터를 생성 하는 빠르고 캐시 되지 않은, 앞 으로만 이동 가능한 방법을 제공 합니다.<br />사용 하 여 개체를 만들 수-는 <xref:System.Xml.XmlWriter.Create%2A?displayProperty=nameWithType> 메서드를 사용 하 여 개체에서 활성화할 기능 집합을 지정 하 고는 <xref:System.Xml.XmlWriterSettings> 클래스입니다.|  
|<xref:System.Xml.XmlDocument?displayProperty=nameWithType>|메모리 내|-구현에서 [W3C 문서 개체 모델 (DOM) Level 1 Core](http://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html) 및 [DOM Level 2 Core](http://www.w3.org/TR/DOM-Level-2-Core/) 권장 사항입니다.<br />-있습니다 수 만들, 삽입, 제거 및 익숙한 DOM 모델을 기반으로 하는 속성과 메서드를 사용 하 여 노드를 수정 합니다.<br />-W3C DOM를 활용 하는 기존 코드를 수정 하는 경우이 옵션 사용|  
|<xref:System.Xml.XPath.XPathNavigator?displayProperty=nameWithType>|메모리 내|-몇 가지 편집 옵션 및 커서 모델을 사용 하 여 탐색 기능을 제공 합니다.<br />XML 문서에 포함 될 수는 <xref:System.Xml.XPath.XPathDocument> 또는 <xref:System.Xml.XmlDocument> 개체입니다.<br />-XML의 읽기 전용 처리에 우수한 성능을 제공합니다.<br />-XPath 쿼리 또는 XSLT 변형이 포함 된 기존 코드를 수정 하는 경우이 옵션을 사용 합니다.|  
|<xref:System.Xml.Xsl.XslCompiledTransform>|메모리 내|-XSL 변형을 사용 하 여 XML 데이터를 변환에 대 한 옵션을 제공 합니다.<br />- [XSLT 컴파일러 (xsltc.exe)](../../../../docs/standard/data/xml/xslt-compiler-xsltc-exe.md) 응용 프로그램에서 변환으로 미리 컴파일한 참조할 수 있습니다.|  
  
## <a name="win32-and-com-based-options"></a>Win32 및 COM 기반 옵션  
  
|**옵션**|**설명**|  
|----------------|---------------------|  
|[XmlLite](http://go.microsoft.com/fwlink/?LinkId=93723)|-빠른, 보안, 캐시, 앞 으로만 이동 가능한 XML 파서를 사용 하면 고성능 XML 앱 빌드합니다.<br />-동적 연결 라이브러리 (Dll);를 사용할 수 있는 모든 언어에서 작동 합니다. c + +를 사용 하는 것이 좋습니다.|  
|[MSXML](http://go.microsoft.com/fwlink/?LinkId=93722)|-Windows 운영 체제에 포함 된 XML 처리를 위한 COM 기반 기술입니다.<br />-XPath 및 XSLT를 지 원하는 DOM의 기본적인 구현을 제공 합니다.<br />-SAX2 이벤트 기반 파서가 포함 되어 있습니다.|  
  
## <a name="see-also"></a>참고 항목  
 [DOM 모델을 사용 하 여 XML 데이터 처리](../../../../docs/standard/data/xml/process-xml-data-using-the-dom-model.md)  
 [XPath 데이터 모델을 사용하여 XML 데이터 처리](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [XSLT 컴파일러 (xsltc.exe)](../../../../docs/standard/data/xml/xslt-compiler-xsltc-exe.md)
