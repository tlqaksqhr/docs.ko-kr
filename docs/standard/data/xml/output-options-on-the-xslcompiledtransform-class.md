---
title: "XslCompiledTransform 클래스의 출력 옵션 | Microsoft Docs"
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
ms.assetid: 91ce8cba-386c-411e-bb38-0891a0393c0a
caps.latest.revision: 2
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 2
---
# XslCompiledTransform 클래스의 출력 옵션
이 항목에서는 사용할 수 있는 XSLT 출력 옵션에 대해 설명합니다.  스타일시트나 <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> 메서드에서 출력 옵션을 지정할 수 있습니다.  
  
## xsl:output 요소  
 `xsl:output` 요소는 출력 옵션을 지정합니다.  <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> 메서드로 지정한 출력 형식에 의해 `xsl:output` 옵션의 동작이 결정됩니다.  
  
 다음 표에서는 출력 형식이 스트림 또는 <xref:System.IO.TextWriter>인 경우 `xsl:output` 요소에서 사용할 수 있는 각 특성의 동작에 대해 설명합니다.  
  
|특성 이름|동작|  
|-----------|--------|  
|메서드|지원됩니다.|  
|버전|무시됩니다.  버전은 항상 XML의 경우 1.0이고 HTML의 경우 4.0입니다.|  
|encoding|<xref:System.IO.TextWriter>로 출력하는 경우 무시됩니다.  <xref:System.IO.TextWriter.Encoding%2A?displayProperty=fullName> 속성이 대신 사용됩니다.|  
|omit\-xml\-declaration|지원됩니다.|  
|독립 실행형|지원됩니다.|  
|doctype\-public|지원됩니다.|  
|doctype\-system|지원됩니다.|  
|cdata\-section\-elements|지원됩니다.|  
|indent|지원됩니다.|  
|media\-type|지원됩니다.|  
  
#### XmlWriter로 출력 보내기  
 스타일시트에서 `xsl:output` 요소를 사용하며 출력 형식이 <xref:System.Xml.XmlWriter> 개체인 경우 <xref:System.Xml.XmlWriter> 개체를 만들 때 <xref:System.Xml.Xsl.XslCompiledTransform.OutputSettings%2A?displayProperty=fullName> 속성을 사용해야 합니다.  <xref:System.Xml.Xsl.XslCompiledTransform.OutputSettings%2A?displayProperty=fullName> 속성은 컴파일된 스타일시트의 `xsl:output` 요소에서 파생된 정보가 포함된 <xref:System.Xml.XmlWriterSettings> 개체를 반환합니다.  이 <xref:System.Xml.XmlWriterSettings> 개체를 <xref:System.Xml.XmlWriter.Create%2A?displayProperty=fullName> 메서드에 전달하여 올바른 설정으로 <xref:System.Xml.XmlWriter> 개체를 만들 수 있습니다.  
  
## 출력 형식  
 다음 목록에서는 <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> 명령에서 사용할 수 있는 출력 형식에 대해 설명합니다.  
  
#### XmlWriter  
 <xref:System.Xml.XmlWriter> 클래스는 XML 스키마 또는 파일을 씁니다.  <xref:System.Xml.XmlWriterSettings> 클래스를 사용하면 출력 옵션을 비롯하여 <xref:System.Xml.XmlWriter> 개체에서 지원할 기능을 지정할 수 있습니다.  <xref:System.Xml.XmlWriter> 클래스는 <xref:System.Xml> 프레임워크의 필수 부분입니다.  이 출력 형식을 사용하여 출력 결과를 다른 XML 프로세스에 보낼 수 있습니다.  
  
#### 문자열  
 이 출력 형식을 사용하여 출력 파일의 URI를 지정할 수 있습니다.  
  
#### 스트림  
 스트림은 파일, 입력\/출력 장치, 프로세스 간 통신 파이프 또는 TCP\/IP 소켓과 같은 바이트 시퀀스를 추상적으로 나타낸 것입니다.  <xref:System.IO.Stream> 클래스와 해당 파생 클래스는 이러한 여러 형식의 입력 및 출력의 일반 뷰를 제공하는데 이때 프로그래머는 운영 체제 및 기본 장치의 세부 정보에서 격리됩니다.  
  
 이 출력 형식을 사용하여 데이터를 <xref:System.IO.FileStream>, <xref:System.IO.MemoryStream> 또는 출력 스트림\(`Response.OutputStream`\)으로 보낼 수 있습니다.  
  
#### TextWriter  
 <xref:System.IO.TextWriter>는 연속 문자를 씁니다.  <xref:System.IO.StringWriter> 및 <xref:System.IO.StreamWriter> 클래스에서 구현되며 이 클래스는 각각 문자열과 스트림에 문자를 씁니다.  문자열로 출력하려면 이 출력 형식을 사용합니다.  
  
## 참고  
  
-   빈 태그를 쓰는 경우 `<myElement />`와 같이 요소 이름의 마지막 문자와 백슬래시 사이에 공백이 쓰여집니다.  그러면 이전 브라우저에 생성된 HTML 페이지가 올바르게 표시됩니다.  
  
## 참고 항목  
 [XSLT 변환](../../../../docs/standard/data/xml/xslt-transformations.md)