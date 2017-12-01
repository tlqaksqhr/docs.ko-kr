---
title: "XslTransform에 대한 XmlDataDocument 입력"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a0b536b6-cdb3-4a44-86c2-3b2ebc7bd4c9
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 813c240ca0115015158988e1226d25890cde6939
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="xmldatadocument-input-to-xsltransform"></a>XslTransform에 대한 XmlDataDocument 입력
> [!NOTE]
>  <xref:System.Xml.Xsl.XslTransform> 클래스는 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]에서 사용되지 않습니다. <xref:System.Xml.Xsl.XslCompiledTransform> 클래스를 사용하여 XSLT(Extensible Stylesheet Language for Transformations) 변환을 수행할 수 있습니다. 참조 [XslCompiledTransform 클래스를 사용 하 여](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) 및 [마이그레이션 XslTransform 클래스에서](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) 자세한 정보에 대 한 합니다.  
  
 Microsoft [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]에서는 XML 문서의 데이터에 대한 액세스를 제공하는 XML DOM(문서 개체 모델)과 XML 문서를 읽고, 쓰고, 탐색하는 추가 클래스를 구현합니다. <xref:System.Xml.XmlDataDocument> 네임스페이스에 있는 <xref:System.Xml>는 <xref:System.Data.DataSet>의 관계형 데이터를 동기화하는 기능을 사용하여 데이터에 대한 관계형 액세스를 제공합니다. <xref:System.Data.DataSet>의 관계형 표현을 통해 구조적 XML을 보면서 조작하거나 <xref:System.Xml.XmlDataDocument>의 DOM 표현을 통해 반구조적 XML을 조작할 수 있습니다. 따라서 <xref:System.Xml.XmlDataDocument>는 XML과 관계형 데이터의 경계를 초월합니다.  
  
 데이터를 관계형 구조에 저장하고 XSLT 변환의 입력으로 사용하려면 관계형 데이터를 <xref:System.Data.DataSet>에 로드하고 <xref:System.Xml.XmlDataDocument>와 연결하면 됩니다. <xref:System.Xml.XPath.XPathNavigator>에 대한 입력인 <xref:System.Xml.Xsl.XslTransform>는 <xref:System.Xml.XmlDataDocument> 인터페이스를 통해 <xref:System.Xml.XPath.IXPathNavigable>에 구현됩니다. 관계형 데이터를 가져와 <xref:System.Data.DataSet>에 로드하고 <xref:System.Xml.XmlDataDocument> 내에서 동기화를 사용하면 관계형 데이터에 XSLT 변환을 수행할 수 있습니다.  
  
 관계형 데이터에 변환을 적용에 대 한 자세한 내용은 참조 하십시오. [DataSet에는 XSLT 변환 적용](../../../../docs/framework/data/adonet/dataset-datatable-dataview/applying-an-xslt-transform-to-a-dataset.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Xml.XmlDataDocument>  
 [데이터 집합 및 XmlDataDocument 동기화](../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md)  
 [XslTransform 클래스와 함께 XSLT 변환](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)  
 [XslTransform 클래스의 XSLT 프로세서 구현](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)  
 [변형의 XPathNavigator](../../../../docs/standard/data/xml/xpathnavigator-in-transformations.md)  
 [변형의 XPathNodeIterator](../../../../docs/standard/data/xml/xpathnodeiterator-in-transformations.md)  
 [XslTransform에 대 한 XPathDocument 입력](../../../../docs/standard/data/xml/xpathdocument-input-to-xsltransform.md)  
 [XslTransform에 대 한 XmlDocument 입력](../../../../docs/standard/data/xml/xmldocument-input-to-xsltransform.md)
