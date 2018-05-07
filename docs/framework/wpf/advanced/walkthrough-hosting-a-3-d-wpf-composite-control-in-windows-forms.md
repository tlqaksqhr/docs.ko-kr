---
title: '연습: Windows Forms에서 3-D WPF 복합 컨트롤 호스팅'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
- composite controls [WPF], hosting WPF in
ms.assetid: 486369a9-606a-4a3b-b086-a06f2119c7b0
ms.openlocfilehash: a9aca5d1aff1057d85509be517bb352b4b27bf9f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms"></a>연습: Windows Forms에서 3-D WPF 복합 컨트롤 호스팅
이 연습에서는 어떻게 만들 수는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 복합 제어 하 고 호스트에서 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤 및 폼을 사용 하 여는 <xref:System.Windows.Forms.Integration.ElementHost> 제어 합니다.  
  
 이 연습에서는 구현는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> 두 개의 자식 컨트롤이 들어 있는입니다. <xref:System.Windows.Controls.UserControl> 3 차원 (3-D) 원뿔 표시 됩니다. 3 차원 개체를 렌더링 하는 것은 훨씬 쉽게 통합할는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 보다와 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]합니다. 따라서 하는 의미가 호스트는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> 의 3 차원 그래픽 만들 클래스 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]합니다.  
  
 이 연습에서 설명하는 작업은 다음과 같습니다.  
  
-   만들기는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>합니다.  
  
-   Windows Forms 호스트 프로젝트를 만듭니다.  
  
-   호스팅하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>합니다.  
  
 이 연습에서 설명 하는 작업의 전체 코드 목록을 보려면 [Windows Forms 예제에 3 차원 WPF 합성 컨트롤 호스팅](http://go.microsoft.com/fwlink/?LinkID=160001)합니다.  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].  
  
<a name="To_Create_the_UserControl"></a>   
## <a name="creating-the-usercontrol"></a>UserControl 만들기  
  
#### <a name="to-create-the-usercontrol"></a>UserControl을 만들려면  
  
1.  이라는 WPF 사용자 정의 컨트롤 라이브러리 프로젝트 만들기 `HostingWpfUserControlInWf`합니다.  
  
2.  Usercontrol1.xaml이에서 열고는 [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]합니다.  
  
3.  생성된 된 코드를 다음 코드로 바꿉니다.  
  
     이 코드 정의 <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> 두 개의 자식 컨트롤이 들어 있는입니다. 첫 번째 자식 컨트롤은 한 <xref:System.Windows.Controls.Label?displayProperty=nameWithType> ; 두 번째는는 <xref:System.Windows.Controls.Viewport3D> 3 차원 원뿔 표시 하는 컨트롤입니다.  
  
     [!code-xaml[HostingWpfUserControlInWf#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]  
  
<a name="To_Create_the_Windows_Forms_Host_Project"></a>   
## <a name="creating-the-windows-forms-host-project"></a>Windows Forms 호스트 프로젝트 만들기  
  
#### <a name="to-create-the-host-project"></a>호스트 프로젝트 만들기  
  
1.  라는 Windows 응용 프로그램 프로젝트를 추가 `WpfUserControlHost` 솔루션에 있습니다. 자세한 내용은 [방법: 새 WPF 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82)를 참조하세요.  
  
2.  솔루션 탐색기에서 WindowsFormsIntegration.dll 라는 WindowsFormsIntegration 어셈블리에 대 한 참조를 추가 합니다.  
  
3.  다음에 대 한 참조를 추가 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 어셈블리:  
  
    -   PresentationCore  
  
    -   PresentationFramework  
  
    -   WindowsBase  
  
4.  에 대 한 참조 추가 `HostingWpfUserControlInWf` 프로젝트.  
  
5.  솔루션 탐색기에서 설정 된 `WpfUserControlHost` 프로젝트를 시작 프로젝트로 합니다.  
  
<a name="To_Host_the_Windows_Presentation_Foundation"></a>   
## <a name="hosting-the-windows-presentation-foundation-usercontrol"></a>Windows Presentation Foundation UserControl 호스팅  
  
#### <a name="to-host-the-usercontrol"></a>UserControl 호스트 하려면  
  
1.  Windows Forms 디자이너에서 Form1을 엽니다.  
  
2.  속성 창에서 클릭 **이벤트**, 두 번 클릭 하 고는 <xref:System.Windows.Forms.Form.Load> 이벤트를 이벤트 처리기를 만듭니다.  
  
     새로 생성 된 코드 편집기가 열립니다. `Form1_Load` 이벤트 처리기입니다.  
  
3.  Form1.cs의 코드를 다음 코드로 바꿉니다.  
  
     `Form1_Load` 이벤트 처리기의 인스턴스를 만들고 `UserControl1` 추가 초기화는 <xref:System.Windows.Forms.Integration.ElementHost> 자식 컨트롤의 컨트롤의 컬렉션입니다. <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤이 자식 컨트롤의 폼의 컬렉션에 추가 됩니다.  
  
     [!code-csharp[HostingWpfUserControlInWf#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]  
  
4.  F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [WPF 디자이너](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [연습: Windows Forms에서 WPF 복합 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)  
 [연습: WPF에서 Windows Forms 복합 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [Windows Forms 예제에서 WPF 합성 컨트롤 호스팅](http://go.microsoft.com/fwlink/?LinkID=160001)
