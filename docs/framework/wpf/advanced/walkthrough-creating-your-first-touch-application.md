---
title: '연습: 첫 응용 프로그램 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating a touch-sensitive application [WPF]
- touchscreen applications [WPF], creating
- touch-sensitive applications [WPF], creating
- creating a touchscreen application [WPF]
ms.assetid: d69e602e-9a25-4e24-950b-e89eaa2a906b
ms.openlocfilehash: 94a97c30179f7a8231426e31b8cacc364629ffc3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33548353"
---
# <a name="walkthrough-creating-your-first-touch-application"></a>연습: 첫 응용 프로그램 만들기
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 터치에 응답 하도록 응용 프로그램이 있습니다. 예를 들어 하나를 사용 하 여 응용 프로그램 상호 작용할 수 있습니다 또는 터치 지원 장치 등이 연습에서는 사용자가을 이동할 수 있도록 응용 프로그램을 만듭니다 터치 스크린에 손가락 크기 조정 또는 터치를 사용 하 여 단일 개체를 회전 합니다.  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vs_dev10_ext](../../../../includes/vs-dev10-ext-md.md)].  
  
-   Windows 7  
  
-   터치식 등을 지 원하는 Windows Touch 터치 스크린 입력을 허용 하는 장치입니다.  
  
 또한 응용 프로그램을 만들 하는 방법에 대 한 기본적인 이해 있어야 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 구독 하 고 이벤트를 처리 하는 방법에 특히 합니다. 자세한 내용은 참조 [연습: 내 첫 WPF 데스크톱 응용 프로그램](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)합니다.  
  
## <a name="creating-the-application"></a>응용 프로그램 작성  
  
#### <a name="to-create-the-application"></a>응용 프로그램을 만들려면  
  
1.  Visual Basic 또는 Visual C#에서 `BasicManipulation`이라는 새 WPF 응용 프로그램 프로젝트를 만듭니다. 자세한 내용은 [방법: 새 WPF 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82)를 참조하세요.  
  
