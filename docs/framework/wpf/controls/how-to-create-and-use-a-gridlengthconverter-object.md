---
title: "방법: GridLengthConverter 개체 만들기 및 사용 | Microsoft Docs"
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
  - "Grid 컨트롤, 만들기, GridLengthConverter 개체"
ms.assetid: 5ab75911-e36a-4825-80e4-081c57e8e182
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: GridLengthConverter 개체 만들기 및 사용
## 예제  
 다음 예제에서는 <xref:System.Windows.GridLengthConverter>의 인스턴스를 만들고 사용하는 방법을 보여 줍니다.  이 예제에서는 <xref:System.Windows.Controls.ListBoxItem>의 <xref:System.Windows.Controls.ContentControl.Content%2A>를 <xref:System.Windows.GridLength>의 인스턴스로 변환하는 <xref:System.Windows.GridLengthConverter>에 <xref:System.Windows.Controls.ListBoxItem>을 전달하는 `changeCol`이라는 사용자 지정 메서드를 정의합니다.  변환된 값은 <xref:System.Windows.Controls.ColumnDefinition> 요소의 <xref:System.Windows.Controls.ColumnDefinition.Width%2A> 속성 값으로 다시 전달됩니다.  
  
 이 예제에서는 `changeColVal`이라는 두 번째 사용자 지정 메서드도 정의합니다.  이 사용자 지정 메서드는 <xref:System.Windows.Controls.Slider>의 <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A>를 <xref:System.String>으로 변환한 다음 이 값을 요소의 <xref:System.Windows.Controls.ColumnDefinition.Width%2A>로 다시 <xref:System.Windows.Controls.ColumnDefinition>에 전달합니다.  
  
 <xref:System.Windows.Controls.ListBoxItem>의 내용은 별도의 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 파일에 정의됩니다.  
  
 [!code-csharp[gridlengthConverterGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridlengthConverterGrid/CSharp/Window1.xaml.cs#1)]
 [!code-vb[gridlengthConverterGrid#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridlengthConverterGrid/VisualBasic/Window1.xaml.vb#1)]  
  
## 참고 항목  
 <xref:System.Windows.GridLengthConverter>   
 <xref:System.Windows.GridLength>