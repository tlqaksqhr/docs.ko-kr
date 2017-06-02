---
title: "ContextMenu 개요 | Microsoft Docs"
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
  - "ContextMenu 컨트롤[WPF], ContextMenu 컨트롤 정보"
  - "컨트롤, ContextMenu"
ms.assetid: 16909c42-799a-4561-91e0-7d69dcfeea91
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# ContextMenu 개요
<xref:System.Windows.Controls.ContextMenu> 클래스는 컨텍스트별 <xref:System.Windows.Controls.Menu>를 사용하여 기능을 노출하는 요소를 나타냅니다.  일반적으로 사용자는 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]에서 마우스 오른쪽 단추를 클릭하여 <xref:System.Windows.Controls.ContextMenu>를 노출합니다.  이 항목에서는 <xref:System.Windows.Controls.ContextMenu> 요소를 소개하고 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 및 코드에서 이 요소를 사용하는 방법에 대한 예제를 제공합니다.  
  
   
  
<a name="contextmenu_control"></a>   
## ContextMenu 컨트롤  
 <xref:System.Windows.Controls.ContextMenu>는 특정 컨트롤에 연결됩니다.  <xref:System.Windows.Controls.ContextMenu> 요소를 사용하면 <xref:System.Windows.Controls.Button>과 같이 특정 컨트롤과 연결된 명령이나 옵션을 지정하는 항목 목록을 사용자에게 표시할 수 있습니다.  사용자는 컨트롤을 마우스 오른쪽 단추로 클릭하여 메뉴를 표시합니다.  일반적으로 <xref:System.Windows.Controls.MenuItem>을 클릭하면 하위 메뉴가 열리거나 응용 프로그램에서 명령을 수행합니다.  
  
<a name="creating_contextmenus"></a>   
## ContextMenu 만들기  
 다음 예제에서는 하위 메뉴가 있는 <xref:System.Windows.Controls.ContextMenu>를 만드는 방법을 보여 줍니다.  <xref:System.Windows.Controls.ContextMenu> 컨트롤은 단추 컨트롤에 연결됩니다.  
  
 [!code-xml[ContextMenu#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml#1)]  
  
 [!code-csharp[ContextMenu#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ContextMenu#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ContextMenu/VisualBasic/Pane1.xaml.vb#2)]  
  
<a name="applying_styles_to_contextmenu"></a>   
## ContextMenu에 스타일 적용  
 컨트롤 <xref:System.Windows.Style>을 사용하면 사용자 지정 컨트롤을 작성하지 않고도 <xref:System.Windows.Controls.ContextMenu>의 모양과 동작을 큰 폭으로 변경할 수 있습니다.  시각적 속성을 설정하는 것뿐만 아니라 컨트롤 일부에 스타일을 적용할 수도 있습니다.  예를 들어 속성을 사용하여 컨트롤 일부의 동작을 변경하거나 <xref:System.Windows.Controls.ContextMenu>에 일부를 추가하거나 레이아웃을 변경할 수 있습니다.  다음 예제에서는 <xref:System.Windows.Controls.ContextMenu> 컨트롤에 스타일을 추가하는 몇 가지 방법을 보여 줍니다.  
  
 첫 번째 예제에서는 사용자 스타일에서 현재 시스템 설정을 사용하는 방법을 보여 주는 `SimpleSysResources`라는 스타일을 정의합니다.  이 예제에서는 <xref:System.Windows.Controls.ContextMenu>의 <xref:System.Windows.Controls.Control.Background%2A> 색으로 <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A>를 할당하고 <xref:System.Windows.Controls.Control.Foreground%2A> 색으로 <xref:System.Windows.SystemColors.MenuTextBrushKey%2A>를 할당합니다.  
  
```  
<Style x:Key="SimpleSysResources" TargetType="{x:Type MenuItem}">  
  <Setter Property = "Background" Value=   
    "{DynamicResource {x:Static SystemColors.MenuHighlightBrushKey}}"/>  
  <Setter Property = "Foreground" Value=   
    "{DynamicResource {x:Static SystemColors.MenuTextBrushKey}}"/>  
</Style>  
```  
  
 다음 예제에서는 <xref:System.Windows.Controls.ContextMenu>에서 발생하는 이벤트에 대한 응답으로 <xref:System.Windows.Trigger> 요소를 사용하여 <xref:System.Windows.Controls.Menu>의 모양을 변경합니다.  사용자가 마우스를 메뉴 위로 이동하면 <xref:System.Windows.Controls.ContextMenu> 항목 모양이 바뀝니다.  
  
```  
<Style x:Key="Triggers" TargetType="{x:Type MenuItem}">  
  <Style.Triggers>  
    <Trigger Property="MenuItem.IsMouseOver" Value="true">  
      <Setter Property = "FontSize" Value="16"/>  
      <Setter Property = "FontStyle" Value="Italic"/>  
      <Setter Property = "Foreground" Value="Red"/>  
    </Trigger>  
  </Style.Triggers>  
</Style>  
```  
  
## 참고 항목  
 <xref:System.Windows.Controls.ContextMenu>   
 <xref:System.Windows.Style>   
 <xref:System.Windows.Controls.Menu>   
 <xref:System.Windows.Controls.MenuItem>   
 [ContextMenu](../../../../docs/framework/wpf/controls/contextmenu.md)   
 [ContextMenu 스타일 및 템플릿](../../../../docs/framework/wpf/controls/contextmenu-styles-and-templates.md)   
 [WPF Controls Gallery 샘플](http://go.microsoft.com/fwlink/?LinkID=160053)