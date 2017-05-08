---
title: "방법: ICommandSource 구현 | Microsoft Docs"
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
  - "ICommandSource 인터페이스, 구현"
  - "인터페이스, ICommandSource, 구현"
ms.assetid: 7452dd39-6e11-44bf-806a-31d87f3772ac
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: ICommandSource 구현
이 예제에서는 <xref:System.Windows.Input.ICommandSource>를 구현하여 명령 소스를 만드는 방법을 보여 줍니다.  명령 소스는 명령 호출 방법을 아는 개체입니다.  <xref:System.Windows.Input.ICommandSource> 인터페이스는 <xref:System.Windows.Input.ICommandSource.Command%2A>, <xref:System.Windows.Input.ICommandSource.CommandParameter%2A> 및 <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>의 세 멤버를 노출합니다.  <xref:System.Windows.Input.ICommandSource.Command%2A>는 호출될 명령입니다.  <xref:System.Windows.Input.ICommandSource.CommandParameter%2A>는 명령 소스에서 명령을 처리하는 메서드로 전달되는 사용자 정의 데이터 형식입니다.  <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>은 명령이 실행되는 개체입니다.  
  
 이 예제에서는 <xref:System.Windows.Controls.Slider> 컨트롤을 서브클래싱하고 <xref:System.Windows.Input.ICommandSource>를 구현하는 클래스를 만듭니다.  
  
## 예제  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.MenuItem> 및 <xref:System.Windows.Controls.ListBoxItem>과 같은 <xref:System.Windows.Input.ICommandSource>를 구현하는 많은 클래스를 제공합니다.  명령 소스는 명령을 호출하는 방법을 정의합니다.  <xref:System.Windows.Controls.Button> 및 <xref:System.Windows.Controls.MenuItem>의 경우 클릭했을 때 명령을 호출합니다.  <xref:System.Windows.Controls.ListBoxItem>은 두 번 클릭했을 때 명령을 호출합니다.  이러한 클래스는 <xref:System.Windows.Input.ICommandSource.Command%2A> 속성이 설정된 경우에만 명령 소스가 됩니다.  
  
 이 예제의 경우 슬라이더를 이동할 때, 더 정확하게는 <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> 속성이 변경될 때 명령을 호출합니다.  
  
 다음은 클래스 정의입니다.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceClassDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourceclassdefinition)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceClassDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourceclassdefinition)]  
  
 다음 단계에서는 <xref:System.Windows.Input.ICommandSource> 멤버를 구현합니다.  이 예제에서는 속성이 <xref:System.Windows.DependencyProperty> 개체로 구현됩니다.  이를 통해 속성이 데이터 바인딩을 사용할 수 있습니다.  <xref:System.Windows.DependencyProperty> 클래스에 대한 자세한 내용은 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)를 참조하십시오.  데이터 바인딩에 대한 자세한 내용은 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)를 참조하십시오.  
  
 여기에는 <xref:System.Windows.Input.ICommandSource.Command%2A> 속성만 표시됩니다.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandpropertydefinition)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandpropertydefinition)]  
  
 다음은 <xref:System.Windows.DependencyProperty> 변경 콜백입니다.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandChanged](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandchanged)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceCommandChanged](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandchanged)]  
  
 다음 단계에서는 명령 소스와 연결된 명령을 추가 및 제거합니다.  이벤트 처리기가 이전 명령과 연결되어 있으므로 새 명령이 추가될 때 <xref:System.Windows.Input.ICommandSource.Command%2A> 속성을 단순하게 덮어쓸 수는 없으며 이러한 속성이 있는 경우 먼저 제거해야 합니다.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcehookunhookcommands)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcehookunhookcommands)]  
  
 마지막 단계에서는 <xref:System.Windows.Input.ICommand.CanExecuteChanged> 처리기와 <xref:System.Windows.Input.ICommand.Execute%2A> 메서드에 대한 논리를 만듭니다.  
  
 <xref:System.Windows.Input.ICommand.CanExecuteChanged> 이벤트는 현재 명령 대상에 대해 실행할 수 있는 명령의 기능이 변경되었을 수 있음을 명령 소스에 알립니다.  명령 소스가 이 이벤트를 수신하면 일반적으로 명령에 대해 <xref:System.Windows.Input.ICommand.CanExecute%2A> 메서드를 호출합니다.  명령을 현재 명령 대상에 대해 실행할 수 없는 경우 명령 소스는 대개 자체적으로 비활성화됩니다.  명령을 현재 명령 대상에 대해 실행할 수 있는 경우 명령 소스는 대개 자체적으로 활성화됩니다.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandCanExecuteChanged](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandcanexecutechanged)]
 [!code-vb[ImplementICommandSource#ImplementICommandCanExecuteChanged](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandcanexecutechanged)]  
  
 마지막 단계는 <xref:System.Windows.Input.ICommand.Execute%2A> 메서드입니다.  명령이 <xref:System.Windows.Input.RoutedCommand>인 경우 <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand.Execute%2A> 메서드가 호출되고, 그렇지 않은 경우에는 <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A> 메서드가 호출됩니다.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandExecute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandexecute)]
 [!code-vb[ImplementICommandSource#ImplementICommandExecute](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandexecute)]  
  
## 참고 항목  
 <xref:System.Windows.Input.ICommandSource>   
 <xref:System.Windows.Input.ICommand>   
 <xref:System.Windows.Input.RoutedCommand>   
 [명령 개요](../../../../docs/framework/wpf/advanced/commanding-overview.md)