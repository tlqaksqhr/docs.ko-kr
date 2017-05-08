---
title: "방법: 그림자가 적용된 텍스트 만들기 | Microsoft Docs"
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
  - "텍스트의 그림자 효과"
  - "텍스트, 숨겨짐"
  - "입력 체계, 그림자 효과"
ms.assetid: 6ab9c754-6001-4708-b479-5367f2fd1a35
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# 방법: 그림자가 적용된 텍스트 만들기
이 단원의 예제에서는 표시된 텍스트에 대해 그림자 효과를 만드는 방법을 보여 줍니다.  
  
## 예제  
 <xref:System.Windows.Media.Effects.DropShadowEffect> 개체를 사용하면 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 개체에 그림자가 적용된 효과를 다양하게 만들 수 있습니다.  다음 예제에서는 그림자 효과가 적용된 텍스트를 보여 줍니다.  이 경우 그림자는 그림자 색깔이 흐린, 부드러운 그림자입니다.  
  
 ![Softness &#61; 0.25인 텍스트 그림자](../../../../docs/framework/wpf/advanced/media/shadowtext01.png "ShadowText01")  
부드러운 그림자가 적용된 텍스트의 예  
  
 <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> 속성을 설정하여 그림자의 너비를 제어할 수 있습니다.  값 `4.0`은 그림자 너비가 4픽셀임을 나타냅니다.  <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> 속성을 수정하여 그림자의 부드러움이나 흐림 정도를 제어할 수 있습니다.  값 `0.0`은 전혀 흐리지 않음을 나타냅니다.  다음 코드 예제에서는 부드러운 그림자를 만드는 방법을 보여 줍니다.  
  
 [!code-xml[TextShadowSnippets#TextShadowSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet1)]  
  
> [!NOTE]
>  이러한 그림자 효과는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 텍스트 렌더링 파이프라인을 거치지 않습니다.  따라서 이러한 효과를 사용할 때 ClearType이 해제되어 있습니다.  
  
 다음 예제에서는 진한 그림자 효과가 적용된 텍스트를 보여 줍니다.  이 경우 그림자가 흐려지지 않습니다.  
  
 ![Softness &#61; 0인 텍스트 그림자](../../../../docs/framework/wpf/advanced/media/shadowtext02.png "ShadowText02")  
진한 그림자가 적용된 텍스트의 예  
  
 <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> 속성을 흐림이 전혀 사용되지 않음을 나타내는 `0.0`으로 설정하여 진한 그림자를 만들 수 있습니다.  <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> 속성을 수정하여 그림자의 방향을 제어할 수 있습니다.  이 속성의 방향 값을 `0`과 `360`도 사이의 값으로 설정합니다.  다음 그림에서는 <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> 속성 설정의 방향 값을 보여 줍니다.  
  
 ![그림자의 DropShadow 정도 설정](../../../../docs/framework/wpf/advanced/media/shadowtext08.png "ShadowText08")  
DropShadow 방향 다이어그램  
  
 다음 코드 예제에서는 진한 그림자를 만드는 방법을 보여 줍니다.  
  
 [!code-xml[TextShadowSnippets#TextShadowSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet2)]  
  
## 흐림 효과 사용  
 <xref:System.Windows.Media.Effects.BlurBitmapEffect>를 사용하여 텍스트 개체 뒤에 놓을 수 있는 그림자 같은 효과를 만들 수 있습니다.  텍스트에 적용된 흐림 비트맵 효과는 모든 방향에서 균등하게 텍스트를 흐리게 만듭니다.  
  
 다음 예제에서는 흐림 효과가 적용된 텍스트를 보여 줍니다.  
  
 ![BlurBitmapEffect를 사용한 텍스트 그림자](../../../../docs/framework/wpf/advanced/media/shadowtext06.png "ShadowText06")  
흐림 효과가 적용된 텍스트의 예  
  
 다음 코드 예제에서는 흐림 효과를 만드는 방법을 보여 줍니다.  
  
 [!code-xml[TextShadowSnippets#TextShadowSnippet6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/BlurShadows.xaml#textshadowsnippet6)]  
  
## 이동 변환 사용  
 <xref:System.Windows.Media.TranslateTransform>을 사용하여 텍스트 개체 뒤에 놓이는 그림자 같은 효과를 만들 수 있습니다.  
  
 다음 코드 예제에서는 <xref:System.Windows.Media.TranslateTransform>을 사용하여 텍스트를 오프셋합니다.  이 예제에서 기본 텍스트 아래에 있는 약간 오프셋된 텍스트 복사본이 그림자 효과를 만듭니다.  
  
 ![TranslateTransform을 사용한 텍스트 그림자](../../../../docs/framework/wpf/advanced/media/shadowtext07.png "ShadowText07")  
그림자 효과에 변환을 적용한 텍스트의 예  
  
 다음 코드 예제에서는 그림자 효과에 변환을 만드는 방법을 보여 줍니다.  
  
 [!code-xml[TextShadowSnippets#TextShadowSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/TransformShadows.xaml#textshadowsnippet7)]