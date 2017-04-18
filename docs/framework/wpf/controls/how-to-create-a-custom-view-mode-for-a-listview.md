---
title: "방법: ListView의 사용자 지정 뷰 모드 만들기 | Microsoft Docs"
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
  - "ListView 컨트롤, 사용자 지정 보기 모드 만들기"
ms.assetid: 71077349-eeb9-4344-ab29-b5df96df3314
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: ListView의 사용자 지정 뷰 모드 만들기
이 예제에서는 <xref:System.Windows.Controls.ListView> 컨트롤의 사용자 지정 <xref:System.Windows.Controls.ListView.View%2A> 모드를 만드는 방법을 보여 줍니다.  
  
## 예제  
 <xref:System.Windows.Controls.ListView> 컨트롤의 사용자 지정 뷰를 만들 때는 <xref:System.Windows.Controls.ViewBase> 클래스를 사용해야 합니다.  다음 예제에서는 <xref:System.Windows.Controls.ViewBase> 클래스에서 파생되는 `PlainView` 보기 모드를 보여 줍니다.  
  
 [!code-csharp[ListViewCustomView#PlainView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/PlainView.cs#plainview)]
 [!code-vb[ListViewCustomView#PlainView](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/plainview.vb#plainview)]  
  
 사용자 지정 뷰에 스타일을 적용하려면 <xref:System.Windows.Style> 클래스를 사용합니다.  다음 예제에서는 `PlainView` 보기 모드에 <xref:System.Windows.Style>을 정의합니다.  이전 예제에서 이 스타일은 `PlainView`에 대해 정의된 <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> 속성의 값으로 설정되었습니다.  
  
 [!code-xml[ListViewCustomView#PlainViewStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Themes/Generic.xaml#plainviewstyle)]  
  
 사용자 지정 보기 모드에서 데이터의 레이아웃을 정의하려면 <xref:System.Windows.DataTemplate> 개체를 정의합니다.  다음 예제에서는 `PlainView` 보기 모드에서 데이터를 표시하는 데 사용할 수 있는 <xref:System.Windows.DataTemplate>을 정의합니다.  
  
 [!code-xml[ListViewCustomView#PlainViewDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewdatatemplate)]  
  
 다음 예제에서는 이전 예제에서 정의한 <xref:System.Windows.DataTemplate>을 사용하는 `PlainView` 보기 모드에 대한 <xref:System.Windows.ResourceKey>를 정의하는 방법을 보여 줍니다.  
  
 [!code-xml[ListViewCustomView#PlainViewtileView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewtileview)]  
  
 <xref:System.Windows.Controls.ListView.View%2A> 속성을 리소스 키로 설정한 경우 <xref:System.Windows.Controls.ListView> 컨트롤은 사용자 지정 뷰를 사용할 수 있습니다.  다음 예제에서는 `PlainView`를 <xref:System.Windows.Controls.ListView>의 보기 모드로 지정하는 방법을 보여 줍니다.  
  
 [!code-csharp[ListViewCustomView#ListViewtileViewmode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml.cs#listviewtileviewmode)]
 [!code-vb[ListViewCustomView#ListViewtileViewmode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/window1.xaml.vb#listviewtileviewmode)]  
  
 전체 샘플을 보려면 [ListView with Multiple Views 샘플](http://go.microsoft.com/fwlink/?LinkID=160013)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Controls.ListView>   
 <xref:System.Windows.Controls.GridView>   
 [방법 항목](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)   
 [ListView 개요](../../../../docs/framework/wpf/controls/listview-overview.md)   
 [GridView 개요](../../../../docs/framework/wpf/controls/gridview-overview.md)