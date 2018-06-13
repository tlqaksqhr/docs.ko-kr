---
title: '방법: Storyboard를 시작한 후 이벤트 트리거를 사용하여 제어'
ms.date: 03/30/2017
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
ms.openlocfilehash: c864668026c4f8bb58a4d6c4c36f96fb07445a9d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561296"
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a>방법: Storyboard를 시작한 후 이벤트 트리거를 사용하여 제어
제어 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Animation.Storyboard> 시작 된 후입니다. 시작 하려면는 <xref:System.Windows.Media.Animation.Storyboard> 를 사용 하 여 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]를 사용 하 여 <xref:System.Windows.Media.Animation.BeginStoryboard>, 개체 및 애니메이션 효과 적용 하며 다음 스토리 보드를 시작 하는 속성에 애니메이션을 배포한입니다. 제공 하는 경우 <xref:System.Windows.Media.Animation.BeginStoryboard> 이름을 지정 하 여 해당 <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> 속성 되도록 하 여 제어할 수 있는 스토리 보드 합니다. 제어할 수 있습니다 다음 대화형으로 스토리 보드 시작 된 후.  
  
 와 함께 다음 스토리 보드 작업을 사용 하 여 <xref:System.Windows.EventTrigger> 스토리 보드를 제어 하는 개체입니다.  
  
-   <xref:System.Windows.Media.Animation.PauseStoryboard>: 스토리 보드를 일시 중지 됩니다.  
  
-   <xref:System.Windows.Media.Animation.ResumeStoryboard>: 일시 중지 된 스토리 보드를 다시 시작합니다.  
  
-   <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: 스토리 보드 속도 변경합니다.  
  
-   <xref:System.Windows.Media.Animation.SkipStoryboardToFill>: 있는 경우 채우기 기간의 끝에 스토리 보드를 진행 합니다.  
  
-   <xref:System.Windows.Media.Animation.StopStoryboard>: 스토리 보드를 중지합니다.  
  
-   <xref:System.Windows.Media.Animation.RemoveStoryboard>: 리소스를 확보 스토리 보드를 제거 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 스토리 보드를 대화형으로 제어 제어할 수 있는 스토리 보드 작업을 사용 합니다.  
  
 **참고:** 코드를 사용 하 여 스토리 보드 제어의 예를 보려면 [한 스토리 보드 후 것 시작를 사용 하 여 해당 대화형 방법을 제어할](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md)합니다.  
  
 [!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]  
  
 추가 예제에 대 한 참조는 [애니메이션 예제 갤러리](http://go.microsoft.com/fwlink/?LinkID=159969)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.Animation.ResumeStoryboard>  
 <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>  
 <xref:System.Windows.Media.Animation.SkipStoryboardToFill>  
 <xref:System.Windows.Media.Animation.PauseStoryboard>  
 <xref:System.Windows.Media.Animation.StopStoryboard>  
 <xref:System.Windows.Media.Animation.SeekStoryboard>  
 [대화형 메서드를 사용하여 이미 시작된 Storyboard 제어](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md)  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Storyboard 개요](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
