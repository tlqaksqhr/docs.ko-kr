---
title: "방법: ContextMenuOpening 이벤트 처리 | Microsoft Docs"
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
  - "ContextMenuOpening 이벤트"
ms.assetid: 789652fb-1951-4217-934a-7843e355adf4
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: ContextMenuOpening 이벤트 처리
응용 프로그램에서 <xref:System.Windows.FrameworkElement.ContextMenuOpening> 이벤트를 처리하여 기존 컨텍스트 메뉴를 표시하기 전에 조정하거나 이벤트 데이터에서 <xref:System.Windows.RoutedEventArgs.Handled%2A> 속성을 `true`로 설정하여 다른 경우에는 표시되는 메뉴가 표시되지 않도록 할 수 있습니다.  이벤트 데이터에서 <xref:System.Windows.RoutedEventArgs.Handled%2A>를 `true`로 설정하는 일반적인 이유는 메뉴 전체를 새 <xref:System.Windows.Controls.ContextMenu> 개체로 바꾸기 위한 것입니다. 이 경우 작업을 취소하고 새로 열기를 시작해야 할 수 있습니다.  <xref:System.Windows.FrameworkElement.ContextMenuOpening> 이벤트에 대한 처리기를 작성하는 경우 <xref:System.Windows.Controls.ContextMenu> 컨트롤과 컨트롤 전반적으로 컨텍스트 메뉴의 열기와 위치 지정을 담당하는 서비스 사이에 타이밍 문제가 있음을 알고 있어야 합니다.  이 항목에서는 다양한 컨텍스트 메뉴 열기 시나리오에 대한 코드 기술 몇 가지를 설명하고 타이밍 문제가 발생하는 사례를 보여 줍니다.  
  
 <xref:System.Windows.FrameworkElement.ContextMenuOpening> 이벤트를 처리하기 위한 몇 가지 시나리오가 있습니다.  
  
-   표시하기 전에 메뉴 항목 조정  
  
-   표시하기 전에 전체 메뉴 바꾸기  
  
-   기존 컨텍스트 메뉴의 완전한 억제 및 컨텍스트 메뉴 표시 제한  
  
## 예제  
  
