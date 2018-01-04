---
title: "방법: UIElement를 투명하거나 반투명하게 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UIElements [WPF], transparency
- opacity [WPF], of UIElements
- transparency of UIElements [WPF]
- UIElements [WPF], opacity
ms.assetid: a49fc8d6-7b32-4f28-9122-39b632a19b4b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 25245319c02ae376410d71afb7a1e56eda259e99
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-make-a-uielement-transparent-or-semi-transparent"></a>방법: UIElement를 투명하거나 반투명하게 만들기
확인 하는 방법을 보여 주는이 예제는 <xref:System.Windows.UIElement> 투명 하 게 또는 반투명 하 게 합니다. 요소를 투명 하 게 또는 반투명 하 게 확인을 설정 하면 해당 <xref:System.Windows.UIElement.Opacity%2A> 속성입니다. 값이 `0.0` 요소 값 완전히 투명 하 게 만듭니다 `1.0` 요소를 완전히 불투명 하 게 만듭니다. 값이 `0.5` 사용 하면 요소 50% 불투명 하 고 까지입니다. 요소의 <xref:System.Windows.UIElement.Opacity%2A> 로 설정 된 `1.0` 기본적으로 합니다.  
  
## <a name="example"></a>예  
 다음 예에서는 <xref:System.Windows.UIElement.Opacity%2A> 단추의 `0.25`, 내용을에 (이 경우 단추의 텍스트) 25% 불투명 하 게 만들기.  
  
 [!code-xaml[brushsamples_snip#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#2)]  
  
 [!code-csharp[brushsamples_procedural_snip#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#2)]  
  
 요소의 콘텐츠에 자체적인 경우 <xref:System.Windows.UIElement.Opacity%2A> 설정을, 해당 값은 요소를 포함 하는에 곱할 <xref:System.Windows.UIElement.Opacity%2A>합니다.  
  
 다음 예제는 단추를 설정 <xref:System.Windows.UIElement.Opacity%2A> 를 `0.25`, 및 <xref:System.Windows.UIElement.Opacity%2A> 의 <xref:System.Windows.Controls.Image> 를 단추에 포함 된 컨트롤 `0.5`합니다. 결과적으로, 이미지 표시 12.5% 불투명: 0.25 * 0.5 = 0.125 합니다.  
  
 [!code-xaml[brushsamples_snip#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#3)]  
  
 [!code-csharp[brushsamples_procedural_snip#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#3)]  
  
 요소의 불투명도 제어 하는 방법의 불투명도 설정 하는 것은 <xref:System.Windows.Media.Brush> 요소를 칠하는 합니다. 이 방법을 사용 하면를 선택적으로 요소 중 일부의 투명도 변경할 수 있으며 요소를 사용 하 여 보다 성능상 이점이 <xref:System.Windows.UIElement.Opacity%2A> 속성입니다. 다음 예에서는 <xref:System.Windows.Media.Brush.Opacity%2A> 의 <xref:System.Windows.Media.SolidColorBrush> 단추의 그리는 데 사용 되는 <xref:System.Windows.Controls.Control.Background%2A> 로 설정 된 `0.25`합니다. 결과적으로, 브러시의 배경은 25% 않지만 해당 내용을 (단추의 텍스트) 100% 불투명 계속 있습니다.  
  
 [!code-xaml[brushsamples_snip#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#4)]  
  
 [!code-csharp[brushsamples_procedural_snip#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#4)]  
  
 브러시 내의 개별 색의 불투명도 제어할 수 있습니다. 색 및 브러시에 대 한 자세한 내용은 참조 [단색 및 그라데이션 개요 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)합니다. 불투명도 요소에 애니메이션을 적용 하는 방법을 보여 주는 예제를 참조 하십시오. [애니메이션의 요소 또는 브러시 불투명도](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-the-opacity-of-an-element-or-brush.md)합니다.
