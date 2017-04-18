---
title: "방법: ObservableCollection 만들기 및 바인딩 | Microsoft Docs"
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
  - "클래스, ObservableCollection"
  - "데이터 바인딩(data binding), ObservableCollection 클래스"
  - "알림"
ms.assetid: 6cf7e275-df76-41c6-a611-53b889b8fd5a
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: ObservableCollection 만들기 및 바인딩
이 예제에서는 항목이 추가되거나 제거될 때 알림을 제공하는 컬렉션 클래스인 <xref:System.Collections.ObjectModel.ObservableCollection%601> 클래스에서 파생된 컬렉션을 만들고 이 컬렉션에 바인딩하는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 `NameList` 컬렉션의 구현을 보여 줍니다.  
  
 [!code-csharp[MultiBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[MultiBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MultiBinding/VisualBasic/NameList.vb#1)]  
  
 [XAML의 바인딩에 사용할 수 있는 데이터 만들기](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md)에 설명되어 있는 것처럼 다른 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 개체의 경우와 마찬가지 방식으로 해당 컬렉션을 바인딩에 사용할 수 있게 만들 수 있습니다.  예를 들어 다음과 같이 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 컬렉션을 인스턴스화하고 컬렉션을 리소스로 지정할 수 있습니다.  
  
 [!code-xml[MultiBinding#OCHowTo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#ochowto)]  
[!code-xml[MultiBinding#Resources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources2)]  
  
 그런 다음 컬렉션에 바인딩할 수 있습니다.  
  
 [!code-xml[MultiBinding#MultiBindingListBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#multibindinglistbox)]  
  
 `NameItemTemplate`의 정의는 여기에 나와 있지 않습니다.  
  
> [!NOTE]
>  컬렉션의 개체는 [바인딩 소스 개요](../../../../docs/framework/wpf/data/binding-sources-overview.md)에 설명된 요구 사항에 맞아야 합니다.  특히 <xref:System.Windows.Data.BindingMode> 또는 <xref:System.Windows.Data.BindingMode>를 사용하는 경우\(예: 소스 속성이 동적으로 변경될 때 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 업데이트\) <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스와 같은 적절한 속성 변경 알림 메커니즘을 구현해야 합니다.  
  
 자세한 내용은 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)에서 "컬렉션에 바인딩" 단원을 참조하십시오.  
  
## 참고 항목  
 [뷰의 데이터 정렬](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)   
 [뷰에서 데이터 필터링](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)   
 [XAML에서 뷰를 사용하여 데이터 정렬 및 그룹화](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)   
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)