---
title: "방법: XMLData Provider 및 XPath 쿼리를 사용하여 XML 데이터에 바인딩"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XmlDataProvider [WPF], binding to XML data
- data binding [WPF], binding to XML data using XmlDataProvider queries
- binding [WPF], to XML data using XmlDataProvider queries
ms.assetid: 7dcd018f-16aa-4870-8e47-c1b4ea31e574
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 92037be2280eaa248951ff9bad82b7a1581a4fd9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries"></a>방법: XMLData Provider 및 XPath 쿼리를 사용하여 XML 데이터에 바인딩
에 바인딩하는 방법을 보여 주는이 예제 [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] 사용 하 여 데이터는 <xref:System.Windows.Data.XmlDataProvider>합니다.  
  
 와 <xref:System.Windows.Data.XmlDataProvider>, 내부 응용 프로그램에서 데이터 바인딩을 통해 액세스할 수 있는 데이터의 모든 트리 수 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 노드. 즉, 한 <xref:System.Windows.Data.XmlDataProvider> 의 모든 트리를 사용 하는 편리한 방법을 제공 [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] 바인딩 소스로 노드.  
  
## <a name="example"></a>예  
 다음 예제에서는 데이터 변수로 직접 포함 되어는 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] *데이터 아일랜드* 내에서 <xref:System.Windows.FrameworkElement.Resources%2A> 섹션. [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터 고립 영역은 `<x:XData>` 태그로 래핑되어야 하며, 항상 단일 루트 노드가 있어야 합니다. 이 예에서는 *인벤토리*입니다.  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터의 루트 노드에는 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 네임스페이스를 빈 문자열로 설정하는 **xmlns** 특성이 있습니다. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지에 인라인인 데이터 고립 영역에 XPath 쿼리를 적용하기 위한 요구 사항입니다. 인라인 여기서는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], 데이터 아일랜드 상속 따라서 및는 <xref:System.Windows> 네임 스페이스입니다. 네임 스페이스를으로 한정 되 고에서 XPath 쿼리를 유지 하려면 비워 설정 해야이 인해는 <xref:System.Windows> 네임 스페이스에는 쿼리 되어 잘못 사용 됩니다.  
  
 [!code-xaml[XMLDataSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource/CS/Window1.xaml#1)]  
  
 이 예에 표시된 대로 특성 구문에서 동일한 바인딩 선언을 만들기 위해 특수 문자를 적절하게 이스케이프 처리해야 합니다. 자세한 내용은 [XML 문자 엔터티 및 XAML](../../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md)을 참조하세요.  
  
 <xref:System.Windows.Controls.ListBox> 이 예제를 실행 하는 경우 다음 항목이 표시 됩니다. *재고* 값이 “*out*”이거나 *숫자* 값이 3이상 또는 8과 동일한 *책* 아래에 있는 모든 요소의 *제목*입니다. 다음에 유의 없는 *CD* 항목은 반환는 <xref:System.Windows.Data.XmlDataProvider.XPath%2A> 값이 설정에는 <xref:System.Windows.Data.XmlDataProvider> 됨을 나타냅니다는 *설명서* (기본적으로 필터 설정) 요소에 노출 되어야 합니다.  
  
 ![XPath 예제](../../../../docs/framework/wpf/data/media/xpathexample.PNG "XPathExample")  
  
 이 예제에서는 때문에 책 제목이 표시 됩니다는 <xref:System.Windows.Data.Binding.XPath%2A> 의 <xref:System.Windows.Controls.TextBlock> 에서 바인딩는 <xref:System.Windows.DataTemplate> 로 설정 된 "*제목*"입니다. 와 같은 특성의 값을 표시 하려는 경우는 *ISBN*는 설정한 <xref:System.Windows.Data.Binding.XPath%2A> 값을 "`@ISBN`"입니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 **XPath** 속성은 XmlNode.SelectNodes 메서드를 통해 처리됩니다. **XPath** 쿼리를 수정하여 다른 결과를 얻을 수 있습니다. 다음은 몇 가지 예는 <xref:System.Windows.Data.Binding.XPath%2A> 의 경계에서 쿼리를 <xref:System.Windows.Controls.ListBox> 이전 예제에서:  
  
-   `XPath="Book[1]"`은 첫 번째 책 요소를 반환합니다(“작동 중인 XML”). **XPath** 색인은 0이 아니라 1을 기반으로 합니다.  
  
-   `XPath="Book[@*]"`에서는 모든 특성이 있는 모든 책 요소를 반환합니다.  
  
-   `XPath="Book[last()-1]"`은 끝에서 두 번째인 책 요소를 반환합니다(“Microsoft .NET 소개”).  
  
-   `XPath="*[position()>3]"`에서는 처음 3개를 제외한 모든 책 요소를 반환합니다.  
  
 실행 하는 경우는 **XPath** 쿼리 반환는 <xref:System.Xml.XmlNode> XmlNodes 목록이 나 합니다. <xref:System.Xml.XmlNode>이 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 개체를 사용할 수 있습니다는 <xref:System.Windows.Data.Binding.Path%2A> 바인딩할 속성은 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 속성입니다. 이전 예를 다시 살펴보겠습니다. 이 예제에서는 나머지 그대로 변경 하면는 <xref:System.Windows.Controls.TextBlock> 바인딩을 다음과 같이 나타납니다에 반환된 된 XmlNodes 이름을 <xref:System.Windows.Controls.ListBox>합니다. 이 경우 반환된 모든 노드의 이름은 "*Book*"입니다.  
  
 [!code-xaml[XmlDataSourceVariation#XmlNodePath](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSourceVariation/CS/Page1.xaml#xmlnodepath)]  
  
 컴파일 시 데이터의 정확한 콘텐츠를 알아야 하므로, 일부 응용 프로그램에서 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]를 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지 소스의 데이터 고립 영역으로 포함하면 불편할 수 있습니다. 따라서 다음 예에서와 같이 외부 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 파일에서 데이터 가져오기도 지원됩니다.  
  
 [!code-xaml[XMLDataSource2#XmlFileExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource2/CS/Window1.xaml#xmlfileexample)]  
  
 경우는 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 멤버 데이터에 원격 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 파일인 있습니다 액세스를 정의할 수는 데이터에 적절 한 할당 하 여 [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] 에 <xref:System.Windows.Data.XmlDataProvider.Source%2A> 특성을 다음과 같이:  
  
```xml  
<XmlDataProvider x:Key="BookData" Source="http://MyUrl" XPath="Books"/>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Data.ObjectDataProvider>  
 [XDocument, XElement 또는 LINQ for XML 쿼리 결과에 바인딩](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)  
 [계층적 XML 데이터에 마스터-세부 패턴 사용](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)  
 [바인딩 소스 개요](../../../../docs/framework/wpf/data/binding-sources-overview.md)  
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
