---
title: "방법: XAML의 바인딩에 사용할 수 있는 데이터 만들기 | Microsoft Docs"
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
  - "데이터 바인딩, 데이터를 사용 가능하게 만들기"
  - "데이터 바인딩(data binding), 데이터를 바인딩 가능하게 만들기"
ms.assetid: 7103c2e8-0e31-4a13-bf12-ca382221a8d5
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: XAML의 바인딩에 사용할 수 있는 데이터 만들기
이 항목에서는 응용 프로그램의 필요에 따라 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]의 바인딩에 사용할 수 있게 데이터를 만드는 다양한 방법을 설명합니다.  
  
## 예제  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 바인딩하고자 하는 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 개체가 있는 경우 개체를 바인딩에서 사용할 수 있게 만드는 방법은 해당 개체를 리소스로 정의하여 `x:Key`를 부여하는 것입니다.  다음 예제에는 `PersonName`이라는 문자열 속성과 함께 `Person` 개체가 있습니다.  `Person` 개체는 `SDKSample`이라는 네임스페이스에 정의되어 있습니다.  
  
 [!code-xml[SimpleBinding#Instantiation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#instantiation)]  
[!code-xml[SimpleBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#2)]  
  
 그리고 나서 다음 예제와 같이 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 개체에 바인딩할 수 있습니다.  
  
 [!code-xml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 또는 다음 예제와 같이 <xref:System.Windows.Data.ObjectDataProvider> 클래스를 사용할 수 있습니다.  
  
 [!code-xml[SimpleBinding#ODPCP](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml#odpcp)]  
  
 같은 방법으로 바인딩을 정의합니다.  
  
 [!code-xml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 이 특정 예제에서 결과는 같습니다. 즉, 텍스트 콘텐츠가 `Joe`인 <xref:System.Windows.Controls.TextBlock>을 갖게 됩니다.  그러나 <xref:System.Windows.Data.ObjectDataProvider> 클래스는 메서드의 결과에 바인딩하는 기능과 같은 기능을 제공합니다.  이와 같은 기능이 필요한 경우 <xref:System.Windows.Data.ObjectDataProvider> 클래스 사용을 선택할 수 있습니다.  
  
 하지만 이미 만들어진 개체에 바인딩하는 경우 다음 예제와 같이 코드에서 `DataContext`를 설정해야 합니다.  
  
 [!code-csharp[ADODataSet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 <xref:System.Windows.Data.XmlDataProvider> 클래스를 사용하여 바인딩할 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터에 액세스하려면 [XMLData Provider 및 XPath 쿼리를 사용하여 XML 데이터에 바인딩](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)을 참조하십시오.  <xref:System.Windows.Data.ObjectDataProvider> 클래스를 사용하여 바인딩할 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터에 액세스하려면 [XDocument, XElement 또는 LINQ for XML 쿼리 결과에 바인딩](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)을 참조하십시오.  
  
 바인딩할 데이터를 지정하는 다양한 방법에 대한 자세한 내용은 [바인딩 소스 지정](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md)을 참조하십시오.  바인딩할 수 있는 데이터 형식이나 바인딩을 위해 사용자 고유의 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 개체를 구현하는 방법에 대한 자세한 내용은 [바인딩 소스 개요](../../../../docs/framework/wpf/data/binding-sources-overview.md)를 참조하십시오.  
  
## 참고 항목  
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)