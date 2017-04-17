---
title: "방법: ColumnDefinitionsCollections 및 RowDefinitionsCollections를 사용하여 열 및 행 조작 | Microsoft Docs"
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
  - "클래스, ColumnDefinitionCollection"
  - "클래스, RowDefinitionCollection"
  - "ColumnDefinitionCollection 클래스"
  - "컨트롤, Grid 클래스"
  - "Grid 컨트롤, ColumnDefinitionCollection 클래스"
  - "Grid 컨트롤, RowDefinitionCollection 클래스"
  - "RowDefinitionCollection 클래스"
ms.assetid: bfc7160a-45f2-4e17-9961-df414dfb13c5
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: ColumnDefinitionsCollections 및 RowDefinitionsCollections를 사용하여 열 및 행 조작
이 예제에서는 <xref:System.Windows.Controls.ColumnDefinitionCollection> 및 <xref:System.Windows.Controls.RowDefinitionCollection> 클래스의 메서드를 사용하여 행이나 열의 내용 추가, 지우기 또는 계산과 같은 작업을 수행하는 방법을 보여 줍니다.  예를 들어 <xref:System.Windows.Controls.ColumnDefinition> 또는 <xref:System.Windows.Controls.RowDefinition>에 포함된 항목에 대해 <xref:System.Windows.Controls.ColumnDefinitionCollection.Add%2A>, <xref:System.Windows.Controls.ColumnDefinitionCollection.Clear%2A> 또는 <xref:System.Windows.Controls.ColumnDefinitionCollection.Count%2A>를 수행할 수 있습니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.FrameworkElement.Name%2A>이 `grid1`인 <xref:System.Windows.Controls.Grid> 요소를 만듭니다.  <xref:System.Windows.Controls.Grid>에는 각각 서로 다른 컬렉션 메서드로 제어되는 <xref:System.Windows.Controls.Button> 요소가 저장되는 <xref:System.Windows.Controls.StackPanel>이 포함됩니다.  <xref:System.Windows.Controls.Button>을 클릭하면 코드 숨김 파일에서 메서드 호출이 활성화됩니다.  
  
 [!code-xml[ColumnDefinitionsGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ColumnDefinitionsGrid/CSharp/Window1.xaml#1)]  
  
 이 예제에서는 각각 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 파일의 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트에 해당하는 일련의 사용자 지정 메서드를 정의합니다.  <xref:System.Windows.Controls.Grid>의 열과 행 수를 여러 방법으로 변경할 수 있습니다. 여기에는 행과 열의 추가 또는 제거와 전체 행과 열 수의 계산이 포함됩니다.  <xref:System.ArgumentOutOfRangeException> 및 <xref:System.ArgumentException> 예외가 발생하지 않도록 하려면 <xref:System.Windows.Controls.ColumnDefinitionCollection.RemoveRange%2A> 메서드가 제공하는 오류 검사 기능을 사용할 수 있습니다.  
  
 [!code-csharp[ColumnDefinitionsGrid#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ColumnDefinitionsGrid/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ColumnDefinitionsGrid#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ColumnDefinitionsGrid/VisualBasic/Window1.xaml.vb#2)]  
  
## 참고 항목  
 <xref:System.Windows.Controls.Grid>   
 <xref:System.Windows.Controls.ColumnDefinitionCollection>   
 <xref:System.Windows.Controls.RowDefinitionCollection>