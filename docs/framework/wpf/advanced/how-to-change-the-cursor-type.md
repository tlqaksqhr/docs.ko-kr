---
title: "방법: 커서 형식 변경 | Microsoft Docs"
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
  - "커서(마우스 포인터)"
  - "마우스 포인터(커서), 커서 형식"
ms.assetid: 08c945a7-8ab0-4320-acf3-0b4955a344c2
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: 커서 형식 변경
이 예제에서는 특정 요소 및 응용 프로그램에 대해 마우스 포인터의 <xref:System.Windows.Input.Cursor>를 변경하는 방법을 보여 줍니다.  
  
 이 예제는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 파일 및 코드 숨김 파일로 구성되어 있습니다.  
  
## 예제  
 원하는 <xref:System.Windows.Input.Cursor>를 선택할 수 있는 <xref:System.Windows.Controls.ComboBox>, 변경된 커서를 요소 하나에만 적용할지 또는 응용 프로그램 전체에 적용할지 결정하는 <xref:System.Windows.Controls.RadioButton> 개체 쌍 및 새 커서를 적용할 요소를 나타내는 <xref:System.Windows.Controls.Border>로 구성된 사용자 인터페이스를 만듭니다.  
  
 [!code-xml[cursors#ChangeCursorsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml#changecursorsxaml)]  
  
 다음 코드 숨김 파일은 <xref:System.Windows.Controls.ComboBox>에서 커서 형식을 변경했을 때 호출되는 <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> 이벤트 처리기를 만듭니다.  Switch 문에서는 커서 이름을 필터링하고 이름이 *DisplayArea*인 <xref:System.Windows.Controls.Border>에 <xref:System.Windows.FrameworkElement.Cursor%2A> 속성을 설정합니다.  
  
 커서 변경을 "Entire Application"으로 설정하면 <xref:System.Windows.Controls.Border> 컨트롤의 <xref:System.Windows.FrameworkElement.Cursor%2A> 속성에 <xref:System.Windows.Input.Mouse.OverrideCursor%2A> 속성이 설정됩니다.  이렇게 하면 응용 프로그램 전체에서 커서가 변경됩니다.  
  
 [!code-csharp[cursors#ChangeCursorsSample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml.cs#changecursorssample)]
 [!code-vb[cursors#ChangeCursorsSample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/cursors/VisualBasic/Window1.xaml.vb#changecursorssample)]  
  
## 참고 항목  
 [입력 개요](../../../../docs/framework/wpf/advanced/input-overview.md)