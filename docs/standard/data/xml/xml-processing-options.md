---
title: "XML 처리 옵션 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 33ced8ee-1745-4e71-8dee-ebe70ec067c7
caps.latest.revision: 5
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 5
---
# XML 처리 옵션
XML 데이터를 처리하는 데 사용할 수 있는 Microsoft 기술 목록은 다음 표를 참조하세요.  
  
## .NET Framework 옵션  
  
|**옵션**|**처리 유형**|**설명**|  
|------------|---------------|------------|  
|[LINQ to XML](../../../../ocs/visual-basic/programming-guide/concepts/linq/linq-to-xml.md) <br /> \(<xref:System.Xml.Linq> 네임스페이스\)|메모리 내|-   .NET Framework LINQ\(Language\-Integrated Query\) 기술을 기반으로 합니다.<br />-   개체, 관계형 데이터 및 XML 데이터에 대해 SQL과 유사한 쿼리 경험을 제공합니다.<br />-   직관적인 문서 작성 및 문서 변환 기능을 제공합니다.<br />-   새 코드를 작성 중인 경우 이 옵션을 사용합니다.|  
|<xref:System.Xml.XmlReader?displayProperty=fullName>|스트림 기반|-   캐시를 사용하지 않고 앞으로만 이동 가능한 빠른 XML 데이터 액세스 방법을 제공합니다.<br />-   <xref:System.Xml.XmlReader.Create%2A?displayProperty=fullName> 메서드를 사용하여 개체를 만들고 <xref:System.Xml.XmlReaderSettings> 클래스를 사용하여 개체에서 활성화할 기능 집합을 지정할 수 있습니다.|  
|<xref:System.Xml.XmlWriter?displayProperty=fullName>|스트림 기반|-   캐시를 사용하지 않고 앞으로만 이동 가능한 빠른 XML 데이터 생성 방법을 제공합니다.<br />-   <xref:System.Xml.XmlWriter.Create%2A?displayProperty=fullName> 메서드를 사용하여 개체를 만들고 <xref:System.Xml.XmlWriterSettings> 클래스를 사용하여 개체에서 활성화할 기능 집합을 지정할 수 있습니다.|  
|<xref:System.Xml.XmlDocument?displayProperty=fullName>|메모리 내|-   [W3C DOM\(문서 개체 모델\) 수준 1 코어](http://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html)\(영문\) 및 [DOM 수준 2 코어](http://www.w3.org/TR/DOM-Level-2-Core/)\(영문\) 권장 사항을 구현합니다.<br />-   익숙한 DOM 모델을 기반으로 한 메서드 및 속성을 사용하여 노드를 생성, 삽입, 제거 및 수정할 수 있습니다.<br />-   W3C DOM을 사용하는 기존 코드를 수정 중인 경우 이 옵션을 사용합니다.|  
|<xref:System.Xml.XPath.XPathNavigator?displayProperty=fullName>|메모리 내|-   커서 모델을 사용하는 몇 가지 편집 옵션 및 탐색 기능을 제공합니다.<br />-   XML 문서는 <xref:System.Xml.XPath.XPathDocument> 또는 <xref:System.Xml.XmlDocument> 개체에 포함될 수 있습니다.<br />-   XML의 읽기 전용 처리에 우수한 성능을 제공합니다.<br />-   XPath 쿼리 또는 XSLT 변환이 포함된 기존 코드를 수정 중인 경우 이 옵션을 사용합니다.|  
|<xref:System.Xml.Xsl.XslCompiledTransform>|메모리 내|-   XSL 변환을 사용하여 XML 데이터를 변환하는 옵션을 제공합니다.<br />-   [XSLT 컴파일러\(xsltc.exe\)](../../../../docs/standard/data/xml/xslt-compiler-xsltc-exe.md)를 사용하여 응용 프로그램에서 미리 컴파일된 변환을 참조할 수 있습니다.|  
  
## Win32 및 COM 기반 옵션  
  
|**옵션**|**설명**|  
|------------|------------|  
|[XmlLite](http://go.microsoft.com/fwlink/?LinkId=93723)\(영문\)|-   빠르고 안전하며 캐시를 사용하지 않고 앞으로만 이동 가능한 XML 파서로서, 고성능의 XML 응용 프로그램을 작성할 수 있도록 도움을 줍니다.<br />-   DLL\(동적 연결 라이브러리\)을 사용할 수 있는 모든 언어에서 사용할 수 있습니다. C\+\+ 사용을 권장합니다.|  
|[MSXML](http://go.microsoft.com/fwlink/?LinkId=93722)\(영문\)|-   Windows 운영 체제에 포함된 XML을 처리할 수 있는 COM 기반 기술입니다.<br />-   XPath 및 XSLT를 지원하는 DOM의 기본적인 구현을 제공합니다.<br />-   SAX2 이벤트 기반 파서가 포함되어 있습니다.|  
  
## 참고 항목  
 [DOM 모델을 사용하여 XML 데이터 처리](../../../../docs/standard/data/xml/process-xml-data-using-the-dom-model.md)   
 [XPath 데이터 모델을 사용하여 XML 데이터 처리](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)   
 [XSLT 컴파일러\(xsltc.exe\)](../../../../docs/standard/data/xml/xslt-compiler-xsltc-exe.md)