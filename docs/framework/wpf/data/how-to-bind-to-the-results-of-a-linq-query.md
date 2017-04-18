---
title: "방법: LINQ 쿼리 결과에 바인딩 | Microsoft Docs"
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
  - "LINQ 쿼리 결과에 바인딩[WPF]"
  - "LINQ 쿼리 실행[WPF], 결과에 바인딩"
ms.assetid: ff2844d9-17ed-4ea6-aab1-5111af0bc684
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# 방법: LINQ 쿼리 결과에 바인딩
이 예제에서는 LINQ 쿼리를 실행한 다음 결과에 바인딩하는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 두 개의 목록 상자를 만듭니다.  첫 번째 목록 상자에는 세 개의 목록 항목이 들어 있습니다.  
  
 [!code-xml[LinqExample#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml#ui)]  
  
 첫 번째 목록 상자에서 항목을 선택하면 다음 이벤트 처리기가 호출됩니다.  이 예제에서 `Tasks`는 `Task` 개체의 컬렉션입니다.  `Task` 클래스에는 `Priority`라는 속성이 있습니다.  이 이벤트 처리기는 선택된 우선 순위 값을 가지는 `Task` 개체의 컬렉션을 반환하는 LINQ 쿼리를 실행한 다음 이를 <xref:System.Windows.FrameworkElement.DataContext%2A>로 설정합니다.  
  
 [!code-csharp[LinqExample#Using](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#using)]  
[!code-csharp[LinqExample#Tasks](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#tasks)]  
[!code-csharp[LinqExample#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#handler)]  
  
 두 번째 목록 상자는 해당 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 값이 `{Binding}`으로 설정되기 때문에 이 컬렉션에 바인딩됩니다.  그 결과, 반환된 컬렉션을 표시합니다\(`myTaskTemplate` <xref:System.Windows.DataTemplate>에 기반함\).  
  
## 참고 항목  
 [XAML의 바인딩에 사용할 수 있는 데이터 만들기](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md)   
 [선택에 따라 수집 및 표시 정보에 바인딩](../../../../docs/framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md)   
 [WPF 버전 4.5의 새로운 기능](../../../../docs/framework/wpf/getting-started/whats-new.md)   
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)