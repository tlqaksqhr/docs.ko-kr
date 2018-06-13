---
title: '방법: 혼합 응용 프로그램에서 비주얼 스타일 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- visual styles [Windows Forms]
ms.assetid: 95de9b9c-d804-405c-b2d1-49a88c1e0fe1
ms.openlocfilehash: 2d714ad020f2f7b6a6343c8f8e3901b59dfd23a8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545625"
---
# <a name="how-to-enable-visual-styles-in-a-hybrid-application"></a>방법: 혼합 응용 프로그램에서 비주얼 스타일 사용
이 항목에서는 사용 하도록 설정 하는 방법을 보여 줍니다. [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] 비주얼 스타일에 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에서 호스트 되는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-기반 응용 프로그램입니다.  
  
 응용 프로그램에서 호출 하는 경우는 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> 메서드, 대부분의 프로그램 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 응용 프로그램에서 실행 될 때 컨트롤에서 비주얼 스타일을 자동으로 사용 됩니다 [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)]합니다. 자세한 내용은 참조 [비주얼 스타일을 사용 하 여 컨트롤 렌더링](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)합니다.  
  
 이 항목에서 설명 하는 작업의 전체 코드 목록을 보려면 [하이브리드 응용 프로그램 샘플에서 비주얼 스타일을 사용 하도록 설정](http://go.microsoft.com/fwlink/?LinkID=159986)합니다.  
  
## <a name="enabling-windows-forms-visual-styles"></a>Windows Forms 시각적 스타일 사용  
  
#### <a name="to-enable-windows-forms-visual-styles"></a>Windows Forms 시각적 스타일을 사용하려면  
  
1.  만들기는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 라는 응용 프로그램 프로젝트 `HostingWfWithVisualStyles`합니다.  
  
2.  솔루션 탐색기에서 다음 어셈블리에 대한 참조를 추가합니다.  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
3.  도구 상자에서 두 번 클릭은 <xref:System.Windows.Controls.Grid> 아이콘을 한 <xref:System.Windows.Controls.Grid> 디자인 화면에서 요소입니다.  
  
4.  속성 창에서 값을 설정할는 <xref:System.Windows.FrameworkElement.Height%2A> 및 <xref:System.Windows.FrameworkElement.Width%2A> 속성을 **자동**합니다.  
  
5.  디자인 보기 또는 XAML 보기에서 선택 된 <xref:System.Windows.Window>합니다.  
  
6.  속성 창에서 클릭 된 **이벤트** 탭 합니다.  
  
7.  두 번 클릭 하 여 <xref:System.Windows.FrameworkElement.Loaded> 이벤트입니다.
  
8.  MainWindow.xaml.vb 또는 MainWindow.xaml.cs에서 다음 코드를 처리 하는 <xref:System.Windows.FrameworkElement.Loaded> 이벤트입니다.  
  
     [!code-csharp[HostingWfWithVisualStyles#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfWithVisualStyles/CSharp/HostingWfWithVisualStyles/Window1.xaml.cs#11)]
     [!code-vb[HostingWfWithVisualStyles#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfWithVisualStyles/VisualBasic/HostingWfWithVisualStyles/Window1.xaml.vb#11)]  
  
9. F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.  
  
     [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤이 비주얼 스타일으로 그려집니다.  
  
## <a name="disabling-windows-forms-visual-styles"></a>Windows Forms 시각적 스타일 사용 안 함  
 제거에 대 한 호출 하면 비주얼 스타일을 사용 하지 않으려면는 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> 메서드.  
  
#### <a name="to-disable-windows-forms-visual-styles"></a>Windows Forms 시각적 스타일을 사용하지 않으려면  
  
1.  코드 편집기에서 MainWindow.xaml.vb 또는 MainWindow.xaml.cs를 엽니다.  
  
2.  에 대 한 호출의 주석에서 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> 메서드.  
  
3.  F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.  
  
     [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤이 기본 시스템 스타일으로 그려집니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>  
 <xref:System.Windows.Forms.VisualStyles>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [비주얼 스타일을 사용하여 컨트롤 렌더링](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)  
 [연습: WPF에서 Windows Forms 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)
