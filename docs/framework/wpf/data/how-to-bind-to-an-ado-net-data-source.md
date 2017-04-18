---
title: "방법: ADO.NET 데이터 소스 바인딩 | Microsoft Docs"
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
  - "ADO.NET 데이터 소스, 바인딩"
  - "바인딩, ADO.NET 데이터 소스에"
  - "데이터 바인딩(data binding), ADO.NET 데이터 소스에 바인딩"
ms.assetid: a70c6d7b-7b38-4fdf-b655-4804db7c8315
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: ADO.NET 데이터 소스 바인딩
이 예제에서는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.ListBox> 컨트롤을 [!INCLUDE[TLA#tla_adonet](../../../../includes/tlasharptla-adonet-md.md)] `DataSet`에 바인딩하는 방법을 보여 줍니다.  
  
## 예제  
 이 예제에서는 연결 문자열에 지정된 `Access MDB` 파일인 데이터 소스에 연결하는 데 `OleDbConnection` 개체가 사용됩니다.  연결이 설정되면 `OleDbDataAdpater` 개체가 만들어집니다.  `OleDbDataAdpater` 개체는 Select [!INCLUDE[TLA#tla_sql](../../../../includes/tlasharptla-sql-md.md)] 문을 실행하여 데이터베이스에서 레코드 집합을 검색합니다.  [!INCLUDE[TLA2#tla_sql](../../../../includes/tla2sharptla-sql-md.md)] 명령의 결과는 `OleDbDataAdapter`의 `Fill` 메서드를 호출하여 `DataSet`의 `DataTable`에 저장됩니다.  이 예제에서 `DataTable`의 이름은 `BookTable`로 지정됩니다.  그런 다음 이 예제에서는 <xref:System.Windows.Controls.ListBox>의 <xref:System.Windows.FrameworkElement.DataContext%2A> 속성을 `DataSet` 개체로 설정합니다.  
  
 [!code-csharp[ADODataSet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 그러면 <xref:System.Windows.Controls.ListBox>의 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 속성을 `DataSet`의 `BookTable`에 바인딩할 수 있습니다.  
  
 [!code-xml[ADODataSet#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#2)]  
  
 `BookItemTemplate`은 데이터가 나타나는 방식을 정의하는 <xref:System.Windows.DataTemplate>입니다.  
  
 [!code-xml[ADODataSet#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#3)]  
  
 `IntColorConverter`는 `int`를 색으로 변환합니다.  이 변환기를 사용할 경우 `NumPages`의 값이 350 미만이면 세 번째 <xref:System.Windows.Controls.TextBlock>의 <xref:System.Windows.Controls.TextBlock.Background%2A> 색이 녹색으로 나타나고 그렇지 않으면 빨간색으로 나타납니다.  여기에서는 변환기의 구현을 보여 주지 않습니다.  
  
## 참고 항목  
 <xref:System.Windows.Data.BindingListCollectionView>   
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)