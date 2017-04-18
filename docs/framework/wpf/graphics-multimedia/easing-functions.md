---
title: "감속/가속 함수 | Microsoft Docs"
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
  - "애니메이션에 수학 공식 적용[WPF]"
  - "애니메이션에 감속/가속 함수 적용[WPF]"
  - "애니메이션에 적용 수학 공식 [WPF]"
  - "실제와 같은 움직임 애니메이션 [WPF]"
  - "감속/가속 함수[WPF]"
  - "감속/가속 함수 사용자 지정[WPF]"
  - "정의 감속/가속 함수 [WPF]"
  - "사용자 지정 감속/가속 함수 [WPF]"
  - "적용 되는 애니메이션 [WPF]"
ms.assetid: 075b9c2b-82c4-43fa-b3cd-de0b6236eb38
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 감속/가속 함수
감속/가속 함수에는 사용자 지정 수식을 애니메이션을 적용할 수 있습니다. 예를 들어 사실적으로 바운스 하거나 스프링에 있는 것 처럼 개체를 좋습니다. 이러한 효과 모방할에 From/To/By 애니메이션 또는 키 프레임을 사용할 수 있고 상당한 양의 작업을 걸리는 애니메이션 수학 수식을 사용 하 여 보다 덜 정확할 수는 합니다.  
  
 상속 하 여 사용자 고유의 사용자 지정 감속/가속 함수를 만들 뿐 아니라 <xref:System.Windows.Media.Animation.EasingFunctionBase>, 런타임에서 제공 하는 여러 감속/가속 함수 중 하나를 사용 하 여 일반적인 효과 만들 수 있습니다.  
  
-   <xref:System.Windows.Media.Animation.BackEase>: 표시 된 경로에 애니메이션 효과를 시작 하기 전에 약간 애니메이션 동작을 제거 합니다.  
  
-   <xref:System.Windows.Media.Animation.BounceEase>: 바운스 효과 만듭니다.  
  
-   <xref:System.Windows.Media.Animation.CircleEase>: 애니메이션 가속 및/또는 순환 함수를 사용 하 여 감속을 만듭니다.  
  
-   <xref:System.Windows.Media.Animation.CubicEase>: 애니메이션 가속 및/또는 수식을 사용 하 여 감속을 만듭니다 *f*( *t*) = *t*<sup>3</sup>합니다.  
  
-   <xref:System.Windows.Media.Animation.ElasticEase>: 앞뒤로 정지할 될 때까지 spring 유사한는 애니메이션을 만듭니다.  
  
-   <xref:System.Windows.Media.Animation.ExponentialEase>: 애니메이션 가속 및/또는 지 수 수식을 사용 하 여 감속을 만듭니다.  
  
-   <xref:System.Windows.Media.Animation.PowerEase>: 애니메이션 가속 및/또는 수식을 사용 하 여 감속을 만듭니다 *f*( *t*) = *t*<sup>p</sup> 여기서 p는 같지는 <xref:System.Windows.Media.Animation.PowerEase.Power%2A> 속성입니다.  
  
-   <xref:System.Windows.Media.Animation.QuadraticEase>: 애니메이션 가속 및/또는 수식을 사용 하 여 감속을 만듭니다 *f*( *t*) = *t*<sup>2</sup>합니다.  
  
-   <xref:System.Windows.Media.Animation.QuarticEase>: 애니메이션 가속 및/또는 수식을 사용 하 여 감속을 만듭니다 *f*( *t*) = *t*<sup>4</sup>합니다.  
  
-   <xref:System.Windows.Media.Animation.QuinticEase>: 애니메이션 가속 및/또는 수식을 사용 하 여 감속을 만들 *f*( *t*) = *t*<sup>5</sup>합니다.  
  
