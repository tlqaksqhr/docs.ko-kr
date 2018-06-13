---
title: '방법: 해당 Timeline의 속도를 변경하지 않고 시계의 속도 변경'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- speed of Clock [WPF], changing
- clocks [WPF], changing speed of
ms.assetid: 72f36dd0-f085-445d-8589-19a83fe74f5e
ms.openlocfilehash: 126d260fbd59c1c35d8f56be6aa7dabe7688fa32
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556616"
---
# <a name="how-to-change-the-speed-of-a-clock-without-changing-the-speed-of-its-timeline"></a>방법: 해당 Timeline의 속도를 변경하지 않고 시계의 속도 변경
A <xref:System.Windows.Media.Animation.ClockController> 개체의 <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> 속성의 속도 변경 하면는 <xref:System.Windows.Media.Animation.Clock> 변경 하지 않고는 <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> 클록의의 <xref:System.Windows.Media.Animation.Timeline>합니다. 다음 예제에서는 <xref:System.Windows.Media.Animation.ClockController> 대화형으로 수정 하는 데 사용 되는 <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> 클록의 합니다. <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeedInvalidated> 이벤트와 클록의 <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeed%2A> 속성은 클록의 현재 글로벌 속도 표시 하는 데 사용 됩니다 대화형 때마다 <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> 변경 됩니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerSpeedRatioExample.cs#graphicsmmclockcontrollerspeedratioexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerspeedratioexample.vb#graphicsmmclockcontrollerspeedratioexample)]
