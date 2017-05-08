---
title: "방법: 텍스트에 애니메이션 적용 | Microsoft Docs"
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
  - "애니메이션, 텍스트"
  - "입력 체계, 애니메이션"
ms.assetid: eec3d26c-0a21-420f-8012-671621c47089
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: 텍스트에 애니메이션 적용
애니메이션은 응용 프로그램에서 텍스트의 표시 및 모양을 변경할 수 있습니다.  다음 예제에서는 다양한 애니메이션 형식을 사용하여 <xref:System.Windows.Controls.TextBlock> 컨트롤에서의 텍스트 표시 방식에 영향을 줍니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimation>을 사용하여 텍스트 블록의 너비에 애니메이션 효과를 줍니다.  너비 값이 10초의 지속 시간 동안 텍스트 블록의 너비에서 0으로 변경된 다음 너비 값을 반대로 바꾸고 계속됩니다.  이 애니메이션의 형식은 닦아내기 효과를 만듭니다.  
  
 [!code-xml[TextAnimationSample#TextAnimationSample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample1)]  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimation>을 사용하여 텍스트 블록의 불투명도에 애니메이션 효과를 줍니다.  불투명도 값이 5초의 지속 시간 동안 1.0에서 0으로 변경된 다음 불투명도 값을 반대로 바꾸고 계속됩니다.  
  
 [!code-xml[TextAnimationSample#TextAnimationSample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample2)]  
  
 다음 다이어그램에서는 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>에서 정의한 5초의 지속 시간 동안 불투명도를 `1.00`에서 `0.00`으로 변경하는 <xref:System.Windows.Controls.TextBlock> 컨트롤의 효과를 보여 줍니다.  
  
 ![불투명도가 1.00에서 0.00으로 바뀌는 텍스트](../../../../docs/framework/wpf/advanced/media/fadedtext01.png "FadedText01")  
불투명도가 1.00에서 0.00으로 바뀌는 텍스트  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.ColorAnimation>을 사용하여 텍스트 블록의 전경색에 애니메이션 효과를 줍니다.  전경색 값이 5초의 지속 시간 동안 한 색에서 두 번째 색으로 변경된 다음 색 값을 반대로 바꾸고 계속됩니다.  
  
 [!code-xml[TextAnimationSample#TextAnimationSample3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample3)]  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimation>을 사용하여 텍스트 블록을 회전합니다.  텍스트 블록은 20초의 지속 시간 동안 전체 회전을 수행한 다음 회전 반복을 계속합니다.  
  
 [!code-xml[TextAnimationSample#TextAnimationSample4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample4)]  
  
## 참고 항목  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)