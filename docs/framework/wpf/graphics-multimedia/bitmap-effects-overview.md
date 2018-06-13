---
title: 비트맵 효과 개요
ms.date: 03/30/2017
helpviewer_keywords:
- bitmap effects [WPF]
ms.assetid: 23cb338e-4b59-4b52-b294-96431f9c9568
ms.openlocfilehash: 7a93c5e247af7c9a54799721553ba486164a12e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558007"
---
# <a name="bitmap-effects-overview"></a>비트맵 효과 개요
디자이너를 사용 하는 비트맵 효과 되 고 개발자 시각적 효과를 적용 하려면 Windows Presentation Foundation (WPF) 콘텐츠 렌더링 합니다. 예를 들어 비트맵 효과 사용 하면 쉽게 적용할 수는 <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> 효과나 흐림 효과 이미지 또는 단추를 합니다.  
  
> [!IMPORTANT]
>  에 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] 이후 버전의 <xref:System.Windows.Media.Effects.BitmapEffect> 클래스는 사용 되지 않습니다. 사용 하려는 경우는 <xref:System.Windows.Media.Effects.BitmapEffect> 클래스, 사용 되지 않음 예외가 발생 합니다. 클래스 대신에는 <xref:System.Windows.Media.Effects.BitmapEffect> 클래스는는 <xref:System.Windows.Media.Effects.Effect> 클래스입니다. 대부분의 경우에는 <xref:System.Windows.Media.Effects.Effect> 클래스는 훨씬 더 빨라집니다.  
  
  
  
<a name="wpf_effects"></a>   
## <a name="wpf-bitmap-effects"></a>WPF 비트맵 효과  
 비트맵 효과 (<xref:System.Windows.Media.Effects.BitmapEffect> 개체)는 처리 작업을 간단한 픽셀입니다. 비트맵 효과 <xref:System.Windows.Media.Imaging.BitmapSource> 를 입력 및 생성 새 <xref:System.Windows.Media.Imaging.BitmapSource> 흐림 또는 그림자 같은 효과 적용 한 후 합니다. 각 비트맵 효과 같은 필터링 속성을 제어할 수 있는 속성을 공개 <xref:System.Windows.Media.Effects.BlurBitmapEffect.Radius%2A> 의 <xref:System.Windows.Media.Effects.BlurBitmapEffect>합니다.  
  
 특별 한 경우로에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], 효과에 설정 될 수 속성으로 라이브 <xref:System.Windows.Media.Visual> 와 같은 개체는 <xref:System.Windows.Controls.Button> 또는 <xref:System.Windows.Controls.TextBox>합니다. 런타임에 픽셀 처리가 적용되고 렌더링됩니다. 렌더링 시이 경우에 <xref:System.Windows.Media.Visual> 자동으로 변환 되며 해당 <xref:System.Windows.Media.Imaging.BitmapSource> 해당 하는 및에 대 한 입력으로 제공 됩니다는 <xref:System.Windows.Media.Effects.BitmapEffect>합니다. 출력 대체는 <xref:System.Windows.Media.Visual> 개체의 기본 렌더링 동작 합니다. 이 인해 <xref:System.Windows.Media.Effects.BitmapEffect> 개체에에서 렌더링할 소프트웨어만 즉, 하드웨어 가속 없이 시각적 개체에 효과 적용할 경우 시각적 개체를 강제 합니다.  
  
-   <xref:System.Windows.Media.Effects.BlurBitmapEffect> 포커스를 벗어난 표시 되는 개체를 시뮬레이션 합니다.  
  
-   <xref:System.Windows.Media.Effects.OuterGlowBitmapEffect> 개체의 경계 주위에 색상의 무리 짐을 만듭니다.  
  
-   <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> 개체 뒤에 그림자를 만듭니다.  
  
-   <xref:System.Windows.Media.Effects.BevelBitmapEffect> 지정된 된 곡선에 따라 이미지의 표면을 올리는 3d 가장자리를 만듭니다.  
  
