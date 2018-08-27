---
title: '연습: Windows Forms에서 3-D WPF 복합 컨트롤 호스팅'
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
- composite controls [WPF], hosting WPF in
ms.assetid: 486369a9-606a-4a3b-b086-a06f2119c7b0
ms.openlocfilehash: b9642cec30c5e929102616577d9f2b1b2544c6d0
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932268"
---
# <a name="walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms"></a>연습: Windows Forms에서 3-D WPF 복합 컨트롤 호스팅

이 연습을 만드는 방법을 보여 줍니다.를 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 복합 제어 하 고 호스트에서 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤 및 사용 하 여 폼을 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤입니다.

이 연습에서는 상속을 구현 된 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> 두 자식 컨트롤이 들어 있는입니다. <xref:System.Windows.Controls.UserControl> 3 차원 (3-D) 원뿔을 표시 합니다. 3 차원 개체를 렌더링 하는 것은 훨씬 쉽게 통합할 합니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 보다 사용 하 여 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]입니다. 따라서 편이 호스트에는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> 클래스에서 3 차원 그래픽을 만들 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]합니다.

이 연습에서 설명하는 작업은 다음과 같습니다.

-   만들기는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>합니다.

-   Windows Forms 호스트 프로젝트를 만드는 중입니다.

-   호스팅하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>합니다.

## <a name="prerequisites"></a>전제 조건

이 연습을 완료하려면 다음 구성 요소가 필요합니다.

-   Visual Studio 2017

<a name="To_Create_the_UserControl"></a>
## <a name="create-the-usercontrol"></a>UserControl 만들기

1.  만들기는 **WPF 사용자 정의 컨트롤 라이브러리** 라는 프로젝트 `HostingWpfUserControlInWf`합니다.

2.  Usercontrol1.xaml이에서 엽니다는 [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]합니다.

3.  생성된 된 코드를 다음 코드로 바꿉니다.

     [!code-xaml[HostingWpfUserControlInWf#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]

     이 코드는 정의 <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> 두 자식 컨트롤이 들어 있는입니다. 첫 번째 자식 컨트롤은는 <xref:System.Windows.Controls.Label?displayProperty=nameWithType> ; 두 번째는는 <xref:System.Windows.Controls.Viewport3D> 3 차원 원뿔을 표시 하는 컨트롤입니다.

<a name="To_Create_the_Windows_Forms_Host_Project"></a>
## <a name="create-the-host-project"></a>호스트 프로젝트 만들기

1.  추가 된 **WPF 앱 (.NET Framework)** 라는 프로젝트 `WpfUserControlHost` 솔루션입니다. 자세한 내용은 [방법: 새 WPF 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82)를 참조하세요.

2.  **솔루션 탐색기**, WindowsFormsIntegration.dll 이라는 WindowsFormsIntegration 어셈블리에 대 한 참조를 추가 합니다.

3.  다음에 대 한 참조를 추가 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 어셈블리:

    -   PresentationCore

    -   PresentationFramework

    -   WindowsBase

4.  에 대 한 참조를 추가 합니다 `HostingWpfUserControlInWf` 프로젝트입니다.

5.  솔루션 탐색기에서 설정 된 `WpfUserControlHost` 프로젝트를 시작 프로젝트로 합니다.

<a name="To_Host_the_Windows_Presentation_Foundation"></a>
## <a name="host-the-usercontrol"></a>UserControl 호스트

1.  Windows Forms 디자이너에서 Form1을 엽니다.

2.  속성 창에서 클릭 **이벤트**를 차례로 두 번 클릭 합니다 <xref:System.Windows.Forms.Form.Load> 이벤트를 이벤트 처리기를 만듭니다.

     새로 생성 된 코드 편집기가 열립니다 `Form1_Load` 이벤트 처리기입니다.

3.  Form1.cs의 코드를 다음 코드로 바꿉니다.

     합니다 `Form1_Load` 이벤트 처리기의 인스턴스를 만듭니다 `UserControl1` 초기화를 추가 하 고는 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤의 자식 컨트롤 컬렉션입니다. <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤이 자식 컨트롤의 폼의 컬렉션에 추가 됩니다.

     [!code-csharp[HostingWpfUserControlInWf#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]

4.  **F5** 키를 눌러 응용 프로그램을 빌드하고 실행합니다.

## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [WPF 디자이너](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)
- [연습: Windows Forms에서 WPF 복합 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [연습: WPF에서 Windows Forms 복합 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Windows Forms 샘플에서 WPF 복합 컨트롤 호스팅](http://go.microsoft.com/fwlink/?LinkID=160001)