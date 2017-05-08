---
title: "방법: 사용자 지정 라우트된 이벤트 만들기 | Microsoft Docs"
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
  - "만들기, 라우트된 이벤트"
  - "이벤트, 라우팅"
  - "라우트된 이벤트, 만들기"
ms.assetid: b79f459a-1c3f-4045-b2d4-1659cc8eaa3c
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: 사용자 지정 라우트된 이벤트 만들기
[이벤트 라우팅](GTMT)을 지원하는 사용자 지정 이벤트를 만들려면 <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> 메서드를 사용하여 <xref:System.Windows.RoutedEvent>를 등록해야 합니다.  이 예제에서는 사용자 지정 라우트된 이벤트를 만드는 데 대한 기본 사항을 설명합니다.  
  
## 예제  
 다음 예제와 같이 먼저 <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> 메서드를 사용하여 <xref:System.Windows.RoutedEvent>를 등록합니다.  규칙에 따라 <xref:System.Windows.RoutedEvent> 정적 필드 이름에는 ***Event***라는 접미사를 사용해야 합니다.  이 예제에서 이벤트 이름은 `Tap`이고 이벤트의 라우팅 전략은 <xref:System.Windows.RoutingStrategy>입니다.  등록 호출 후에는 이벤트에 대한 추가 및 제거 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 이벤트 접근자를 제공할 수 있습니다.  
  
 이 예제에서는 `OnTap`이라는 가상 메서드를 통해 이벤트를 발생시키지만 이벤트를 발생시키는 방법 및 이벤트가 변경에 응답하는 방법은 필요에 맞게 설정할 수 있습니다.  
  
 또한 이 예제에서는 기본적으로 <xref:System.Windows.Controls.Button>의 서브클래스 전체를 구현합니다. 즉, 이 서브클래스를 별도의 어셈블리로 빌드한 후 별도의 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 페이지에 사용자 지정 클래스로 인스턴스화합니다.  이는 다른 컨트롤로 구성된 트리에 서브클래싱된 컨트롤을 삽입할 수 있고, 이 경우 이러한 컨트롤의 사용자 지정 이벤트의 이벤트 라우팅 기능이 모든 네이티브 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 요소의 이벤트 라우팅 기능과 동일하다는 점을 보여 주기 위함입니다.  
  
 [!code-csharp[RoutedEventCustom#CustomClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/SDKSampleLibrary/class1.cs#customclass)]
 [!code-vb[RoutedEventCustom#CustomClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventCustom/VB/SDKSampleLibrary/Class1.vb#customclass)]  
  
 [!code-xml[RoutedEventCustom#Page](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/RoutedEventCustomApp/default.xaml#page)]  
  
 터널링 이벤트도 같은 방법으로 만들 수 있으며 이 경우에는 등록 호출 시 <xref:System.Windows.RoutedEvent.RoutingStrategy%2A>를 <xref:System.Windows.RoutingStrategy>로 설정하는 점만 다릅니다.  규칙에 따라 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 터널링 이벤트에는 "Preview"라는 접두사가 붙습니다.  
  
 버블링 이벤트 작동 방법에 대한 예제를 보려면 [라우트된 이벤트 처리](../../../../docs/framework/wpf/advanced/how-to-handle-a-routed-event.md)를 참조하십시오.  
  
## 참고 항목  
 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)   
 [입력 개요](../../../../docs/framework/wpf/advanced/input-overview.md)   
 [컨트롤 제작 개요](../../../../docs/framework/wpf/controls/control-authoring-overview.md)