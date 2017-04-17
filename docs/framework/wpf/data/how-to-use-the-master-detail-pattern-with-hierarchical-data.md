---
title: "방법: 계층적 데이터에 마스터-세부 패턴 사용 | Microsoft Docs"
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
  - "데이터 바인딩(data binding), 마스터-세부 데이터 패러다임"
  - "마스터-세부 데이터 패러다임"
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: 계층적 데이터에 마스터-세부 패턴 사용
이 예제에서는 마스터\-세부 시나리오를 구현하는 방법을 보여 줍니다.  
  
## 예제  
 이 예제에서 `LeagueList`는 `Leagues` 컬렉션입니다.  각 `League`에는 `Name` 및 `Divisions` 컬렉션이 있으며 각 `Division`에는 이름 및 `Teams` 컬렉션이 있습니다.  각 `Team`에는 팀 이름이 있습니다.  
  
 [!code-xml[MasterDetail#HowTo1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xml[MasterDetail#HowTo2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 다음은 예제의 스크린 샷입니다.  `Divisions` <xref:System.Windows.Controls.ListBox>는 `Leagues` <xref:System.Windows.Controls.ListBox>의 선택 항목을 자동으로 추적하고 해당 데이터를 표시합니다.  `Teams` <xref:System.Windows.Controls.ListBox>는 다른 두 <xref:System.Windows.Controls.ListBox> 컨트롤의 선택 항목을 추적합니다.  
  
 ![마스터&#45;세부 예제](../../../../docs/framework/wpf/data/media/databindingmasterdetailsample.png "DataBindingMasterDetailSample")  
  
 이 예제에서 주목해야 할 두 가지 내용은 다음과 같습니다.  
  
1.  세 <xref:System.Windows.Controls.ListBox> 컨트롤은 같은 소스에 바인딩됩니다.  바인딩의 <xref:System.Windows.Data.Binding.Path%2A> 속성을 설정하여 <xref:System.Windows.Controls.ListBox>에 표시할 데이터의 수준을 지정할 수 있습니다.  
  
2.  추적하는 선택 항목의 <xref:System.Windows.Controls.ListBox> 컨트롤에서 <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> 속성을 `true`로 설정해야 합니다.  이 속성을 설정하면 선택한 항목이 항상 <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>으로 설정됩니다.  <xref:System.Windows.Controls.ListBox>가 <xref:System.Windows.Data.CollectionViewSource>에서 데이터를 가져오는 경우에는 선택 항목과 통화가 자동으로 동기화됩니다.  
  
 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터를 사용할 경우에는 방법이 약간 다릅니다.  예제를 보려면 [계층적 XML 데이터에 마스터\-세부 패턴 사용](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.HierarchicalDataTemplate>   
 [선택에 따라 수집 및 표시 정보에 바인딩](../../../../docs/framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md)   
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [데이터 템플릿 개요](../../../../docs/framework/wpf/data/data-templating-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)