2.  MainWindow.xaml의 내용을 다음 XAML로 바꿉니다.  
  
     이 태그는 빨강을 포함 하는 간단한 응용 프로그램을 만듭니다 <xref:System.Windows.Shapes.Rectangle> 에 <xref:System.Windows.Controls.Canvas>합니다. <xref:System.Windows.UIElement.IsManipulationEnabled%2A> 의 속성은 <xref:System.Windows.Shapes.Rectangle> 조작 이벤트를 받을 있도록 true로 설정 됩니다. 응용 프로그램 구독 하는 <xref:System.Windows.UIElement.ManipulationStarting>, <xref:System.Windows.UIElement.ManipulationDelta>, 및 <xref:System.Windows.UIElement.ManipulationInertiaStarting> 이벤트입니다. 이 이벤트는 논리를 포함할는 <xref:System.Windows.Shapes.Rectangle> 경우는 사용자가 조작할 합니다.  
  
     [!code-xaml[BasicManipulation#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml#ui)]  
  
3.  Visual Basic에서 MainWindow.xaml의 첫 번째 줄을 사용 하는 경우 대체 `x:Class="BasicManipulation.MainWindow"` 와 `x:Class="MainWindow"`합니다.  
  
4.  에 `MainWindow` 클래스, 다음 추가 <xref:System.Windows.UIElement.ManipulationStarting> 이벤트 처리기입니다.  
  
     <xref:System.Windows.UIElement.ManipulationStarting> 이벤트가 발생할 때 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 터치 검색 입력 개체를 조작 하기 시작 합니다. 코드는 조작의 위치에 상대적이 되도록 지정 된 <xref:System.Windows.Window> 설정 하 여는 <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A> 속성입니다.  
  
     [!code-csharp[BasicManipulation#ManipulationStarting](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationstarting)]
     [!code-vb[BasicManipulation#ManipulationStarting](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationstarting)]  
  
5.  에 `MainWindow` 클래스, 다음 추가 <xref:System.Windows.Input.ManipulationDelta> 이벤트 처리기입니다.  
  
     <xref:System.Windows.Input.ManipulationDelta> 터치 입력 위치를 변경 하 고 조작 하는 동안 여러 번 발생할 수 있는 이벤트가 발생 합니다. 이벤트를 손가락 발생 한 후에 발생할 수 있습니다. 예를 들어 사용자가 화면에서 손가락을 끌 경우는 <xref:System.Windows.Input.ManipulationDelta> 이벤트 손가락 이동으로 여러 번 발생 합니다. 사용자의 화면에서 손가락을 발생 시킬 때는 <xref:System.Windows.Input.ManipulationDelta> 관성을 시뮬레이션 하 이벤트가 계속 발생 합니다.  
  
     코드 적용는 <xref:System.Windows.Input.ManipulationDeltaEventArgs.DeltaManipulation%2A> 에 <xref:System.Windows.UIElement.RenderTransform%2A> 의 <xref:System.Windows.Shapes.Rectangle> 터치를 이동할 때 이동 하려면 다음을 입력 합니다. 또한 확인 여부는 <xref:System.Windows.Shapes.Rectangle> 의 경계를 벗어납니다는 <xref:System.Windows.Window> 관성 하는 동안 이벤트가 발생할 때. 응용 프로그램 호출에서 <xref:System.Windows.Input.ManipulationDeltaEventArgs.Complete%2A?displayProperty=nameWithType> 조작 발생 하 합니다.  
  
     [!code-csharp[BasicManipulation#ManipulationDelta](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationdelta)]
     [!code-vb[BasicManipulation#ManipulationDelta](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationdelta)]  
  
6.  에 `MainWindow` 클래스, 다음 추가 <xref:System.Windows.UIElement.ManipulationInertiaStarting> 이벤트 처리기입니다.  
  
     <xref:System.Windows.UIElement.ManipulationInertiaStarting> 사용자 화면에서 손가락을 모두 발생 하면 오류가 발생 합니다. 코드에는 초기 속도 이동, 확장 및 사각형의 회전에 대 한 선언을 설정합니다.  
  
     [!code-csharp[BasicManipulation#ManipulationInertiaStarting](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationinertiastarting)]
     [!code-vb[BasicManipulation#ManipulationInertiaStarting](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationinertiastarting)]  
  
7.  프로젝트를 빌드하고 실행합니다.  
  
     창에 나타나는 빨간색 사각형이 표시 됩니다.  
  
## <a name="testing-the-application"></a>응용 프로그램 테스트  
 응용 프로그램을 테스트 하려면 다음 조작을 시도 합니다. Note 동시에 다음 중 하나 이상 수행할 수 있습니다.  
  
-   이동 하는 <xref:System.Windows.Shapes.Rectangle>, 위에 손가락을 놓고는 <xref:System.Windows.Shapes.Rectangle> 화면에서 손가락을 이동 합니다.  
  
-   크기를 조정 하려면는 <xref:System.Windows.Shapes.Rectangle>에 두 손가락을 배치는 <xref:System.Windows.Shapes.Rectangle> 가까워지거나 함께 또는 서로 다른에서 멀리 손가락을 이동 합니다.  
  
-   회전 하려면는 <xref:System.Windows.Shapes.Rectangle>에 두 손가락을 배치는 <xref:System.Windows.Shapes.Rectangle> 서로 손가락의 회전 하 고 있습니다.  
  
 관성 시킬 신속 하 게 발생 화면에서 손가락 이전 조작을 수행 합니다. <xref:System.Windows.Shapes.Rectangle> 이동, 크기 조정 또는 회전 중지 하기 전에 몇 초 동안 계속 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.UIElement.ManipulationStarting?displayProperty=nameWithType>  
 <xref:System.Windows.UIElement.ManipulationDelta?displayProperty=nameWithType>  
 <xref:System.Windows.UIElement.ManipulationInertiaStarting?displayProperty=nameWithType>
