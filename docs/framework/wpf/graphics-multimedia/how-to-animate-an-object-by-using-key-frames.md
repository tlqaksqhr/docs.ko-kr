---
title: "방법: 키 프레임을 사용하여 개체에 애니메이션 효과 주기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 71feb0ecef7a6356c95b843fbc2657ad2e4a7996
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a>방법: 키 프레임을 사용하여 개체에 애니메이션 효과 주기
이 예제는 개체에 애니메이션을 적용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Page.Background%2A> 속성은 <xref:System.Windows.Controls.Page> 키 프레임을 사용 하 여 제어 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> 색 애니메이션 효과를 클래스에 대 한 변경의 <xref:System.Windows.Controls.Page.Background%2A> 속성의는 <xref:System.Windows.Controls.Page> 제어 합니다. 예제 애니메이션 배경 브러시를 정기적으로 변경합니다. 이 애니메이션에 사용 하 여는 <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> 클래스 세 개의 서로 다른 키 프레임을 만듭니다. 애니메이션 키 프레임을 사용 하 여 다음과 같은 방식:  
  
1.  애니메이션 효과 인스턴스의 첫 번째 초 후에는 <xref:System.Windows.Media.LinearGradientBrush> 클래스입니다. 예제의이 섹션에서는 색을 빨간색 주황색 노랑에서 전환 되도록 배경색에 선형 그라데이션으로 표시할 적용 됩니다.  
  
2.  애니메이션 효과의 인스턴스를 완료 한 다음 초에는 <xref:System.Windows.Media.RadialGradientBrush> 클래스입니다. 예제의이 섹션은 방사형 그라데이션 배경색으로 적용 하므로 색을 검정으로 파란색 흰색에서 전환 합니다.  
  
3.  애니메이션 효과의 인스턴스 세 번째 초 후에는 <xref:System.Windows.Media.DrawingBrush> 클래스입니다. 예제의이 섹션에서는 백그라운드에 체크 무늬 패턴을 적용합니다.  
  
4.  애니메이션 다시 시작 되 고 무한 반복 합니다.  
  
> [!NOTE]
>  <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>함께 사용할 수 있는 키 프레임의 유일한 종류는 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> 클래스입니다. 같은 키 프레임 <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> 즉에서 값을 급격 한 변경과 만들고,이 예에서 색 변경 갑자기 이루어집니다.  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 전체 샘플을 보려면 [키 프레임 애니메이션 샘플](http://go.microsoft.com/fwlink/?LinkID=160012)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>  
 <xref:System.Windows.Controls.Page.Background%2A>  
 <xref:System.Windows.Controls.Page>  
 <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>  
 <xref:System.Windows.Media.LinearGradientBrush>  
 <xref:System.Windows.Media.RadialGradientBrush>  
 <xref:System.Windows.Media.DrawingBrush>  
 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [키 프레임 방법 항목](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
