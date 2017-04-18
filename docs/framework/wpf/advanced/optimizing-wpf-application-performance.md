---
title: "WPF 응용 프로그램 성능 최적화 | Microsoft Docs"
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
  - "응용 프로그램 최적화"
  - "응용 프로그램 렌더링, 성능"
  - "응용 프로그램, 최적화"
  - "WPF 응용 프로그램, 최적화"
ms.assetid: ac8c6aa3-3c68-4a24-9827-3b6c829c1ebf
caps.latest.revision: 45
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 45
---
# WPF 응용 프로그램 성능 최적화
이 단원은 응용 프로그램 성능을 개선할 방법을 찾는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램 개발자가 참조할 수 있도록 제공됩니다.  [!INCLUDE[TLA#tla_avalonwinfx](../../../../includes/tlasharptla-avalonwinfx-md.md)] 및 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 처음 사용하는 개발자의 경우 먼저 두 플랫폼에 대해 숙지할 필요가 있습니다.  이 단원에서는 사용자가 두 플랫폼의 작동 방식을 알고 있다고 가정합니다. 이 문서는 자신의 응용 프로그램을 지속적으로 실행할 수 있을 정도의 지식을 갖춘 프로그래머를 위해 작성되었습니다.  
  
> [!NOTE]
>  이 단원에서 제공되는 성능 데이터는 512RAM 및 ATI Radeon 9700 그래픽 카드가 있는 2.8GHz PC에서 실행되는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램을 기반으로 합니다.  
  
## 단원 내용  
 [응용 프로그램 성능 계획](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
  
 [하드웨어 이용](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
  
 [레이아웃 및 디자인](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
  
 [2차원 그래픽 및 이미징](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
  
 [개체 동작](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
  
 [응용 프로그램 리소스](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
  
 [텍스트](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
  
 [데이터 바인딩](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
  
 [컨트롤](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)  
  
 [기타 성능 권장 사항](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)  
  
 [응용 프로그램 시작 시간](../../../../docs/framework/wpf/advanced/application-startup-time.md)  
  
## 참고 항목  
 <xref:System.Windows.Media.RenderOptions>   
 <xref:System.Windows.Media.RenderCapability>   
 [그래픽 렌더링 계층](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md)   
 [WPF 그래픽 렌더링 개요](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)   
 [레이아웃](../../../../docs/framework/wpf/advanced/layout.md)   
 [WPF의 트리](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)   
 [Drawing 개체 개요](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)   
 [DrawingVisual 개체 사용](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)   
 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)   
 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)   
 [WPF의 문서](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [서식 있는 텍스트 그리기](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)   
 [WPF의 입력 체계](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)   
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [탐색 개요](../../../../docs/framework/wpf/app-development/navigation-overview.md)   
 [애니메이션에 대한 유용한 정보](../../../../docs/framework/wpf/graphics-multimedia/animation-tips-and-tricks.md)   
 [연습: WPF 응용 프로그램에서 응용 프로그램 데이터 캐싱](../../../../docs/framework/wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md)