-   <xref:System.Windows.Media.Animation.SineEase>: 애니메이션 가속 및/또는 사인 수식을 사용 하 여 감속을 만듭니다.  
  
 다음 샘플에서 이러한 감속/가속 함수 동작을 탐색할 수 있습니다.  
  
 [이 샘플을 실행 합니다.](http://go.microsoft.com/fwlink/?LinkId=139798&sref=easing_functions_gallery)  
  
 애니메이션에 감속/가속 함수를 적용 하려면 사용 된 `EasingFunction` 애니메이션의 속성에 애니메이션을 적용할 감속/가속 함수를 지정 합니다. 다음 예제에서는 적용는 <xref:System.Windows.Media.Animation.BounceEase> 감속/가속 함수에는 <xref:System.Windows.Media.Animation.DoubleAnimation> 바운스되 효과를 만듭니다.  
  
 [이 샘플을 실행 합니다.](http://go.microsoft.com/fwlink/?LinkId=139798&sref=BounceEase)  
  
 [!code-xml[BounceEase_snippet#BounceEase](../../../../samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 이전 예제에서는 감속/가속 함수 적용할 From/To/By 애니메이션 합니다. 키 프레임 애니메이션에 감속/가속 함수를 적용할 수도 있습니다. 다음 예제에서는 계약 위로 느려 다음 확장 아래로 (떨어지는 것 처럼) 및 중지 하기 반송 다음 여부를 지정 하는 사각형의 애니메이션을 만드는 감속/가속 함수 연관 된 키 프레임을 사용 하는 방법을 보여 줍니다.  
  
 [이 샘플을 실행 합니다.](http://go.microsoft.com/fwlink/?LinkId=139798&sref=EasingFunctionDoubleKeyFrame)  
  
 [!code-xml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](../../../../samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 사용할 수는 <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> 즉, 감속/가속 함수 동작 방식을 변경 하는 속성 애니메이션 보간 방법을 변경 합니다. 제공할 수 있는 세 가지 가능한 값은 <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:  
  
-   <xref:System.Windows.Media.Animation.EasingMode>: 보간 감속/가속 함수에 연결 된 수학 공식을 따릅니다.  
  
-   <xref:System.Windows.Media.Animation.EasingMode>: 보간에서 감속/가속 함수에 연결 된 식의 결과 뺀 값 100% 보간입니다.  
  
-   <xref:System.Windows.Media.Animation.EasingMode>: 보간을 사용 하 여 <xref:System.Windows.Media.Animation.EasingMode> 애니메이션의 첫 번째 절반에 대 한 및 <xref:System.Windows.Media.Animation.EasingMode> 하반기에 있습니다.  
  
 다음 그래프의 다른 값을 보여 줍니다. <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> 여기서 *f*( *x*)에서는 및 *t* 시간을 나타냅니다.  
  
 <xref:System.Windows.Media.Animation.BackEase>  
  
 ![BackEase EasingMode 그래프 ] (../Image/BackEase_Graph.png "BackEase_Graph")  
  
 <xref:System.Windows.Media.Animation.BounceEase>  
  
 ![BounceEase EasingMode 그래프 ] (../Image/BounceEase_Graph.png "BounceEase_Graph")  
  
 <xref:System.Windows.Media.Animation.CircleEase>  
  
 ![CircleEase EasingMode 그래프 ] (../Image/CircleEase_Graph.png "CircleEase_Graph")  
  
 <xref:System.Windows.Media.Animation.CubicEase>  
  
 ![CubicEase EasingMode 그래프 ] (../Image/CubicEase_Graph.png "CubicEase_Graph")  
  
 <xref:System.Windows.Media.Animation.ElasticEase>  
  
 ![다양 한 easingmode 그래프로 나타낸 ElasticEase ] (../Image/ElasticEase_Graph.png "ElasticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.ExponentialEase>  
  
 ![다양 한 easingmode 그래프로 나타낸 ExponentialEase 합니다. ] (../Image/ExponentialEase_Graph.png "ExponentialEase_Graph")  
  
 <xref:System.Windows.Media.Animation.PowerEase>  
  
 ![다양 한 easingmode 그래프로 나타낸 QuarticEase ] (../Image/QuarticEase_Graph.png "QuarticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuadraticEase>  
  
 ![다양 한 easingmode 그래프로 나타낸 QuadraticEase](../../../../docs/framework/wpf/graphics-multimedia/media/quadraticease-graph.png "QuadraticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuarticEase>  
  
 ![다양 한 easingmode 그래프로 나타낸 QuarticEase ] (../Image/QuarticEase_Graph.png "QuarticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuinticEase>  
  
 ![다양 한 easingmode 그래프로 나타낸 QuinticEase ] (../Image/QuinticEase_Graph.png "QuinticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.SineEase>  
  
 ![다양 한 EasingMode 값의 SineEase](../../../../docs/framework/wpf/graphics-multimedia/media/sineease-graph.png "SineEase_Graph")  
  
> [!NOTE]
>  사용할 수 있습니다 <xref:System.Windows.Media.Animation.PowerEase> 동일한 동작을 만들려면 <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, 및 <xref:System.Windows.Media.Animation.QuinticEase> 를 사용 하 여는 <xref:System.Windows.Media.Animation.PowerEase.Power%2A> 속성입니다. 예를 들어 사용 하려는 경우 <xref:System.Windows.Media.Animation.PowerEase> 대신 <xref:System.Windows.Media.Animation.CubicEase>, 지정는 <xref:System.Windows.Media.Animation.PowerEase.Power%2A> 값 3입니다.  
  
 실행 시간에 포함 된 감속/가속 함수를 사용 하는 것 외에도 사용자 지정 감속/가속 함수에서 상속 하 여 만들 수 있습니다 <xref:System.Windows.Media.Animation.EasingFunctionBase>합니다. 다음 예제에서는 간단한 사용자 지정 감속/가속 함수를 만드는 방법을 보여 줍니다. 감속/가속 함수를 재정의 하 여 작동 하는 방법에 대 한 고유한 수학적 논리를 추가할 수는 <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> 메서드.  
  
 [이 샘플을 실행 합니다.](http://go.microsoft.com/fwlink/?LinkId=139798&sref=CustomEasingFunction)  
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xml[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]