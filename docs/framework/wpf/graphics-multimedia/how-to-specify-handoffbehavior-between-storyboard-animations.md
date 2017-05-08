---
title: "방법: Storyboard 애니메이션 간의 HandoffBehavior 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "애니메이션, 전달 동작"
  - "스토리보드, 애니메이션 간의 전달 동작"
ms.assetid: 97bd6842-929b-49d9-813e-46553ae46472
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: Storyboard 애니메이션 간의 HandoffBehavior 지정
이 예제에서는 Storyboard 애니메이션 간의 전달 동작을 지정하는 방법을 보여 줍니다.  <xref:System.Windows.Media.Animation.BeginStoryboard>의 <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> 속성은 새 애니메이션이 이미 속성에 적용되어 있는 기존 애니메이션과 상호 작용하는 방식을 지정합니다.  
  
## 예제  
 다음 예제에서는 마우스 커서를 단추 위로 이동하면 커지고 커서를 단추 바깥쪽으로 이동하면 작아지는 단추 두 개를 만듭니다.  마우스 커서를 단추 위로 이동했다가 재빠르게 치우면 첫 번째 애니메이션이 완료되기 전에 두 번째 애니메이션이 적용됩니다.  이렇게 두 애니메이션이 겹칠 때 <xref:System.Windows.Media.Animation.HandoffBehavior> 및 <xref:System.Windows.Media.Animation.HandoffBehavior>의 <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> 값의 차이를 확인할 수 있습니다.  <xref:System.Windows.Media.Animation.HandoffBehavior> 값은 겹치는 애니메이션을 결합하여 애니메이션 간의 전환을 더 부드럽게 만들지만 <xref:System.Windows.Media.Animation.HandoffBehavior> 값은 새 애니메이션이 겹치는 이전 애니메이션을 즉시 교체하도록 합니다.  
  
 [!code-xml[timingbehaviors_snip#HandoffBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/HandoffBehaviorExample.xaml#handoffbehaviorwholepage)]  
  
## 참고 항목  
 <xref:System.Windows.Media.Animation.BeginStoryboard>   
 <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>   
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Animation and Timing](http://msdn.microsoft.com/ko-kr/7d83765b-d5ae-41b1-b423-80206e1124aa)   
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)