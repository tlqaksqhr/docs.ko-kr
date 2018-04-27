---
title: '연습: WPF에서 ActiveX 컨트롤 호스팅'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ActiveX controls [WPF interoperability]
- hosting ActiveX controls [WPF]
ms.assetid: 1931d292-0dd1-434f-963c-dcda7638d75a
caps.latest.revision: 30
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fc4f577da04fb8ed15bae3c0497b35803a46f08f
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="walkthrough-hosting-an-activex-control-in-wpf"></a>연습: WPF에서 ActiveX 컨트롤 호스팅
향상 된 상호 작용할 수 있도록 브라우저를 사용할 수 있습니다 [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] 의 제어 프로그램 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-기반 응용 프로그램입니다. 이 연습에서는 호스팅하는 방법을 보여 줍니다.는 [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] 의 컨트롤로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 페이지.  
  
 이 연습에서 설명하는 작업은 다음과 같습니다.  
  
-   프로젝트 만들기.  
  
-   ActiveX 컨트롤을 만듭니다.  
  
-   WPF 페이지에서 ActiveX 컨트롤 호스팅  
  
 사용 하는 방법을 이해 하 게이 연습을 완료 하는 경우 [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] 의 제어 프로그램 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-기반 응용 프로그램입니다.  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] Visual Studio가 설치 된 컴퓨터에 설치 합니다.  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
## <a name="creating-the-project"></a>프로젝트 만들기  
  
#### <a name="to-create-and-set-up-the-project"></a>프로젝트를 만들고 설정하려면  
  
1.  이라는 WPF 응용 프로그램 프로젝트 만들기 `HostingAxInWpf`합니다.  
  
2.  Windows Forms 컨트롤 라이브러리 프로젝트를 솔루션에 추가 하 고 프로젝트 이름을 `WmpAxLib`합니다.  
  
3.  WmpAxLib 프로젝트에서 wmp.dll 라고 하는 Windows Media Player 어셈블리에 대 한 참조를 추가 합니다.  
  
4.  열기는 **도구 상자**합니다.  
  
5.  마우스 오른쪽 단추로 클릭는 **도구 상자**, 클릭 하 고 **항목 선택**합니다.  
  
6.  클릭는 **COM 구성 요소** 탭을는 **Windows Media Player** 컨트롤을 선택한 다음 클릭 **확인**합니다.  
  
     에 Windows Media Player 컨트롤이 추가 되 고 **도구 상자**합니다.  
  
7.  솔루션 탐색기에서 마우스 오른쪽 단추로 클릭는 **UserControl1** 파일을 선택한 다음 클릭 **이름 바꾸기**합니다.  
  
8.  이름을 변경한 `WmpAxControl.vb` 또는 `WmpAxControl.cs`언어에 따라, 합니다.  
  
9. 모든 참조는 메시지가 클릭 **예**합니다.  
  
## <a name="creating-the-activex-control"></a>ActiveX 컨트롤 만들기  
 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] 자동으로 생성 한 <xref:System.Windows.Forms.AxHost> 에 대 한 래퍼 클래스는 [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] 컨트롤 디자인 화면에 추가 된 경우를 제어 합니다. 다음 절차는 AxInterop.WMPLib.dll 이라는 관리 되는 어셈블리를 만듭니다.  
  
#### <a name="to-create-the-activex-control"></a>ActiveX 컨트롤을 만들려면  
  
1.  Windows Forms 디자이너에서 WmpAxControl.vb 또는 WmpAxControl.cs를 엽니다.  
  
2.  **도구 상자**, Windows Media Player 컨트롤 디자인 화면을 추가 합니다.  
  
3.  속성 창에서 Windows Media Player 컨트롤의 값을 설정 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Fill>합니다.  
  
4.  WmpAxLib 컨트롤 라이브러리 프로젝트를 빌드하십시오.  
  
## <a name="hosting-the-activex-control-on-a-wpf-page"></a>WPF 페이지에서 ActiveX 컨트롤 호스팅  
  
#### <a name="to-host-the-activex-control"></a>ActiveX 컨트롤을 호스트 하려면  
  
1.  HostingAxInWpf 프로젝트에서 생성 된에 대 한 참조를 추가 [!INCLUDE[TLA2#tla_actx](../../../../includes/tla2sharptla-actx-md.md)] 상호 운용성 어셈블리.  
  
     이 어셈블리 AxInterop.WMPLib.dll은, Windows Media Player 컨트롤을 가져올 때 WmpAxLib 프로젝트의 디버그 폴더에 추가 되었습니다.  
  
2.  WindowsFormsIntegration.dll 라는 WindowsFormsIntegration 어셈블리에 대 한 참조를 추가 합니다.  
  
3.  에 대 한 참조 추가 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] System.Windows.Forms.dll 이름으로 지정 된 어셈블리입니다.  
  
4.  WPF Designer의 MainWindow.xaml을 엽니다.  
  
5.  이름에서 <xref:System.Windows.Controls.Grid> 요소 `grid1`합니다.  
  
     [!code-xaml[HostingAxInWpf#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml#1)]  
  
6.  디자인 보기 또는 XAML 보기에서 선택 된 <xref:System.Windows.Window> 요소입니다.  
  
7.  속성 창에서 클릭 된 **이벤트** 탭 합니다.  
  
8.  두 번 클릭 하 여 <xref:System.Windows.FrameworkElement.Loaded> 이벤트입니다.  
  
9. 다음 코드를 처리 하는 <xref:System.Windows.FrameworkElement.Loaded> 이벤트입니다.  
  
     이 코드의 인스턴스를 만듭니다.는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 제어 하 고 인스턴스를 추가 `AxWindowsMediaPlayer` 을 자식으로 제어 합니다.  
  
     [!code-csharp[HostingAxInWpf#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml.cs#11)]
     [!code-vb[HostingAxInWpf#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingAxInWpf/VisualBasic/HostingAxInWpf/window1.xaml.vb#11)]  
  
10. F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [WPF 디자이너](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [연습: WPF에서 Windows Forms 복합 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [연습: Windows Forms에서 WPF 복합 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
