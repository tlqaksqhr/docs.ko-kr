---
title: "미리 보기 이벤트 | Microsoft Docs"
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
  - "이벤트, 미리 보기"
  - "이벤트, 표시 안 함"
  - "이벤트 미리 보기"
  - "이벤트 표시 안 함"
ms.assetid: b5032308-aa9c-4d02-af11-630ecec8df7e
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 미리 보기 이벤트
터널링 이벤트라고도 하는 미리 보기 이벤트는 응용 프로그램 루트에서 이벤트를 발생시키고 이벤트 데이터에 소스로 보고되는 요소까지의 경로를 따라 이동하는 라우트된 이벤트입니다.  모든 이벤트 시나리오에 미리 보기 이벤트가 필요하거나 지원되는 것은 아닙니다. 이 항목에서는 미리 보기 이벤트를 사용하는 시나리오, 응용 프로그램이나 구성 요소에서 미리 보기 이벤트를 처리하는 방법 및 사용자 지정 구성 요소나 클래스에서 미리 보기 이벤트를 만들어야 하는 경우에 대해 설명합니다.  
  
## 미리 보기 이벤트 및 입력  
 일반적으로 미리 보기 이벤트를 처리하는 경우에는 이벤트 데이터에 이벤트를 처리된 것으로 표시할 때 주의해야 합니다.  이벤트를 발생시킨 요소, 즉 이벤트 데이터에 소스로 보고된 요소 이외의 다른 요소에서 미리 보기 이벤트를 처리하면 해당 요소는 원래 발생시킨 이벤트를 처리하지 못합니다.  그러나 복합 컨트롤을 만드는 과정에서 해당 요소 사이에 관계가 형성되는 경우와 같이 이러한 결과가 필요할 때도 있습니다.  
  
 특히 입력 이벤트의 경우 미리 보기 이벤트는 해당되는 버블링 이벤트와 이벤트 데이터 인스턴스를 공유합니다.  따라서 미리 보기 이벤트 클래스 처리기를 사용하여 입력 이벤트를 처리된 것으로 표시하면 버블링 입력 이벤트 클래스가 호출되지 않습니다.  또는 미리 보기 이벤트 인스턴스 처리기를 사용하여 이벤트를 처리된 것으로 표시하면 일반적으로 버블링 이벤트에 대한 처리기가 호출되지 않습니다.  이벤트가 처리된 것으로 표시되더라도 처리기가 호출되도록 하는 옵션을 사용하여 클래스 처리기나 인스턴스 처리기를 등록하거나 연결할 수 있지만 이 방법은 일반적으로 사용되지 않습니다.  
  
 클래스 처리 및 클래스 처리와 미리 보기 이벤트의 관계에 대한 자세한 내용은 [라우트된 이벤트를 처리된 것으로 표시 및 클래스 처리](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md)를 참조하십시오.  
  
### 컨트롤에서 억제하는 이벤트 문제 해결  
 미리 보기 이벤트는 복합 컨트롤에서 입력 이벤트를 처리하는 경우에 일반적으로 사용됩니다.  원래 이벤트 대신 더 많은 정보를 제공하거나 더 구체적인 동작을 수행하는 구성 요소 정의 이벤트를 사용하기 위해 컨트롤 작성자가 컨트롤에서 특정 이벤트가 발생되지 않도록 설정하는 경우도 있습니다.  예를 들어 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.Button>은 <xref:System.Windows.Controls.Button> 또는 해당 복합 요소에서 발생시키는 <xref:System.Windows.UIElement.MouseLeftButtonDown> 및 <xref:System.Windows.UIElement.MouseLeftButtonDown> 버블링 이벤트를 억제하고, 대신 마우스를 캡처하고 <xref:System.Windows.Controls.Button> 자체에서 항상 발생되는 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트를 발생시킵니다.  이벤트와 해당 데이터는 계속해서 경로를 따라 이동하지만 <xref:System.Windows.Controls.Button>이 이벤트 데이터를 <xref:System.Windows.RoutedEventArgs.Handled%2A>로 표시하기 때문에 `handledEventsToo`인 경우 동작하도록 특별히 설정된 이벤트 처리기만 호출됩니다.  컨트롤에서 발생되지 않도록 설정한 이벤트를 응용 프로그램 루트의 다른 요소에서는 여전히 처리할 수 있도록 하려면 코드에서 `handledEventsToo`를 `true`로 설정하고 처리기를 연결해야 합니다.  그러나 이 방법보다는 입력 이벤트에 해당하는 미리 보기 이벤트를 처리하도록 경로를 변경하는 것이 더 간단합니다.  예를 들어 컨트롤에서 <xref:System.Windows.UIElement.MouseLeftButtonDown> 이벤트가 발생하지 않도록 설정한 경우 대신 <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown>에 대한 처리기를 연결해 보십시오.  이 방법은 <xref:System.Windows.UIElement.MouseLeftButtonDown>과 같은 기본 요소 입력 이벤트에만 사용할 수 있습니다.  이러한 입력 이벤트는 터널\/버블 쌍을 사용하고, 둘 모두 이벤트를 발생시키며 이벤트 데이터를 공유합니다.  
  
 이 두 가지 방법 모두 예기치 않은 결과를 초래하거나 제한 사항이 있습니다.  미리 보기 이벤트를 처리하는 경우에는 미리 보기 이벤트를 처리할 때 버블링 이벤트를 처리해야 하는 처리기가 비활성화되는 결과가 초래될 수 있습니다. 따라서 이벤트가 경로에서 미리 보기 부분에 있는 동안은 이벤트를 처리된 것으로 표시하지 않아야 하는 제한 사항이 있습니다.  `handledEventsToo` 기술을 사용하는 경우에는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에 `handledEventsToo` 처리기를 특성으로 지정할 수 없기 때문에 이벤트 처리기를 연결할 요소에 대한 개체 참조를 가져온 후 코드에서 이벤트 처리기를 직접 등록해야 하는 단점이 있습니다.  
  
## 참고 항목  
 [라우트된 이벤트를 처리된 것으로 표시 및 클래스 처리](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md)   
 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)