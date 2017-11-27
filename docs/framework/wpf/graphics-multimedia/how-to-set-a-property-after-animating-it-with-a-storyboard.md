---
title: "방법: Storyboard를 사용하여 애니메이션 효과를 적용한 후 속성 설정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: animation [WPF], changing property values after
ms.assetid: 79466556-4dbf-40bd-9c1e-a77613b07077
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 357a9bb6c1a01b00e7f9bcfc17267797f20366b0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-a-property-after-animating-it-with-a-storyboard"></a>방법: Storyboard를 사용하여 애니메이션 효과를 적용한 후 속성 설정
일부 경우 애니메이션이 적용 된 후에 속성의 값을 변경할 수 나타날 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Windows.Media.Animation.Storyboard> 애니메이션의 색을 적용 하는 데 사용 되는 <xref:System.Windows.Media.SolidColorBrush>합니다. 스토리 보드는 단추를 클릭할 때 트리거됩니다. <xref:System.Windows.Media.Animation.Timeline.Completed> 는 프로그램이 알림을 받을 수 있도록 이벤트를 처리 때는 <xref:System.Windows.Media.Animation.ColorAnimation> 완료 합니다.  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton1Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton1declaration)]  
  
## <a name="example"></a>예제  
 이후에 <xref:System.Windows.Media.Animation.ColorAnimation> 완료 되 면 브러시의 색을 파란색을 변경 하려면 프로그램 시도 합니다.  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton1Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton1handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton1Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton1handler)]  
  
 이전 코드가 어떤 작업을 보이지 않으면: 번째 노란색, 브러시 남아 제공한는 <xref:System.Windows.Media.Animation.ColorAnimation> 작업도 합니다. 기본 속성 값 (기본값)은 실제로 파란색으로 변경 됩니다. 그러나 유효 또는 현재, 값은 노란색 때문에 <xref:System.Windows.Media.Animation.ColorAnimation> 여전히 기준 값을 재정의 합니다. 유효한 값을 다시 되도록 기준 값을 원하는 경우 속성에 영향을 주지 애니메이션을 중지 해야 합니다. 스토리 보드 애니메이션이 작업을 수행 하는 방법은 세 가지가 있습니다.  
  
-   애니메이션의 설정 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 속성을<xref:System.Windows.Media.Animation.FillBehavior.Stop>  
  
-   전체 스토리 보드를 제거 합니다.  
  
-   각 속성에서 애니메이션을 제거 합니다.  
  
## <a name="set-the-animations-fillbehavior-property-to-stop"></a>Stop으로 애니메이션의 FillBehavior 속성 설정  
 설정 하 여 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 를 <xref:System.Windows.Media.Animation.FillBehavior.Stop>을 활성 기간의 끝에 도달한 후 대상 속성에 영향을 주는 중지 된 애니메이션 합니다.  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton2Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton2declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton2Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton2handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton2Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton2handler)]  
  
## <a name="remove-the-entire-storyboard"></a>전체 스토리 보드를 제거 합니다.  
 사용 하 여 한 <xref:System.Windows.Media.Animation.RemoveStoryboard> 트리거 또는 <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType> 메서드를 스토리 보드 애니메이션의 대상 속성에 영향을 중지 하 게 지시 합니다. 이 접근 방식 및 설정 간의 차이 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 속성은 스토리 보드를 제거할 수 있습니다에 동안 언제 든 지는 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 속성에만 효과가 애니메이션 활성 기간의 끝에 도달 합니다.  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton3Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton3declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton3Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton3handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton3Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton3handler)]  
  
## <a name="remove-an-animation-from-an-individual-property"></a>개별 속성에서 애니메이션을 제거 합니다.  
 속성에 영향을 미치지 애니메이션을 중지 하는 다른 방법을 사용 하는 것은 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> 애니메이션 효과가 적용 되는 개체의 메서드. 첫 번째 매개 변수로 애니메이션 효과가 적용 되는 속성을 지정 하 고 `null` 를 두 번째입니다.  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton4Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton4declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton4Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton4handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton4Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton4handler)]  
  
 이 기술은 스토리 보드 비 애니메이션에 대 한 에서도 작동합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>  
 <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Media.Animation.RemoveStoryboard>  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [속성 애니메이션 기술 개요](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)
