---
title: "방법: From, To 및 By를 사용하여 애니메이션 제어"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], From/to/by
- basic animation [WPF]
- animation [WPF], basic animation
- From/to/by animation
ms.assetid: 59afba57-6fc1-44c8-987e-8a5f4142adad
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: aab775ab1c2f55d79da0773f81c006015c349f8b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-control-an-animation-using-from-to-and-by"></a>방법: From, To 및 By를 사용하여 애니메이션 제어
"From/하/By" 또는 "기본 애니메이션" 두 대상 값 사이의 전환을 만듭니다 (참조 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) 다양 한 유형의 애니메이션에 대 한 소개). 기본 애니메이션의 대상 값을 설정 하려면 해당 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, 및 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성입니다.  다음 표에서 요약 방법을 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, 및 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성을 함께 사용할 수 있습니다. 또는 개별적으로 애니메이션의 대상 값을 확인 하 합니다.  
  
|지정된 속성|결과 동작|  
|--------------------------|------------------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>|에 지정 된 값은 애니메이션이 적용 된 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 애니메이션 효과 줄 속성의 기준 값 또는 이전 애니메이션 속성의 구성 방식에 따라 값을 출력 합니다.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 및 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|에 지정 된 값은 애니메이션이 적용 된 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성에 지정 된 값을는 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성입니다.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 및 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|에 지정 된 값은 애니메이션이 적용 된 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성에 의해 지정 된 값을는 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 및 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성입니다.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|속성의 기준 값에서 진행 되는 애니메이션 또는 이전 애니메이션의 출력 값으로 지정 된 값으로는 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성입니다.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|애니메이션 효과 줄 속성의 기본값은 애니메이션이 적용 또는 이전 애니메이션의 출력에 지정 된 값과 값의 합계를 구할 값은 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성입니다.|  
  
> [!NOTE]
>  둘 다 설정 하지 않으면는 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성 및 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 동일한 애니메이션 속성입니다.  
  
 다른 보간 방법을 사용하거나 둘 이상의 대상 값 사이에 애니메이션 효과를 주려면 키 프레임 애니메이션을 사용합니다. 참조 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md) 자세한 정보에 대 한 합니다.  
  
 단일 속성에 여러 애니메이션을 적용 하는 방법에 대 한 내용은 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)합니다.  
  
 다음 예제에서는 다양 한 설정의 효과 보여 줍니다. <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>, 및 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 애니메이션 속성입니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[BasicAnimations_snippet#AnimationTargetValuesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snippet/CS/AnimationTargetValuesExample.xaml#animationtargetvalueswholepage)]  
  
## <a name="see-also"></a>참고 항목  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [From, To 및 By 애니메이션 대상 값 샘플](http://go.microsoft.com/fwlink/?LinkID=159988)
