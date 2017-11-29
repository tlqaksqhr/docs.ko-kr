---
title: "방법: 텍스트에 애니메이션 적용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- typography [WPF], animations
- animation [WPF], text
ms.assetid: eec3d26c-0a21-420f-8012-671621c47089
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0298462db5897e955bf0a2551cca7fc81bb27d89
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-apply-animations-to-text"></a>방법: 텍스트에 애니메이션 적용
애니메이션은 응용 프로그램의 텍스트 모양과 표시를 변경할 수 있습니다. 다음 예에서는 다양 한 유형의 애니메이션의 텍스트 표시에 영향을 사용 하 여 한 <xref:System.Windows.Controls.TextBlock> 제어 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 한 <xref:System.Windows.Media.Animation.DoubleAnimation> 텍스트 블록의 너비를 애니메이션 효과를 주는 합니다. 10초 동안 너비 값을 텍스트 블록의 너비에서 0으로 변경한 후 다시 너비 값을 반대로 변경하여 계속합니다. 이러한 형식의 애니메이션은 지우기 효과를 생성합니다.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample1)]  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimation> 에 텍스트 블록의 불투명도 애니메이션을 적용 합니다. 5초 동안 불투명도 값을 1.0에서 0으로 변경한 다음 불투명 값을 반대로 변경하고 계속합니다.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample2)]  
  
 다음 다이어그램의 효과 보여 줍니다.는 <xref:System.Windows.Controls.TextBlock> 불투명도를 변경 하는 컨트롤 `1.00` 를 `0.00` 에 정의 된 5 초 간격 동안는 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>합니다.  
  
 ![불투명도 1.00에서 0.00으로 바뀌는 텍스트](../../../../docs/framework/wpf/advanced/media/fadedtext01.png "FadedText01")  
1.00에서 0.00으로 변경하는 텍스트 불투명도  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.ColorAnimation> 에 텍스트 블록의 전경 색 애니메이션을 적용 합니다. 전경색 값을 5초 동안 한 색상에서 두 번째 색상으로 변경한 다음 색상 값을 반대로 변경하고 계속합니다.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample3)]  
  
 다음 예제에서는 한 <xref:System.Windows.Media.Animation.DoubleAnimation> 텍스트 블록을 회전 합니다. 텍스트 블록은 20초 동안 전체 회전을 수행한 다음 회전을 계속 반복합니다.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample4)]  
  
## <a name="see-also"></a>참고 항목  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
