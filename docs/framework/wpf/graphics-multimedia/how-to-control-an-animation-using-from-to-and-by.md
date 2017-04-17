---
title: "방법: From, To 및 By를 사용하여 애니메이션 제어 | Microsoft Docs"
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
  - "애니메이션에서 / 에/에서"
  - "기본 애니메이션"
  - "애니메이션, 기본적인 애니메이션"
  - "From/To/By 애니메이션"
ms.assetid: 59afba57-6fc1-44c8-987e-8a5f4142adad
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: From, To 및 By를 사용하여 애니메이션 제어
"From/To/By" 또는 "기본 애니메이션"은 두 개의 대상 값 사이의 전환을 만듭니다 (참조 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) 다양 한 유형의 애니메이션에 대 한 소개). 기본 애니메이션의 대상 값을 설정 하려면 해당 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, 및 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성입니다.  다음 표에 요약 되어 방법을 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, 및 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 별도로 애니메이션의 대상 값을 확인 하 또는 속성을 함께 사용할 수 있습니다.  
  
|지정 된 속성|결과 동작|  
|--------------------------|------------------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>|에 지정 된 값은 애니메이션이 적용 된 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 되는 속성의 기준 값 또는 이전 애니메이션 속성의 구성 방식에 따라 값을 출력 합니다.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> and                              <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|에 지정 된 값은 애니메이션이 적용 된 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성에 지정 된 값을는 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> and                              <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|에 지정 된 값은 애니메이션이 적용 된 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성에 의해 지정 된 값을는 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 및 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|속성의 기본 값에서 진행 되는 애니메이션 또는 이전 애니메이션의 값에 지정 된 값을 출력에서 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성입니다.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|출력에 지정 된 값과 값의 합계 값은 애니메이션이 적용 되는 속성의 기준 값 이나 이전 애니메이션의 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성입니다.|  
  
> [!NOTE]
>  둘 다 설정 하지 않으면는 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성 및 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 동일한 애니메이션 속성입니다.  
  
 다른 보간 메서드를 사용 하거나 두 개 이상의 대상 값 사이 애니메이션을 적용 하려면 키 프레임 애니메이션을 사용 합니다. 참조 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md) 에 대 한 자세한 내용은 합니다.  
  
 단일 속성에 여러 애니메이션을 적용 하는 방법에 대 한 정보를 참조 하십시오. [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)합니다.  
  
 아래 예제에서는 다양 한 설정의 효과 보여 줍니다. <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>, 및 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 애니메이션 속성입니다.  
  
## <a name="example"></a>예제  
 [!code-xml[BasicAnimations_snippet#AnimationTargetValuesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snippet/CS/AnimationTargetValuesExample.xaml#animationtargetvalueswholepage)]  
  
## <a name="see-also"></a>참고 항목  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [From, To 및 애니메이션 대상 값 샘플](http://go.microsoft.com/fwlink/?LinkID=159988)