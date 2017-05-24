---
title: "비트맵 효과 개요 | Microsoft Docs"
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
  - "비트맵 효과"
ms.assetid: 23cb338e-4b59-4b52-b294-96431f9c9568
caps.latest.revision: 34
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 31
---
# 비트맵 효과 개요
비트맵 효과를 사용하면 디자이너와 개발자는 렌더링된 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 콘텐츠에 시각적 효과를 적용할 수 있습니다.  예를 들어 비트맵 효과를 사용하면 <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> 효과 또는 흐림 효과를 이미지나 단추에 쉽게 적용할 수 있습니다.  
  
> [!IMPORTANT]
>  [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] 이상에서 <xref:System.Windows.Media.Effects.BitmapEffect> 클래스는 사용되지 않습니다.  <xref:System.Windows.Media.Effects.BitmapEffect> 클래스를 사용하려고 하면 사용되지 않음 예외가 발생합니다.  <xref:System.Windows.Media.Effects.BitmapEffect> 클래스 대신 <xref:System.Windows.Media.Effects.Effect> 클래스를 사용할 수 있습니다.  대부분의 경우 <xref:System.Windows.Media.Effects.Effect> 클래스가 훨씬 빠릅니다.  
  
   
  
<a name="wpf_effects"></a>   
## WPF 비트맵 효과  
 비트맵 효과\(<xref:System.Windows.Media.Effects.BitmapEffect> 개체\)는 간단한 픽셀 처리 작업입니다.  비트맵 효과는 <xref:System.Windows.Media.Imaging.BitmapSource>를 입력으로 사용하고 흐림 또는 그림자와 같은 효과를 적용한 후 새 <xref:System.Windows.Media.Imaging.BitmapSource>를 생성합니다.  각 비트맵 효과는 <xref:System.Windows.Media.Effects.BlurBitmapEffect>의 <xref:System.Windows.Media.Effects.BlurBitmapEffect.Radius%2A>와 같은 필터링 속성을 제어할 수 있는 속성을 노출합니다.  
  
 특별한 경우로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 효과는 <xref:System.Windows.Controls.Button> 또는 <xref:System.Windows.Controls.TextBox>와 같은 라이브 <xref:System.Windows.Media.Visual> 개체의 속성으로 설정될 수 있습니다.  픽셀 처리는 런타임에 적용 및 렌더링됩니다.  이 경우 렌더링 시에 <xref:System.Windows.Media.Visual>은 해당 <xref:System.Windows.Media.Imaging.BitmapSource>와 동등하게 자동 변환되고 <xref:System.Windows.Media.Effects.BitmapEffect>에 대한 입력으로 제공됩니다.  출력은 <xref:System.Windows.Media.Visual> 개체의 기본 렌더링 동작을 대체합니다.  이로 인해 <xref:System.Windows.Media.Effects.BitmapEffect> 개체는 시각적 표시가 소프트웨어에서만 렌더링되도록 강제합니다.  즉, 효과가 적용될 때 시각적 표시에서 하드웨어 가속은 없습니다.  
  
-   <xref:System.Windows.Media.Effects.BlurBitmapEffect>는 포커스를 벗어나 표시되는 개체를 시뮬레이션합니다.  
  
-   <xref:System.Windows.Media.Effects.OuterGlowBitmapEffect>는 개체 주위에 색 헤일로 효과를 만듭니다.  
  
-   <xref:System.Windows.Media.Effects.DropShadowBitmapEffect>는 개체 뒤에 그림자를 만듭니다.  
  
-   <xref:System.Windows.Media.Effects.BevelBitmapEffect>는 지정된 곡선을 따라 이미지 표면을 높이는 3D 효과를 만듭니다.  
  
-   <xref:System.Windows.Media.Effects.EmbossBitmapEffect>는 인공 광원으로부터의 깊이 및 질감 효과를 제공하기 위해 <xref:System.Windows.Media.Visual>의 범프 매핑을 만듭니다.  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 비트맵 효과는 소프트웨어 모드로 렌더링됩니다.  효과가 적용되는 개체도 소프트웨어에서 렌더링됩니다.  큰 시각적 표시에서 비트맵 효과를 사용하거나 비트맵 효과의 속성에 애니메이션 효과를 줄 경우 성능이 가장 많이 저하됩니다.  이 방법으로 비트맵 효과를 전혀 사용하지 않아야 한다는 뜻은 아니지만 사용자 경험이 예상대로 제공되려면 주의를 기울이고 충분히 테스트해야 합니다.  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 비트맵 효과의 경우 부분 신뢰 실행이 지원되지 않습니다.  비트맵 효과를 사용하려면 응용 프로그램에 완전 신뢰 권한이 있어야 합니다.  
  
<a name="applyeffects"></a>   
## 효과 적용 방법  
 <xref:System.Windows.Media.Effects.BitmapEffect>는 <xref:System.Windows.Media.Visual>의 속성입니다.  따라서 <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Image>, <xref:System.Windows.Media.DrawingVisual> 또는 <xref:System.Windows.UIElement>와 같은 시각적 표시에 효과를 적용하는 것은 속성을 설정하는 것만큼 쉽습니다.  <xref:System.Windows.UIElement.BitmapEffect%2A>를 단일 <xref:System.Windows.Media.Effects.BitmapEffect> 개체로 설정하거나 <xref:System.Windows.Media.Effects.BitmapEffectGroup> 개체를 사용하여 여러 효과를 연결할 수 있습니다.  
  
 다음 예제에서는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서 <xref:System.Windows.Media.Effects.BitmapEffect>를 적용하는 방법을 보여 줍니다.  
  
 [!code-xml[EffectsGallery_snip#BlurSimpleExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blursimpleexample.xaml#blursimpleexampleinline)]  
  
 다음 예제에서는 코드에서 <xref:System.Windows.Media.Effects.BitmapEffect>를 적용하는 방법을 보여 줍니다.  
  
 [!code-csharp[EffectsGallery_snip#CodeBehindBlurCodeBehindExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blurcodebehindexample.xaml.cs#codebehindblurcodebehindexampleinline)]  
  
> [!NOTE]
>  <xref:System.Windows.Media.Effects.BitmapEffect>가 <xref:System.Windows.Controls.DockPanel> 또는 <xref:System.Windows.Controls.Canvas>와 같은 레이아웃 컨테이너에 적용될 경우 효과는 모든 자식 요소를 포함하는 요소 또는 시각적 표시의 시각적 트리에 적용됩니다.  
  
<a name="customeffects"></a>   
## 사용자 지정 효과 만들기  
 또한 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]는 관리되는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램에서 사용할 수 있는 사용자 지정 효과를 만들기 위한 관리되지 않는 인터페이스를 제공합니다.  사용자 지정 비트맵 효과를 만들기 위한 추가 참조 자료는 [WPF Bitmap Effects](_wibe_lh) 설명서를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Media.Effects.BitmapEffectGroup>   
 <xref:System.Windows.Media.Effects.BitmapEffectInput>   
 <xref:System.Windows.Media.Effects.BitmapEffectCollection>   
 [Unmanaged WPF Bitmap Effect](_wibe_lh)   
 [이미징 개요](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)   
 [보안](../../../../docs/framework/wpf/security-wpf.md)   
 [WPF 그래픽 렌더링 개요](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)   
 [2차원 그래픽 및 이미징](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)