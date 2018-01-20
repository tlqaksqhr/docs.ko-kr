---
title: "연습: WPF에서 Windows Forms 컨트롤 호스팅"
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
helpviewer_keywords: hosting Windows Forms control in WPF [WPF]
ms.assetid: 9cb88415-39b0-4c46-80c4-ff325b674286
caps.latest.revision: "36"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ce6920e8a6cea08f4aba083b99d56b4252409827
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf"></a>연습: WPF에서 Windows Forms 컨트롤 호스팅
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 풍부한 기능 집합이 있는 많은 컨트롤을 제공합니다. 그러나, 때때로 경우도 있습니다 사용할 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에 사용자 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 페이지입니다. 예를 들어 기존 상당한 투자를 해야 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤 또는 있습니다 있을 수는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 고유 기능을 제공 하는 컨트롤입니다.  
  
 이 연습을 호스트 하는 방법을 보여 줍니다.는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> 컨트롤에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 코드를 사용 하 여 페이지입니다.  
  
 이 연습에 나와 있는 작업의 전체 코드 목록을 보려면 [WPF 샘플에서 Windows Forms 컨트롤 호스팅](http://go.microsoft.com/fwlink/?LinkID=160057)합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
## <a name="hosting-the-windows-forms-control"></a>Windows Forms 컨트롤 호스팅  
  
#### <a name="to-host-the-maskedtextbox-control"></a>MaskedTextBox 컨트롤을 호스트하려면  
  
1.  이라는 WPF 응용 프로그램 프로젝트 만들기 `HostingWfInWpf`합니다.  
  
2.  다음 어셈블리에 대한 참조를 추가합니다.  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
3.  MainWindow.xaml의 열은 [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]합니다.  
  
4.  이름에서 <xref:System.Windows.Controls.Grid> 요소 `grid1`합니다.  
  
     [!code-xaml[HostingWfInWPF#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml#1)]  
  
5.  디자인 보기 또는 XAML 보기에서 선택 된 <xref:System.Windows.Window> 요소입니다.  
  
6.  속성 창에서 클릭 된 **이벤트** 탭 합니다.  
  
7.  두 번 클릭 하 여 <xref:System.Windows.FrameworkElement.Loaded> 이벤트입니다.  
  
8.  다음 코드를 처리 하는 <xref:System.Windows.FrameworkElement.Loaded> 이벤트입니다.  
  
     [!code-csharp[HostingWfInWPF#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#10)]
     [!code-vb[HostingWfInWPF#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#10)]  
  
9. 파일 맨 위에 있는 다음 추가 `Imports` 또는 `using` 문.  
  
     [!code-csharp[HostingWfInWPF#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#11)]
     [!code-vb[HostingWfInWPF#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#11)]  
  
10. F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [WPF 디자이너](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [연습: XAML을 사용하여 WPF에서 Windows Forms 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml.md)  
 [연습: WPF에서 Windows Forms 복합 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [연습: Windows Forms에서 WPF 복합 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)  
 [Windows Forms 컨트롤 및 해당 WPF 컨트롤](../../../../docs/framework/wpf/advanced/windows-forms-controls-and-equivalent-wpf-controls.md)  
 [WPF에서 Windows Forms 컨트롤 호스팅 샘플](http://go.microsoft.com/fwlink/?LinkID=160057)
