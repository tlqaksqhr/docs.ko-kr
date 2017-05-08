---
title: "성능 최적화: 응용 프로그램 리소스 | Microsoft Docs"
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
  - "응용 프로그램 리소스, 성능"
  - "브러시, 성능"
  - "리소스, 성능"
  - "복사 없이 브러시 공유"
  - "리소스 공유"
  - "정적 리소스"
ms.assetid: 62b88488-c08e-4804-b7de-a1c34fbe929c
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# 성능 최적화: 응용 프로그램 리소스
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 사용하면 비슷한 형식의 요소에서 일관된 모양이나 동작을 지원할 수 있도록 응용 프로그램 리소스를 공유할 수 있습니다.  이 항목에서는 응용 프로그램의 성능을 향상시키는 데 도움이 되는 이 영역과 관련된 몇 가지 권장 사항을 제공합니다.  
  
 리소스에 대한 자세한 내용은 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)를 참조하십시오.  
  
## 리소스 공유  
 응용 프로그램에서 사용자 지정 컨트롤을 사용하고 <xref:System.Windows.ResourceDictionary> 또는 XAML 리소스 노드에 리소스를 정의할 경우 <xref:System.Windows.Application> 또는 <xref:System.Windows.Window> 개체 수준에서 리소스를 정의하거나 사용자 지정 컨트롤의 기본 테마에 정의하는 것이 좋습니다.  사용자 지정 컨트롤의 <xref:System.Windows.ResourceDictionary>에 리소스를 정의하면 해당 컨트롤의 모든 인스턴스에서 성능에 영향을 줍니다.  예를 들어 사용자 지정 컨트롤의 리소스 정의로 정의된 성능을 많이 소비하는 브러시 작업이 있고 사용자 지정 컨트롤의 인스턴스가 많은 경우 응용 프로그램의 작업 집합이 크게 증가합니다.  
  
 다음 예제에서는 이러한 점을 보여 줍니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 사용하여 카드 게임을 개발 중이라고 가정해 봅니다.  대부분의 카드 게임에는 52개의 다른 그림을 가진 52개의 카드가 필요합니다.  이 경우 카드 사용자 지정 컨트롤을 구현하고 카드 사용자 지정 컨트롤의 리소스에서 52개의 브러시\(각각 카드 그림을 나타냄\)를 정의합니다.  주 응용 프로그램에는 처음에 이 카드 사용자 지정 컨트롤의 인스턴스를 52개 만듭니다.  카드 사용자 지정 컨트롤의 각 인스턴스는 <xref:System.Windows.Media.Brush> 개체의 인스턴스를 52개 생성하므로 응용 프로그램에서는 총 52 \* 52개의 <xref:System.Windows.Media.Brush> 개체가 제공됩니다.  브러시를 카드 사용자 지정 컨트롤 리소스에서 <xref:System.Windows.Application> 또는 <xref:System.Windows.Window> 개체 수준으로 이동하거나 사용자 지정 컨트롤에 대한 기본 테마에 정의하면 52개 인스턴스의 카드 컨트롤에서 52개 브러시를 공유하게 되므로 응용 프로그램의 작업 집합이 줄어듭니다.  
  
## 복사 없이 브러시 공유  
 동일한 <xref:System.Windows.Media.Brush> 개체를 사용하는 여러 요소가 있을 경우 브러시를 [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]에서 인라인으로 정의하는 대신에 리소스로 정의하여 참조합니다.  브러시를 [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]에서 인라인으로 정의하면 각 요소에 대한 새 인스턴스가 만들어지는 것과 달리 이 방법은 하나의 인스턴스를 만들어 다시 사용합니다.  
  
 다음 태그 샘플은 이러한 점을 보여 줍니다.  
  
 [!code-xml[Performance#PerformanceSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/BrushResource.xaml#performancesnippet7)]  
  
## 가능한 경우 정적 리소스 사용  
 정적 리소스는 이미 정의된 리소스에 대한 참조를 조회하여 모든 XAML 속성 특성에 대한 값을 제공합니다.  해당 리소스에 대한 조회 동작은 컴파일 타임 조회와 유사합니다.  
  
 반면에 동적 리소스는 초기 컴파일 도중에 임시 표현식을 만들기 때문에 개체를 생성하기 위해 요청된 리소스 값이 실제로 요구될 때까지 리소스 조회가 연기됩니다.  해당 리소스에 대한 조회 동작은 성능에 영향을 주는 런타임 조회와 유사합니다.  응용 프로그램에서 가능하다면 정적 리소스를 사용하고 동적 리소스는 필요한 경우에만 사용합니다.  
  
 다음 태그 샘플은 두 유형의 리소스 사용을 보여 줍니다.  
  
 [!code-xml[Performance#PerformanceSnippet8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/DynamicResource.xaml#performancesnippet8)]  
  
## 참고 항목  
 [WPF 응용 프로그램 성능 최적화](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)   
 [응용 프로그램 성능 계획](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)   
 [하드웨어 이용](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)   
 [레이아웃 및 디자인](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)   
 [2차원 그래픽 및 이미징](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [개체 동작](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)   
 [텍스트](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)   
 [데이터 바인딩](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [기타 성능 권장 사항](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)