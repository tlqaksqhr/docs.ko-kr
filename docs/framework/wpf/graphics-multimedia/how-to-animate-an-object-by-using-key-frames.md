---
title: "방법: 키 프레임을 사용하여 개체에 애니메이션 효과 주기 | Microsoft Docs"
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
  - "애니메이션, 키 프레임으로 개체"
  - "키 프레임, 개체에 애니메이션 적용"
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: 키 프레임을 사용하여 개체에 애니메이션 효과 주기
이 예제에서는 개체에 애니메이션 효과를 주는 방법을 보여 줍니다. 여기에서는 키 프레임을 사용하여 <xref:System.Windows.Controls.Page> 컨트롤의 <xref:System.Windows.Controls.Page.Background%2A> 속성에 애니메이션 효과를 줍니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> 클래스를 사용하여 <xref:System.Windows.Controls.Page> 컨트롤의 <xref:System.Windows.Controls.Page.Background%2A> 속성에 색 변화 애니메이션 효과를 줍니다.  예제 애니메이션은 일정한 간격으로 배경 브러시를 변경합니다.  이 애니메이션은 <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> 클래스를 사용하여 세 가지 다른 키 프레임을 만듭니다.  이 애니메이션에서는 다음과 같은 방식으로 키 프레임을 사용합니다.  
  
1.  1초가 지난 후 <xref:System.Windows.Media.LinearGradientBrush> 클래스의 인스턴스에 애니메이션 효과를 적용합니다.  예제의 이 부분에서는 배경색에 선형 그라데이션을 적용하므로 색이 노란색에서 주황색에 이어 다시 빨간색으로 변합니다.  
  
2.  또 1초가 지난 후에는 <xref:System.Windows.Media.RadialGradientBrush> 클래스의 인스턴스에 애니메이션 효과를 적용합니다.  예제의 이 부분에서는 배경색에 방사형 그라데이션을 적용하므로 색이 흰색에서 파란색에 이어 다시 검은색으로 변합니다.  
  
3.  또 1초가 지난 후에는 <xref:System.Windows.Media.DrawingBrush> 클래스의 인스턴스에 애니메이션 효과를 적용합니다.  코드의 이 부분에서는 배경에 바둑판 모양의 패턴을 적용합니다.  
  
4.  애니메이션이 다시 시작되고 무한히 반복됩니다.  
  
> [!NOTE]
>  <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>은 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> 클래스와 함께 사용할 수 있는 유일한 키 프레임 형식입니다.  <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> 같은 키 프레임에서는 값을 갑자기 변경하므로 이 예제의 색 변화는 갑자기 이루어집니다.  
  
 [!code-xml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 전체 샘플을 보려면 [KeyFrame Animation 샘플](http://go.microsoft.com/fwlink/?LinkID=160012)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>   
 <xref:System.Windows.Controls.Page.Background%2A>   
 <xref:System.Windows.Controls.Page>   
 <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>   
 <xref:System.Windows.Media.LinearGradientBrush>   
 <xref:System.Windows.Media.RadialGradientBrush>   
 <xref:System.Windows.Media.DrawingBrush>   
 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [키 프레임 애니메이션 방법 항목](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)