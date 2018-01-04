---
title: "방법: 대화형으로 Clock 제어"
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
helpviewer_keywords:
- controlling clocks interactively [WPF]
- clocks [WPF], controlling interactively
ms.assetid: d0b520e0-2f18-4cef-977f-2909e709548a
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d24a5154607bf535cbf995705332092bb86ca02e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-interactively-control-a-clock"></a>방법: 대화형으로 Clock 제어
A <xref:System.Windows.Media.Animation.Clock> 개체의 <xref:System.Windows.Media.Animation.ClockController> 속성을 사용 하면 대화형으로 시작, 일시 중지, 다시 시작, 검색, 시계를 해당 전체 기간 이동 및 시계를 중지 합니다. 시간 트리의 루트 클록만을 대화형으로 제어할 수 있습니다.  
  
> [!NOTE]
>  다른 여러 가지를 대화형으로 제어 하지 않고 애니메이션을 시계와 직접 협업할 수 있습니다: 스토리 보드를 사용할 수도 있습니다. 스토리 보드는 태그와 코드에서 지원 됩니다. 예를 들어 참조 [속성 스토리 보드를 사용 하 여 애니메이션을 적용](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md) 또는 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)합니다.  
  
 다음 예제에서는 여러 단추는 애니메이션 클록을 대화형으로 제어를 사용 됩니다.  
  
## <a name="example"></a>예  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerExample.cs#graphicsmmclockcontrollerexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerexample.vb#graphicsmmclockcontrollerexample)]  
  
## <a name="see-also"></a>참고 항목  
 [Storyboard를 사용하여 속성에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
