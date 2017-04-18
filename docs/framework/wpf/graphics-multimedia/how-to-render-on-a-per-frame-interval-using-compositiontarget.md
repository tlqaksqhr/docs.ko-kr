---
title: "방법: CompositionTarget을 사용하여 프레임별 간격에 렌더링 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "CompositionTarget 개체, 프레임당 렌더링"
  - "CompositionTarget 개체를 사용한 프레임별 렌더링"
ms.assetid: 701246cd-66b7-4d69-ada9-17b3b433d95d
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: CompositionTarget을 사용하여 프레임별 간격에 렌더링
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 애니메이션 엔진은 프레임 기반 애니메이션을 만드는 데 사용할 수 있는 여러 가지 기능을 제공합니다.  그러나 응용 프로그램에서 프레임별로 렌더링을 세밀하게 제어해야 할 경우가 있습니다.  <xref:System.Windows.Media.CompositionTarget> 개체는 프레임당 콜백을 기반으로 사용자 지정 애니메이션을 만들 수 있는 기능을 제공합니다.  
  
 <xref:System.Windows.Media.CompositionTarget>은 응용 프로그램이 그려지는 표시 화면을 나타내는 정적 클래스입니다.  <xref:System.Windows.Media.CompositionTarget.Rendering> 이벤트는 응용 프로그램 장면이 그려질 때마다 발생합니다.  렌더링 프레임 속도는 초당 장면이 그려지는 횟수입니다.  
  
> [!NOTE]
>  <xref:System.Windows.Media.CompositionTarget>을 사용하는 전체 코드 샘플을 보려면 [Using the CompositionTarget 샘플](http://go.microsoft.com/fwlink/?LinkID=160045)을 참조하십시오.  
  
## 예제  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 렌더링 프로세스 동안 <xref:System.Windows.Media.CompositionTarget.Rendering> 이벤트가 발생합니다.  다음 예제에서는 <xref:System.EventHandler> 대리자를 <xref:System.Windows.Media.CompositionTarget>의 정적 <xref:System.Windows.Media.CompositionTarget.Rendering> 메서드에 등록하는 방법을 보여 줍니다.  
  
 [!code-csharp[CompositionTargetSample#CompositionTarget1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CompositionTargetSample/CSharp/Window1.xaml.cs#compositiontarget1)]
 [!code-vb[CompositionTargetSample#CompositionTarget1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CompositionTargetSample/visualbasic/window1.xaml.vb#compositiontarget1)]  
  
 렌더링 이벤트 처리기 메서드를 사용하면 사용자 지정 그리기 콘텐츠를 만들 수 있습니다.  이 이벤트 처리기 메서드는 프레임당 한 번씩 호출됩니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]가 [시각적 트리](GTMT)에 있는 일관된 렌더링 데이터를 컴포지션 장면 그래프를 통해 마샬링하는 경우 이벤트 처리기 메서드가 호출됩니다.  또한 [시각적 트리](GTMT) 변경으로 인해 컴포지션 장면 그래프를 업데이트해야 할 경우 이벤트 처리기 메서드도 호출됩니다.  이벤트 처리기 메서드는 레이아웃이 계산된 후에 호출됩니다.  그러나 이벤트 처리기 메서드에서 레이아웃을 수정할 수 있습니다. 즉, 렌더링 전에 레이아웃이 한 번 더 계산됩니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.CompositionTarget> 이벤트 처리기 메서드에서 사용자 지정 그리기를 제공할 수 있는 방법을 보여 줍니다.  이 경우 <xref:System.Windows.Controls.Canvas>의 배경색은 마우스의 좌표 위치를 기반으로 하는 색상 값으로 그려집니다.  마우스를 <xref:System.Windows.Controls.Canvas> 안에서 이동하면 배경색이 변합니다.  또한 현재 경과된 시간과 렌더링된 프레임의 전체 수를 기반으로 평균 프레임 속도가 다시 계산됩니다.  
  
 [!code-csharp[CompositionTargetSample#CompositionTarget2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CompositionTargetSample/CSharp/Window1.xaml.cs#compositiontarget2)]
 [!code-vb[CompositionTargetSample#CompositionTarget2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CompositionTargetSample/visualbasic/window1.xaml.vb#compositiontarget2)]  
  
 사용자 지정 그리기는 컴퓨터에 따라 다른 속도로 실행될 수 있습니다.  이는 사용자 지정 그리기가 프레임 속도의 영향을 받기 때문입니다.  실행 중인 시스템과 해당 시스템의 작업 부하에 따라 <xref:System.Windows.Media.CompositionTarget.Rendering> 이벤트가 초당 호출되는 횟수가 달라질 수 있습니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램을 실행하는 장치의 그래픽 하드웨어 기능 및 성능을 확인하는 방법에 대한 자세한 내용은 [그래픽 렌더링 계층](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md)을 참조하십시오.  
  
 이벤트가 발생하는 동안 렌더링 <xref:System.EventHandler> 대리자를 추가하거나 제거하면 이벤트 발생이 완료될 때까지 작업이 지연됩니다.  이는 <xref:System.MulticastDelegate> 기반 이벤트가 CLR\(공용 언어 런타임\)에서 처리되는 방식에서도 마찬가지입니다.  또한 렌더링 이벤트가 반드시 특정 순서대로 호출된다고는 보장할 수 없습니다.  특정 순서를 따라야 하는 여러 <xref:System.EventHandler> 대리자가 있는 경우에는 하나의 <xref:System.Windows.Media.CompositionTarget.Rendering> 이벤트를 등록한 다음 올바른 순서에 따라 직접 대리자를 반복해서 사용해야 합니다.  
  
## 참고 항목  
 <xref:System.Windows.Media.CompositionTarget>   
 [WPF 그래픽 렌더링 개요](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)