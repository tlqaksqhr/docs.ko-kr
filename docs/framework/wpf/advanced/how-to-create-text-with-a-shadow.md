---
title: "방법: 그림자가 적용된 텍스트 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- typography [WPF], shadow effects
- shadow effects in text [WPF]
- text [WPF], shadowed
ms.assetid: 6ab9c754-6001-4708-b479-5367f2fd1a35
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 31bbc3da54c10304e52f93d38365a8d9ed005505
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-create-text-with-a-shadow"></a>방법: 그림자가 적용된 텍스트 만들기
이 단원의 예제에서는 표시된 텍스트에 대해 그림자 효과를 만드는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 <xref:System.Windows.Media.Effects.DropShadowEffect> 개체 다양 한 놓기에 대 한 그림자 효과 만들 수 있습니다 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 개체입니다. 다음 예제에서는 그림자 효과가 적용된 텍스트를 보여 줍니다. 이 경우 그림자는 그림자 색깔이 흐린, 부드러운 그림자입니다.  
  
 ![Softness &#61; 인 텍스트 그림자 0.25](../../../../docs/framework/wpf/advanced/media/shadowtext01.jpg "ShadowText01")  
부드러운 그림자가 적용된 텍스트의 예  
  
 그림자의 너비를 설정 하 여 제어할 수 있습니다는 <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> 속성입니다. 값이 `4.0` 그림자 높이 인 4 픽셀을 나타냅니다. 부드러운 정도 제어할 수 있습니다 또는 수정 하 여 그림자 흐림 효과 <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> 속성입니다. 값이 `0.0` 없는 흐림 효과 나타냅니다. 다음 코드 예제에서는 부드러운 그림자를 만드는 방법을 보여 줍니다.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet1)]  
  
> [!NOTE]
>  이러한 그림자 효과 통과 하지 않는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 텍스트 렌더링 파이프라인. 따라서 이러한 효과를 사용할 때 ClearType이 사용하지 않도록 설정됩니다.  
  
 다음 예제에서는 진한 그림자 효과가 적용된 텍스트를 보여 줍니다. 이 경우 그림자가 흐려지지 않습니다.  
  
 ![Softness &#61; 인 텍스트 그림자 0](../../../../docs/framework/wpf/advanced/media/shadowtext02.jpg "ShadowText02")  
진한 그림자가 적용된 텍스트의 예  
  
 설정 하 여 하드 그림자를 만들 수는 <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> 속성을 `0.0`는 없는 뜨 리고 사용 해야 함을 나타냅니다. 그림자의 방향을 수정 하 여 제어할 수 있습니다는 <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> 속성입니다. 이 속성의 방향 값도 값으로 설정 간의 `0` 및 `360`합니다. 다음 그림의 방향 값을 보여 줍니다.는 <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> 속성을 설정 합니다.  
  
 ![그림자의 DropShadow 정도 설정](../../../../docs/framework/wpf/advanced/media/shadowtext08.png "ShadowText08")  
DropShadow 방향 다이어그램  
  
 다음 코드 예제에서는 진한 그림자를 만드는 방법을 보여 줍니다.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet2)]  
  
## <a name="using-a-blur-effect"></a>흐림 효과 사용  
 A <xref:System.Windows.Media.Effects.BlurBitmapEffect> 텍스트 개체 뒤에 배치할 수 있는 그림자 같은 효과 만드는 데 사용할 수 있습니다. 텍스트에 적용된 흐림 비트맵 효과는 모든 방향에서 균등하게 텍스트를 흐리게 만듭니다.  
  
 다음 예제에서는 흐림 효과가 적용된 텍스트를 보여 줍니다.  
  
 ![BlurBitmapEffect를 사용한 텍스트 그림자](../../../../docs/framework/wpf/advanced/media/shadowtext06.jpg "ShadowText06")  
흐림 효과가 적용된 텍스트의 예  
  
 다음 코드 예제에는 흐린 효과를 만드는 방법을 보여 줍니다.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/BlurShadows.xaml#textshadowsnippet6)]  
  
## <a name="using-a-translate-transform"></a>좌표 이동 변환 사용  
 A <xref:System.Windows.Media.TranslateTransform> 텍스트 개체 뒤에 배치할 수 있는 그림자 같은 효과 만드는 데 사용할 수 있습니다.  
  
 다음 코드 예제에서는 한 <xref:System.Windows.Media.TranslateTransform> 텍스트 오프셋 합니다. 이 예제에서 기본 텍스트 아래에 있는 약간 오프셋된 텍스트 복사본이 그림자 효과를 만듭니다.  
  
 ![Translatetransform을 사용한 텍스트 그림자](../../../../docs/framework/wpf/advanced/media/shadowtext07.jpg "ShadowText07")  
그림자 효과에 변환을 적용한 텍스트의 예  
  
 다음 코드 예제에서는 그림자 효과에 변환을 만드는 방법을 보여 줍니다.  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/TransformShadows.xaml#textshadowsnippet7)]
