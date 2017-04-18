---
title: "방법: ListView에 있는 열의 가로 맞춤 변경 | Microsoft Docs"
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
  - "ListView 컨트롤, 가로 맞춤"
ms.assetid: b9573e44-9dad-4d14-939c-7859ca372758
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# 방법: ListView에 있는 열의 가로 맞춤 변경
기본적으로 <xref:System.Windows.Controls.ListViewItem>의 각 열 콘텐츠는 왼쪽으로 정렬됩니다.  이러한 각 열에 대한 맞춤은 <xref:System.Windows.DataTemplate>을 제공하고 <xref:System.Windows.DataTemplate> 안에서 요소에 대한 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 속성을 설정하여 변경할 수 있습니다.  이 항목에서는 <xref:System.Windows.Controls.ListView>의 콘텐츠가 기본적으로 정렬되는 방식과 <xref:System.Windows.Controls.ListView>에서 특정 열의 맞춤을 변경하는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 `Title` 및 `ISBN` 열의 데이터가 왼쪽으로 정렬됩니다.  
  
 [!code-xml[ListViewHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xml[ListViewHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 `ISBN` 열의 맞춤을 변경하려면 각 <xref:System.Windows.Controls.ListViewItem>의 요소가 각 열의 전체 너비에 맞게 확장되거나 배치될 수 있도록 각 <xref:System.Windows.Controls.ListViewItem>의 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> 속성을 <xref:System.Windows.HorizontalAlignment>로 지정해야 합니다.  <xref:System.Windows.Controls.ListView>는 데이터 소스에 바인딩되기 때문에 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>를 설정하는 스타일도 만들어야 합니다.  그런 다음 <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> 속성을 사용하는 대신 <xref:System.Windows.DataTemplate>을 사용하여 콘텐츠를 표시해야 합니다.  각 템플릿의 `ISBN`을 표시하려면 <xref:System.Windows.DataTemplate>에 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 속성이 <xref:System.Windows.HorizontalAlignment>로 설정된 <xref:System.Windows.Controls.TextBlock>만 포함하면 됩니다.  
  
 다음 예제에서는 `ISBN` 열을 오른쪽 맞춤으로 설정하는 데 필요한 스타일과 <xref:System.Windows.DataTemplate>을 정의하고 <xref:System.Windows.DataTemplate>을 참조하도록 <xref:System.Windows.Controls.GridViewColumn>을 변경합니다.  
  
 [!code-xml[ListViewHowTos#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#3)]  
[!code-xml[ListViewHowTos#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#4)]  
  
## 참고 항목  
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [데이터 템플릿 개요](../../../../docs/framework/wpf/data/data-templating-overview.md)   
 [XMLData Provider 및 XPath 쿼리를 사용하여 XML 데이터에 바인딩](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)   
 [ListView 개요](../../../../docs/framework/wpf/controls/listview-overview.md)