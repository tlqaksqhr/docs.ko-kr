---
title: "방법: XML 네임스페이스를 데이터 바인딩에 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "데이터 바인딩(data binding), XML 네임스페이스"
  - "네임스페이스, XML"
  - "XML, 네임스페이스"
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: XML 네임스페이스를 데이터 바인딩에 사용
## 예제  
 이 예제에서는 [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] [바인딩 소스](GTMT)에 지정된 네임스페이스를 처리하는 방법을 보여 줍니다.  
  
 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터에 다음 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 네임스페이스 정의가 있는 경우  
  
 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`  
  
 다음 예제와 같이 <xref:System.Windows.Data.XmlNamespaceMapping> 요소를 사용하여 네임스페이스를 <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>에 매핑할 수 있습니다.  그런 다음 <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>를 사용하여 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 네임스페이스를 참조할 수 있습니다.  이 예제의 <xref:System.Windows.Controls.ListBox>는 각 *item*의 *title*과 *dc:date*를 표시합니다.  
  
 <!-- TODO: review snippet reference [!code-xml[XmlnsBind#XmlNamespaceMapping](../../../../samples/snippets/xaml/VS_Snippets_Wpf/XmlnsBind/XAML/Window1.xaml#xmlnamespacemapping)]  -->
 <!-- TODO: review snippet reference [!code-xml[XmlnsBind#XmlNamespaceMapping](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBind/CS/Window1.xaml#xmlnamespacemapping)]  -->  
  
 지정하는 <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>가 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 소스에 사용되는 접두사와 일치할 필요는 없습니다. [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 소스에서 접두사가 변경되더라도 매핑은 계속 작동합니다.  
  
 이 예제에서 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터는 웹 서비스에서 가져온 것이지만 <xref:System.Windows.Data.XmlNamespaceMapping> 요소는 포함된 파일의 인라인 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 또는 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터의 경우에도 작동합니다.  
  
## 참고 항목  
 [XMLData Provider 및 XPath 쿼리를 사용하여 XML 데이터에 바인딩](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)   
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)