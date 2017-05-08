---
title: "방법: XMLData Provider 및 XPath 쿼리를 사용하여 XML 데이터에 바인딩 | Microsoft Docs"
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
  - "바인딩, XmlDataProvider 쿼리를 사용하여 XML 데이터에"
  - "데이터 바인딩(data binding), XmlDataProvider 쿼리를 사용하여 XML 데이터에 바인딩"
  - "XmlDataProvider, XML 데이터에 바인딩"
ms.assetid: 7dcd018f-16aa-4870-8e47-c1b4ea31e574
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# 방법: XMLData Provider 및 XPath 쿼리를 사용하여 XML 데이터에 바인딩
이 예제에서는 <xref:System.Windows.Data.XmlDataProvider>를 사용하여 [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] 데이터에 바인딩하는 방법을 보여 줍니다.  
  
 <xref:System.Windows.Data.XmlDataProvider>를 사용할 경우 응용 프로그램에서 데이터 바인딩을 통해 액세스할 수 있는 내부 데이터는 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 노드의 트리일 수 있습니다.  즉, <xref:System.Windows.Data.XmlDataProvider>를 사용하면 [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] 노드의 트리를 [바인딩 소스](GTMT)로 손쉽게 사용할 수 있습니다.  
  
## 예제  
 다음 예제에서는 데이터를 <xref:System.Windows.FrameworkElement.Resources%2A> 섹션 내에 직접 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터 아일랜드로 포함합니다.  [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터 아일랜드는 `<x:XData>` 태그에 래핑되어야 하며 항상 단일 루트 노드\(이 예제에서는 *Inventory*\)를 포함하고 있어야 합니다.  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터의 루트 노드에는 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 네임스페이스를 빈 문자열로 설정하는 **xmlns** 특성이 있습니다.  이 특성은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지 내에서 인라인인 데이터 아일랜드에 XPath 쿼리를 적용하는 데 필요합니다.  이와 같이 인라인인 경우 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 및 결과적으로 데이터 아일랜드는 <xref:System.Windows> 네임스페이스를 상속합니다.  이 때문에 XPath 쿼리가 <xref:System.Windows> 네임스페이스로 정규화되어 잘못 사용되는 것을 방지하려면 네임스페이스를 공백으로 설정해야 합니다.  
  
 [!code-xml[XMLDataSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource/CS/Window1.xaml#1)]  
  
 이 예제에서 알 수 있듯이 특성 구문에서 동일한 바인딩 선언을 만들려면 특수 문자를 적절하게 이스케이프해야 합니다.  자세한 내용은 [XML 문자 엔터티 및 XAML](../../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md)을 참조하십시오.  
  
 이 예제를 실행하면 <xref:System.Windows.Controls.ListBox>에서 다음 항목을 표시합니다.  이 항목들은 *Books* 아래에서 *Stock* 값이 "*out*"이거나 *Number* 값이 3 또는 8보다 크거나 같은 모든 요소의 *Title*입니다.  <xref:System.Windows.Data.XmlDataProvider>에서 설정한 <xref:System.Windows.Data.XmlDataProvider.XPath%2A> 값은 *Books* 요소만 노출된다는 것을 나타내므로\(기본적으로 필터 설정\) *CD* 항목은 반환되지 않습니다.  
  
 ![XPath 예제](../../../../docs/framework/wpf/data/media/xpathexample.png "XPathExample")  
  
 이 예제에서는 <xref:System.Windows.DataTemplate>에서 <xref:System.Windows.Controls.TextBlock> 바인딩의 <xref:System.Windows.Data.Binding.XPath%2A>가 "*Title*"로 설정되어 있으므로 책 제목이 표시됩니다.  *ISBN*과 같은 특성 값을 표시하려면 해당 <xref:System.Windows.Data.Binding.XPath%2A> 값을 "`@ISBN`"으로 설정합니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 **XPath** 속성은 XmlNode.SelectNodes 메서드로 처리합니다.  **XPath** 쿼리를 수정하여 다른 결과를 얻을 수 있습니다.  다음은 이전 예제에서 바인딩된 <xref:System.Windows.Controls.ListBox>에 대한 <xref:System.Windows.Data.Binding.XPath%2A> 쿼리의 몇 가지 예입니다.  
  
-   `XPath="Book[1]"`은 첫 번째 책 요소\("XML in Action"\)를 반환합니다.  **XPath** 인덱스는 0이 아닌 1부터 시작합니다.  
  
-   `XPath="Book[@*]"`은 특성이 있는 모든 책 요소를 반환합니다.  
  
-   `XPath="Book[last()-1]"`은 마지막에서 두 번째 책 요소\("Introducing Microsoft .NET"\)를 반환합니다.  
  
-   `XPath="*[position()>3]"`는 처음 세 개를 제외한 모든 책 요소를 반환합니다.  
  
 **XPath** 쿼리를 실행하면 <xref:System.Xml.XmlNode> 또는 XmlNode 목록을 반환합니다.  <xref:System.Xml.XmlNode>는 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 개체이므로 <xref:System.Windows.Data.Binding.Path%2A> 속성을 사용하여 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 속성에 바인딩할 수 있습니다.  앞의 예제를 다시 살펴봅니다.  예제의 나머지는 그대로 두고 <xref:System.Windows.Controls.TextBlock> 바인딩을 다음과 같이 변경하면 <xref:System.Windows.Controls.ListBox>에 반환된 XmlNodes의 이름이 표시됩니다.  이 경우 반환된 모든 노드의 이름은 "*Book*"입니다.  
  
 [!code-xml[XmlDataSourceVariation#XmlNodePath](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSourceVariation/CS/Page1.xaml#xmlnodepath)]  
  
 일부 응용 프로그램에서는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지의 소스 내에 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]을 데이터 아일랜드로 포함하면 컴파일할 때 정확한 데이터 내용이 알려져야 하기 때문에 불편할 수 있습니다.  따라서 다음 예제와 같이 외부 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 파일에서 데이터를 가져올 수도 있습니다.  
  
 [!code-xml[XMLDataSource2#XmlFileExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource2/CS/Window1.xaml#xmlfileexample)]  
  
 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터가 원격 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 파일에 있는 경우 다음과 같이 <xref:System.Windows.Data.XmlDataProvider.Source%2A> 특성에 적절한 [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]을 할당하여 데이터에 대한 액세스를 정의할 수 있습니다.  
  
```  
<XmlDataProvider x:Key="BookData" Source="http://MyUrl" XPath="Books"/>  
```  
  
## 참고 항목  
 <xref:System.Windows.Data.ObjectDataProvider>   
 [XDocument, XElement 또는 LINQ for XML 쿼리 결과에 바인딩](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)   
 [계층적 XML 데이터에 마스터\-세부 패턴 사용](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)   
 [바인딩 소스 개요](../../../../docs/framework/wpf/data/binding-sources-overview.md)   
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)