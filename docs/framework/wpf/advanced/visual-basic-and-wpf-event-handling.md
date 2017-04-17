---
title: "Visual Basic 및 WPF 이벤트 처리 | Microsoft Docs"
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
  - "이벤트 처리기, Visual Basic"
  - "Visual Basic, 이벤트 처리기"
ms.assetid: ad4eb9aa-3afc-4a71-8cf6-add3fbea54a1
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Visual Basic 및 WPF 이벤트 처리
[!INCLUDE[TLA#tla_visualbnet](../../../../includes/tlasharptla-visualbnet-md.md)] 언어의 경우에는 이벤트 처리기를 특성에 연결하거나 <xref:System.Windows.UIElement.AddHandler%2A> 메서드를 사용하는 대신 언어 특정 `Handles` 키워드를 사용하여 이벤트 처리기를 인스턴스에 연결할 수 있습니다.  하지만 `Handles` 구문은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이벤트 시스템의 일부 특정 [라우트된 이벤트](GTMT) 기능을 지원할 수 없기 때문에 처리기를 인스턴스에 연결하기 위한 `Handles` 기술에는 몇 가지 제한 사항이 있습니다.  
  
## WPF 응용 프로그램에서 "핸들" 사용  
 `Handles`로 인스턴스 및 이벤트에 연결되는 이벤트 처리기는 모두 인스턴스의 partial 클래스 선언 안에서 정의해야 합니다. 이는 요소에 대한 특성 값을 통해 할당된 이벤트 처리기에 대한 요구 사항이기도 합니다.  <xref:System.Windows.FrameworkContentElement.Name%2A> 속성 값이 있거나 [x:Name 지시문](../../../../docs/framework/xaml-services/x-name-directive.md)이 선언된 페이지의 요소에 대해서만 `Handles`을 지정할 수 있습니다.  이것은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 <xref:System.Windows.FrameworkContentElement.Name%2A>이 `Handles` 구문에 필요한 *Instance.Event* 참조 형식을 지원하기 위해 필요한 인스턴스 참조를 만들기 때문입니다.  <xref:System.Windows.FrameworkContentElement.Name%2A> 참조 없이 `Handles`에 사용할 수 있는 유일한 요소는 partial 클래스를 정의하는 루트 요소 인스턴스입니다.  
  
 `Handles` 뒤에 쉼표로 *Instance.Event* 참조를 구분하여 여러 요소에 같은 처리기를 할당할 수 있습니다.  
  
 `Handles`을 사용하여 둘 이상의 처리기를 같은 *Instance.Event* 참조에 할당할 수 있습니다.  처리기가 `Handles` 참조에 지정되는 순서에는 중요성을 부여하지 마십시오. 같은 이벤트를 처리하는 처리기가 임의의 순서로 호출될 수 있다고 가정해야 합니다.  
  
 선언에서 `Handles`로 추가된 처리기를 제거하려면 <xref:System.Windows.UIElement.RemoveHandler%2A>를 호출할 수 있습니다.  
  
 멤버 표에서 처리되는 이벤트를 정의하는 인스턴스에 처리기를 연결하는 경우에는 `Handles`을 사용하여 [라우트된 이벤트](GTMT)에 대한 처리기를 연결할 수 있습니다.  [라우트된 이벤트](GTMT)의 경우 `Handles`로 연결되는 처리기는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 특성으로 연결된 특성이 사용하는 것과 같은 라우팅 규칙 또는 <xref:System.Windows.UIElement.AddHandler%2A>의 공통 시그니처를 사용한 라우팅 규칙을 따릅니다.  즉, 이벤트가 이미 처리된 것으로 표시된 경우\(이벤트 데이터의 <xref:System.Windows.RoutedEventArgs.Handled%2A> 속성이 `True`인 경우\) `Handles`로 연결된 처리기는 해당 이벤트 인스턴스에 반응하여 호출되지 않습니다.  이벤트는 경로의 다른 요소에 대한 인스턴스 처리기 또는 경로를 따라 현재 요소 또는 이전 요소의 클래스 처리에 의해 처리된 것으로 표시될 수 있습니다.  쌍을 이룬 터널\/버블 이벤트를 지원하는 입력 이벤트의 경우 터널링 경로가 이벤트 쌍을 처리된 것으로 표시했을 수 있습니다.  라우트된 이벤트에 대한 자세한 내용은 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)를 참조하십시오.  
  
## 처리기 추가에 대한 "핸들"의 제한 사항  
 `Handles`은 [연결된 이벤트](GTMT)에 대한 처리기는 참조할 수 없습니다.  해당 연결된 이벤트에 대한 `add` 접근자 메서드를 사용하거나 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 *typename.eventname* 이벤트 특성을 사용해야 합니다.  자세한 내용은 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)를 참조하십시오.  
  
 [라우트된 이벤트](GTMT)의 경우 인스턴스 멤버 표에 해당 이벤트가 있는 인스턴스의 처리기를 할당하는 데에만 `Handles`을 사용할 수 있습니다.  하지만 일반적으로 라우트된 이벤트의 경우 부모 요소의 멤버 표에 해당 이벤트가 없더라도 부모 요소는 자식 요소의 이벤트에 대한 수신기가 될 수 있습니다.  특성 구문에서 처리하고자 하는 이벤트를 실제로 정의하는 형식을 정규화하는 *typename.membername* 특성 형식을 통해 이를 지정할 수 있습니다.  예를 들어 부모 `Page`\(`Clic`k 이벤트가 정의되지 않은\)는 `Button.Click`의 형식으로 특성 처리기를 할당하여 단추 클릭 이벤트를 수신할 수 있습니다.  하지만 `Handles`은 충돌 *Instance.Event* 형식을 지원해야 하므로 *typename.membername* 형식을 지원하지 않습니다.  자세한 내용은 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)를 참조하십시오.  
  
 `Handles`은 이미 처리된 것으로 표시된 이벤트에 대해 호출되는 처리기를 연결할 수 없습니다.  대신 코드를 사용하여 <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29>의 `handledEventsToo` 오버로드를 호출해야 합니다.  
  
> [!NOTE]
>  XAML에서 동일한 이벤트에 대해 이벤트 처리기를 지정할 때 [!INCLUDE[vb_current_short](../../../../includes/vb-current-short-md.md)] 코드에 `Handles` 구문을 사용하지 마십시오.  이 경우 이벤트 처리기가 두 번 호출됩니다.  
  
## WPF에서 "핸들" 기능을 구현하는 방법  
 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 페이지를 컴파일할 때 중간 파일은 <xref:System.Windows.FrameworkContentElement.Name%2A> 속성이 설정된\(또는 [x:Name 지시문](../../../../docs/framework/xaml-services/x-name-directive.md)가 선언된\) 페이지의 모든 요소에 대한 `Friend` `WithEvents` 참조를 선언합니다.  이름 지정된 각 요소는 `Handles`을 통해 처리기에 할당될 수 있는 요소입니다.  
  
> [!NOTE]
>  [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] 내에서는 [!INCLUDE[TLA2#tla_intellisense](../../../../includes/tla2sharptla-intellisense-md.md)]를 통해 페이지에서 `Handles` 참조에 사용할 수 있는 요소를 자동으로 완성할 수 있습니다.  하지만 이렇게 하려면 중간 파일이 모든 `Friends` 참조를 채울 수 있도록 한 번의 컴파일 패스가 필요합니다.  
  
## 참고 항목  
 <xref:System.Windows.UIElement.AddHandler%2A>   
 [라우트된 이벤트를 처리된 것으로 표시 및 클래스 처리](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md)   
 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)   
 [XAML 개요\(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)