-   <xref:System.Windows.Media.Effects.EmbossBitmapEffect> 범프 매핑을 만듭니다는 <xref:System.Windows.Media.Visual> 인공 광원에서 깊이 및 질감 효과 주기 위해 합니다.  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 비트맵 효과는 소프트웨어 모드에서 렌더링됩니다. 효과를 적용하는 모든 개체도 소프트웨어에서 렌더링됩니다. 큰 시각적 개체에 비트맵 효과를 사용하거나 비트맵 효과의 속성에 애니메이션 효과를 줄 때 성능이 가장 크게 저하됩니다. 따라서 여러분도 이러한 방식으로 비트맵 효과를 사용하지 않아야 하는 것은 물론, 다른 사용자들도 바람직한 경험을 얻을 수 있도록 철저히 테스트하고 주의해야 합니다.  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 비트맵 효과는 부분 신뢰 실행을 지원하지 않습니다. 비트맵 효과를 사용하려면 응용 프로그램에 완전 신뢰 권한이 있어야 합니다.  
  
<a name="applyeffects"></a>   
## <a name="how-to-apply-an-effect"></a>효과를 적용하는 방법  
 <xref:System.Windows.Media.Effects.BitmapEffect> 에 속성 <xref:System.Windows.Media.Visual>합니다. 따라서 효과를 시각적 개체와 같은 적용 한 <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Image>, <xref:System.Windows.Media.DrawingVisual>, 또는 <xref:System.Windows.UIElement>, 속성을 설정 하기만 됩니다. <xref:System.Windows.UIElement.BitmapEffect%2A> 단일으로 설정할 수 있습니다 <xref:System.Windows.Media.Effects.BitmapEffect> 개체 또는 여러 효과 사용 하 여 연결 될 수 있습니다는 <xref:System.Windows.Media.Effects.BitmapEffectGroup> 개체입니다.  
  
 다음 예제에서는 적용 하는 <xref:System.Windows.Media.Effects.BitmapEffect> 에서 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]합니다.  
  
 [!code-xaml[EffectsGallery_snip#BlurSimpleExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blursimpleexample.xaml#blursimpleexampleinline)]  
  
 다음 예제에서는 적용 하는 <xref:System.Windows.Media.Effects.BitmapEffect> 코드에서.  
  
 [!code-csharp[EffectsGallery_snip#CodeBehindBlurCodeBehindExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EffectsGallery_snip/CSharp/blurcodebehindexample.xaml.cs#codebehindblurcodebehindexampleinline)]  
  
> [!NOTE]
>  경우는 <xref:System.Windows.Media.Effects.BitmapEffect> 같은 레이아웃 컨테이너에 적용할 <xref:System.Windows.Controls.DockPanel> 또는 <xref:System.Windows.Controls.Canvas>, 요소 또는 시각적 개체를 모든 자식 요소를 포함 하 여의 시각적 트리에 효과가 적용 됩니다.  
  
<a name="customeffects"></a>   
## <a name="creating-custom-effects"></a>사용자 지정 효과 만들기  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서는 또한 관리되는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램에서 사용할 수 있는 사용자 지정 효과를 만들기 위한 관리되지 않는 인터페이스를 제공합니다. 사용자 지정 비트맵 효과를 만들기 위한 추가 참조 자료에 대해서는 [관리되지 않는 WPF 비트맵 효과](https://msdn.microsoft.com/library/ms735092.aspx) 설명서를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.Effects.BitmapEffectGroup>  
 <xref:System.Windows.Media.Effects.BitmapEffectInput>  
 <xref:System.Windows.Media.Effects.BitmapEffectCollection>  
 [관리 되지 않는 WPF 비트맵 효과](https://msdn.microsoft.com/library/ms735092.aspx)  
 [이미징 개요](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)  
 [보안](../../../../docs/framework/wpf/security-wpf.md)  
 [WPF 그래픽 렌더링 개요](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)  
 [2차원 그래픽 및 이미징](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)
