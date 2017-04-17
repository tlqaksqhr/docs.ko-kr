---
title: "방법: 키 프레임을 사용하여 매트릭스에 애니메이션 효과 주기 | Microsoft Docs"
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
  - "애니메이션, 키 프레임으로 Matrix 속성"
  - "키 프레임, Matrix 속성에 애니메이션 적용"
  - "Matrix 속성, 키 프레임으로 애니메이션 적용"
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: 키 프레임을 사용하여 매트릭스에 애니메이션 효과 주기
이 예제에서는 키 프레임을 사용하여 <xref:System.Windows.Media.MatrixTransform>의 <xref:System.Windows.Media.MatrixTransform.Matrix%2A> 속성에 애니메이션 효과를 주는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> 클래스를 사용하여 <xref:System.Windows.Media.MatrixTransform>의 <xref:System.Windows.Media.MatrixTransform.Matrix%2A> 속성에 애니메이션 효과를 줍니다.  이 예제에서는 <xref:System.Windows.Media.MatrixTransform> 개체를 사용하여 <xref:System.Windows.Controls.Button>의 모양과 위치를 변경합니다.  
  
 이 애니메이션은 <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> 클래스를 사용하여 키 프레임 두 개를 만든 후 다음과 같은 작업을 수행합니다.  
  
1.  처음 0.2초 동안 첫 번째 <xref:System.Windows.Media.Matrix>에 애니메이션 효과를 줍니다.  이 예제에서는 <xref:System.Windows.Media.Matrix>의 <xref:System.Windows.Media.Matrix.M11%2A> 및 <xref:System.Windows.Media.Matrix.M12%2A> 속성을 변경합니다.  이렇게 하면 단추가 늘어나고 기울어집니다.  이 예제에서는 <xref:System.Windows.Media.Matrix.OffsetX%2A> 및 <xref:System.Windows.Media.Matrix.OffsetY%2A> 속성도 변경하여 단추의 위치도 변경합니다.  
  
2.  1.0초 지점에서 두 번째 <xref:System.Windows.Media.Matrix>에 애니메이션 효과를 줍니다.  단추가 더 이상 늘어나거나 기울어지지 않고 다른 위치로 이동합니다.  
  
3.  애니메이션을 무한 반복합니다.  
  
> [!NOTE]
>  <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> 개체에서 파생된 키 프레임에서는 값 간에 급격한 점프 효과를 만듭니다. 즉, 애니메이션이 급격하게 움직입니다.  
  
 [!code-xml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 전체 샘플을 보려면 [KeyFrame Animation 샘플](http://go.microsoft.com/fwlink/?LinkID=160012)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Media.MatrixTransform.Matrix%2A>   
 <xref:System.Windows.Media.MatrixTransform>   
 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [키 프레임 애니메이션 방법 항목](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)