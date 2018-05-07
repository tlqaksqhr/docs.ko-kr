---
title: '방법: XML 네임스페이스를 데이터 바인딩에 사용'
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
ms.openlocfilehash: 483b59bb7cea25617c832b96690f742b8b64b3e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a>방법: XML 네임스페이스를 데이터 바인딩에 사용
## <a name="example"></a>예제  
 이 예제에서는 [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] 바인딩 소스에 지정된 네임스페이스를 처리하는 방법을 보여 줍니다.  
  
 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터에 다음 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 네임스페이스 정의가 있는 경우  
  
 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`  
  
 사용할 수는 <xref:System.Windows.Data.XmlNamespaceMapping> 요소를 네임 스페이스를 한 <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>다음 예제와 같이, 합니다. 그런 다음 사용할 수는 <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> 참조 하는 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 네임 스페이스입니다. <xref:System.Windows.Controls.ListBox> 이 예제에 표시 됩니다는 *제목* 및 *dc:date* 각 *항목*합니다.  
  
 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]  
  
 <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> 사용 하는 것과 일치 하지 않아도 지정는 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 원본; 접두사를 변경 하는 경우는 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 소스 매핑은 계속 작동 합니다.  
  
 이 특정 예제는 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터는 웹 서비스에서 제공 되지만 <xref:System.Windows.Data.XmlNamespaceMapping> 인라인 요소 에서도 작동 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 또는 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 포함된 된 파일의 데이터입니다.  
  
## <a name="see-also"></a>참고 항목  
 [XMLDataProvider 및 XPath 쿼리를 사용하여 XML 데이터에 바인딩](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)  
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
