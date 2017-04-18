---
title: "방법: Timeline을 자동으로 뒤집을지 여부 지정 | Microsoft Docs"
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
  - "Timeline의 AutoReverse 속성"
  - "Timeline, AutoReverse 속성"
ms.assetid: 1648dd90-1bee-409a-ac69-ac729867f557
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# 방법: Timeline을 자동으로 뒤집을지 여부 지정
Timeline의 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 속성은 Timeline을 앞으로 반복한 후 뒤로 재생할 것인지 여부를 결정합니다.  다음 예제에서는 지속 시간 및 대상 값이 동일하지만 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 설정은 서로 다른 여러 개의 애니메이션을 보여 줍니다.  <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 설정이 다를 경우 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 속성이 어떻게 작동하는지 보여 주기 위해 몇몇 애니메이션은 반복되도록 설정되어 있습니다.  마지막 애니메이션은 중첩된 Timeline에서 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 속성이 어떻게 작동하는지 보여 줍니다.  
  
## 예제  
 [!code-xml[timingbehaviors_snip#AutoReverseAndRepeatBehaviorExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AutoReverseExample.xaml#autoreverseandrepeatbehaviorexamplewholepage)]