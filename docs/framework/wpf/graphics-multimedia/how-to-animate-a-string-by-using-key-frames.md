---
title: "방법: 키 프레임을 사용하여 문자열에 애니메이션 효과 주기 | Microsoft Docs"
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
  - "애니메이션, 키 프레임으로 문자열"
  - "키 프레임, 문자열에 애니메이션 적용"
  - "문자열, 키 프레임으로 애니메이션 적용"
ms.assetid: c62bc9fd-c09a-4227-bce0-0a1ab82049dd
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: 키 프레임을 사용하여 문자열에 애니메이션 효과 주기
이 예제에서는 문자열에 애니메이션 효과를 주는 방법을 보여 줍니다. 여기에서는 키 프레임을 사용하여 <xref:System.Windows.Controls.Button> 컨트롤의 <xref:System.Windows.Controls.ContentControl.Content%2A> 속성에 애니메이션 효과를 줍니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> 클래스를 사용하여 <xref:System.Windows.Controls.Button>의 <xref:System.Windows.Controls.ContentControl.Content%2A> 속성에 애니메이션 효과를 줍니다.  
  
 키 프레임으로 만든 문자열 애니메이션은 불연속 키 프레임만 사용할 수 있으므로 이 예제의 모든 키 프레임은 <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> 클래스의 인스턴스를 사용합니다.  <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>과 같은 불연속 키 프레임에서는 값 간에 급격한 점프 효과를 만듭니다. 즉, 애니메이션이 눈에 띌 정도로 갑자기 변합니다.  
  
 [!code-xml[keyframes_snip#StringAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/StringAnimationUsingKeyFramesExample.xaml#stringanimationusingkeyframeswholepage)]  
  
 전체 샘플을 보려면 [KeyFrame Animation 샘플](http://go.microsoft.com/fwlink/?LinkID=160012)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>   
 <xref:System.Windows.Controls.ContentControl.Content%2A>   
 <xref:System.Windows.Controls.Button>   
 <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>   
 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [키 프레임 애니메이션 방법 항목](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)