## 표시하기 전에 메뉴 항목 조정  
 기존 메뉴 항목 조정은 꽤 간단하며 가장 일반적인 시나리오입니다.  응용 프로그램의 현재 상태 정보 또는 컨텍스트 메뉴가 요청된 개체에서 속성으로 사용 가능한 특정 상태 정보에 대한 응답으로 컨텍스트 메뉴 옵션을 추가하거나 제거하기 위해 필요한 작업입니다.  
  
 일반적인 기술은 마우스 오른쪽 단추로 클릭한 특정 컨트롤인 이벤트의 소스를 가져오고 여기에서 <xref:System.Windows.FrameworkElement.ContextMenu%2A> 속성을 가져오는 것입니다.  일반적으로 <xref:System.Windows.Controls.ItemsControl.Items%2A> 컬렉션을 검사하여 메뉴에 이미 존재하는 컨텍스트 메뉴 항목을 확인한 다음 적절한 새 <xref:System.Windows.Controls.MenuItem> 항목을 컬렉션에 추가하거나 컬렉션에서 제거합니다.  
  
 [!code-csharp[ContextMenuOpeningHandlers#AddItemNoHandle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#additemnohandle)]  
  
## 표시하기 전에 전체 메뉴 바꾸기  
 다른 시나리오는 전체 컨텍스트 메뉴를 바꾸려는 경우입니다.  물론 이전 코드의 변형을 사용하여 기존 컨텍스트 메뉴의 모든 항목을 제거하고 0 항목부터 시작하여 새로 추가할 수 있습니다.  컨텍스트 메뉴의 모든 항목을 바꾸는 더 직관적인 방법은 새 <xref:System.Windows.Controls.ContextMenu>를 만들어 여기에 항목을 채운 다음, 컨트롤의 <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=fullName> 속성을 새 <xref:System.Windows.Controls.ContextMenu>로 설정하는 것입니다.  
  
 다음은 <xref:System.Windows.Controls.ContextMenu>를 바꾸기 위한 간단한 처리기 코드입니다.  코드는 둘 이상의 예제 처리기에서 호출되기 때문에 분산되어 있는 사용자 지정 `BuildMenu` 메서드를 참조합니다.  
  
 [!code-csharp[ContextMenuOpeningHandlers#ReplaceNoReopen](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#replacenoreopen)]  
  
 [!code-csharp[ContextMenuOpeningHandlers#BuildMenu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#buildmenu)]  
  
 하지만 <xref:System.Windows.FrameworkElement.ContextMenuOpening>에 대해 이러한 처리기 스타일을 사용하는 경우, <xref:System.Windows.Controls.ContextMenu>를 설정하는 개체에 기존 컨텍스트 메뉴가 없을 때 타이밍 문제가 발생할 수 있습니다.  사용자가 마우스 오른쪽 단추로 컨트롤을 클릭하면 기존 <xref:System.Windows.Controls.ContextMenu>가 비어 있거나 null인 경우라도 <xref:System.Windows.FrameworkElement.ContextMenuOpening>이 발생합니다.  하지만 이 경우 소스 요소에 설정하는 새 <xref:System.Windows.Controls.ContextMenu>는 너무 늦게 도달하여 표시되지 않습니다.  또한 사용자가 마우스 오른쪽 단추를 또 클릭하면 이번에는 새 <xref:System.Windows.Controls.ContextMenu>가 나타나고, 값은 null이 아니며, 처리기가 두 번째 실행될 때 처리기는 메뉴를 적절하게 바꿔서 표시합니다.  여기에는 두 가지 가능한 해결 방법이 있습니다.  
  
1.  항상 처리기 코드로 바꿔야 할 최소 하나의 자리 표시자 <xref:System.Windows.Controls.ContextMenu>가 있는 컨트롤에 대해 <xref:System.Windows.FrameworkElement.ContextMenuOpening> 처리기를 실행합니다.  이 경우에도 이전 예제에 표시된 처리기를 사용할 수 있지만 일반적으로 초기 태그에서 자리 표시자 <xref:System.Windows.Controls.ContextMenu>를 할당합니다.  
  
     [!code-xml[ContextMenuOpeningHandlers#XAMLWithInitCM](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml#xamlwithinitcm)]  
  
2.  몇 가지 예비 논리를 기반으로 초기 <xref:System.Windows.Controls.ContextMenu> 값은 null일 수 있다고 가정합니다.  <xref:System.Windows.Controls.ContextMenu>에서 null을 검사하거나, 코드에 처리기가 최소 한 번 이상 실행되었는지 검사하기 위한 플래그를 사용합니다.  <xref:System.Windows.Controls.ContextMenu>가 표시되려고 한다고 가정하기 때문에 처리기는 이벤트 데이터에서 <xref:System.Windows.RoutedEventArgs.Handled%2A>를 `true`로 설정합니다.  컨텍스트 메뉴 표시를 담당하는 <xref:System.Windows.Controls.ContextMenuService>에 대해 이벤트 데이터에서 <xref:System.Windows.RoutedEventArgs.Handled%2A>의 `true` 값은 이벤트를 발생시킨 컨텍스트 메뉴\/컨트롤 조합에 대한 표시 취소 요청을 나타냅니다.  
  
 이제 문제가 있다고 생각되는 컨텍스트 메뉴가 표시되지 않도록 했으므로 다음 단계에서는 새 컨텍스트 메뉴를 제공하여 표시합니다.  새 메뉴를 설정하는 방법은 기본적으로 이전 처리기와 마찬가지입니다. 새 <xref:System.Windows.Controls.ContextMenu>를 빌드하고 컨트롤 소스의 <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=fullName> 속성을 함께 설정합니다.  여기서 첫 번째 시도에서 표시되지 않게 설정한 컨텍스트 메뉴가 표시되도록 지정하는 단계가 추가됩니다.  강제로 표시하려면 처리기 내에서 <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A?displayProperty=fullName> 속성을 `true`로 설정합니다.  처리기에서 컨텍스트 메뉴를 열면 <xref:System.Windows.FrameworkElement.ContextMenuOpening> 이벤트가 다시 발생하므로 주의해야 합니다.  처리기에 다시 들어가면 무한 반복이 됩니다.  이런 이유 때문에 <xref:System.Windows.FrameworkElement.ContextMenuOpening> 이벤트 처리기 안에서 컨텍스트 메뉴를 열 때 플래그를 사용하거나 `null`을 검사해야 합니다.  
  
## 기존 컨텍스트 메뉴의 억제 및 컨텍스트 메뉴 표시 제한  
 메뉴를 완전히 억제하는 처리기를 작성하는 마지막 시나리오는 많이 사용되지 않습니다.  지정된 컨트롤이 컨텍스트 메뉴를 표시하지 않는 경우에는 사용자가 요청할 때 메뉴를 억제하는 대신 이를 보장하기 위한 더 적절한 방법이 있을 것입니다.  하지만 처리기를 사용하여 컨텍스트 메뉴를 억제하고 아무것도 표시하지 않으려면 처리기는 이벤트 데이터에서 <xref:System.Windows.RoutedEventArgs.Handled%2A>를 `true`로 설정해야 합니다.  컨텍스트 메뉴 표시를 담당하는 <xref:System.Windows.Controls.ContextMenuService>는 컨트롤에서 발생시킨 이벤트의 이벤트 데이터를 검사합니다.  이벤트 경로 중 어떤 곳에서 <xref:System.Windows.RoutedEventArgs.Handled%2A>에 표시된 경우 이벤트를 시작한 컨텍스트 메뉴 열기 작업이 억제됩니다.  
  
 [!code-csharp[ContextMenuOpeningHandlers#ReplaceReopen](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#replacereopen)]  
  
## 참고 항목  
 <xref:System.Windows.Controls.ContextMenu>   
 <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=fullName>   
 [기본 요소 개요](../../../../docs/framework/wpf/advanced/base-elements-overview.md)   
 [ContextMenu 개요](../../../../docs/framework/wpf/controls/contextmenu-overview.md)