---
title: "방법: XslTransform 코드 마이그레이션 | Microsoft Docs"
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
ms.assetid: 910beb2f-cfb3-4e8e-9936-f7e0c5f4064a
caps.latest.revision: 2
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 2
---
# 방법: XslTransform 코드 마이그레이션
새 XSLT 클래스는 기존 클래스와 매우 유사하게 디자인되었습니다.  <xref:System.Xml.Xsl.XslCompiledTransform> 클래스는 <xref:System.Xml.Xsl.XslTransform> 클래스를 대체합니다.  <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> 메서드를 사용하여 스타일시트를 컴파일할 수 있습니다.  <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> 메서드를 사용하여 변환을 실행할 수 있습니다.  다음 프로시저에서는 일반 XSLT 작업을 보여 주고 <xref:System.Xml.Xsl.XslTransform> 클래스를 사용한 코드와 <xref:System.Xml.Xsl.XslCompiledTransform> 클래스를 사용한 코드를 비교합니다.  
  
### 파일 및 출력을 URI로 변환하려면  
  
-   <xref:System.Xml.Xsl.XslTransform> 클래스를 사용하는 코드입니다.  
  
     [!code-csharp[XML_Migration#9](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#9)]
     [!code-vb[XML_Migration#9](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#9)]  
  
-   <xref:System.Xml.Xsl.XslCompiledTransform> 클래스를 사용하는 코드입니다.  
  
     [!code-csharp[XML_Migration#10](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#10)]
     [!code-vb[XML_Migration#10](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#10)]  
  
### 스타일시트를 컴파일하고 기본 자격 증명으로 확인기를 사용하려면  
  
-   <xref:System.Xml.Xsl.XslTransform> 클래스를 사용하는 코드입니다.  
  
     [!code-csharp[XML_Migration#11](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#11)]
     [!code-vb[XML_Migration#11](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#11)]  
  
-   <xref:System.Xml.Xsl.XslCompiledTransform> 클래스를 사용하는 코드입니다.  
  
     [!code-csharp[XML_Migration#12](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#12)]
     [!code-vb[XML_Migration#12](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#12)]  
  
### XSLT 매개 변수를 사용하려면  
  
-   <xref:System.Xml.Xsl.XslTransform> 클래스를 사용하는 코드입니다.  
  
     [!code-csharp[XML_Migration#13](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#13)]
     [!code-vb[XML_Migration#13](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#13)]  
  
-   <xref:System.Xml.Xsl.XslCompiledTransform> 클래스를 사용하는 코드입니다.  
  
     [!code-csharp[XML_Migration#14](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#14)]
     [!code-vb[XML_Migration#14](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#14)]  
  
### XSLT 스크립트를 사용하려면  
  
-   <xref:System.Xml.Xsl.XslTransform> 클래스를 사용하는 코드입니다.  
  
     [!code-csharp[XML_Migration#15](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#15)]
     [!code-vb[XML_Migration#15](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#15)]  
  
-   <xref:System.Xml.Xsl.XslCompiledTransform> 클래스를 사용하는 코드입니다.  
  
     [!code-csharp[XML_Migration#16](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#16)]
     [!code-vb[XML_Migration#16](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#16)]  
  
### 결과를 DOM 개체에 로드하려면  
  
-   <xref:System.Xml.Xsl.XslTransform> 클래스를 사용하는 코드입니다.  
  
     [!code-csharp[XML_Migration#19](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#19)]
     [!code-vb[XML_Migration#19](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#19)]  
  
-   <xref:System.Xml.Xsl.XslCompiledTransform> 클래스를 사용하는 코드입니다.  
  
    > [!NOTE]
    >  <xref:System.Xml.Xsl.XslCompiledTransform> 클래스에는 XSLT 변환 결과를 <xref:System.Xml.XmlReader> 개체로 반환하는 메서드가 없습니다.  그러나 XML 파일로 출력하고 이 XML 파일을 다른 개체에 로드할 수 있습니다.  
  
     [!code-csharp[XML_Migration#20](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#20)]
     [!code-vb[XML_Migration#20](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#20)]  
  
### 결과를 다른 데이터 저장소로 스트리밍하려면  
  
-   <xref:System.Xml.Xsl.XslTransform> 클래스를 사용하는 코드입니다.  
  
     [!code-csharp[XML_Migration#17](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#17)]
     [!code-vb[XML_Migration#17](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#17)]  
  
-   <xref:System.Xml.Xsl.XslCompiledTransform> 클래스를 사용하는 코드입니다.  
  
     [!code-csharp[XML_Migration#18](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#18)]
     [!code-vb[XML_Migration#18](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#18)]  
  
## 참고 항목  
 [XslTransform 클래스에서 마이그레이션](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)   
 [XslCompiledTransform 클래스 사용](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)