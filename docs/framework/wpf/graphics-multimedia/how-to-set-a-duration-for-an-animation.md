---
title: '방법: 애니메이션의 지속 시간 설정'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], duration
- Timelines [WPF], description
- duration of animations [WPF]
ms.assetid: 155034ef-7d00-4416-a73c-b1713992d2eb
ms.openlocfilehash: df9e12e1bd3a365c3013d0f75df663bd46186ee2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-set-a-duration-for-an-animation"></a>방법: 애니메이션의 지속 시간 설정
A <xref:System.Windows.Media.Animation.Timeline> 시간을 세그먼트와 해당 세그먼트의 길이 따라 사용자가 타임 라인의 나타냅니다 <xref:System.Windows.Duration>합니다. 경우는 <xref:System.Windows.Media.Animation.Timeline> 끝에 도달한 기간의 해당 재생이 중지 합니다. 경우는 <xref:System.Windows.Media.Animation.Timeline> 자식 타임 라인에도 재생을 중지 합니다. 애니메이션의 경우는 <xref:System.Windows.Duration> 애니메이션의 소요 시간 전환의 시작 값 끝 값을 지정 합니다.  
  
 지정할 수는 <xref:System.Windows.Duration> 제한 된 특정 시간 또는 특수 한 값을 가진 <xref:System.Windows.Duration.Automatic%2A> 또는 <xref:System.Windows.Duration.Forever%2A>합니다. 애니메이션 항상 정의 된, 유한 길이 있어야 하기 때문에 애니메이션의 지속 시간 값을 항상 이어야 합니다-애니메이션 시간은 대상 값을 인식 하지 못하기 그렇지 않은 경우. 컨테이너 타임 라인 (<xref:System.Windows.Media.Animation.TimelineGroup> 개체), 같은 <xref:System.Windows.Media.Animation.Storyboard> 및 <xref:System.Windows.Media.Animation.ParallelTimeline>의 지속 시간 기본값 <xref:System.Windows.Duration.Automatic%2A>, 즉, 마지막 자식 해당 재생이 중지 되 면 자동으로 종료 합니다.  
  
 다음 예제에서는, 너비, 높이 및 채우기 색에는 <xref:System.Windows.Shapes.Rectangle> 애니메이션 효과가 적용 됩니다. 애니메이션의 인지 된 속도 제어 하 고 재정의 컨테이너 타임 라인의 기간으로 자식 타임 라인의 기간을 포함 하 여 애니메이션 효과 애니메이션 및 컨테이너 타임 라인 기간이 설정 됩니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[timingbehaviors_snip#DurationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/DurationExample.xaml#durationexamplewholepage)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Duration>  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
