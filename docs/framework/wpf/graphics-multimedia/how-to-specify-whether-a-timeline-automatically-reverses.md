---
title: "방법: Timeline을 자동으로 뒤집을지 여부 지정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- AutoReverse property of timelines [WPF]
- Timelines [WPF], AutoReverse property
ms.assetid: 1648dd90-1bee-409a-ac69-ac729867f557
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2abce54905f0bb06bf983c065e064ce2dfeba932
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-specify-whether-a-timeline-automatically-reverses"></a>방법: Timeline을 자동으로 뒤집을지 여부 지정
타임 라인의 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 속성을 정방향으로 반복을 완료 한 후 반대 방향으로 재생 있는지 여부를 결정 합니다. 다음 예에서는 동일한 기간 및 대상 값을 사용 하지만 서로 다른 여러 애니메이션 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 설정 합니다. 설명 하기 위해 방법을 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 속성 서로 다른 동작 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 설정, 일부 애니메이션 반복으로 설정 됩니다. 애니메이션에 마지막 표시 된 방법을 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 속성은 중첩 된 타임 라인에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[timingbehaviors_snip#AutoReverseAndRepeatBehaviorExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AutoReverseExample.xaml#autoreverseandrepeatbehaviorexamplewholepage)]
