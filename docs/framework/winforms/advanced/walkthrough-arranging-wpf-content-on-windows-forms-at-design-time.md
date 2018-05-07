---
title: '연습: 디자인 타임에 Windows Forms에서 WPF 콘텐츠 정렬'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF user control [Windows Forms], hosting in a layout panel
- WPF content [Windows Forms], arranging at design time
- Windows Forms, arranging WPF content at design time
- WPF content [Windows Forms], hosting in Windows Forms
- Windows Forms, anchoring and docking WPF content
- interoperability [WPF]
ms.assetid: 5efb1c53-1484-43d6-aa8a-f4861b99bb8a
ms.openlocfilehash: 373a7f977a9dad59cd40fd29fdd39c8fc6996ad0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-arranging-wpf-content-on-windows-forms-at-design-time"></a>연습: 디자인 타임에 Windows Forms에서 WPF 콘텐츠 정렬
이 연습에서는 기준 위치 지정 및 맞춤선과 같은 Windows Forms 레이아웃 기능을 사용하여 WPF(Windows Presentation Foundation) 컨트롤을 정렬하는 방법을 보여 줍니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   프로젝트를 만듭니다.  
  
-   WPF 컨트롤을 만듭니다.  
  
-   레이아웃 패널에서 WPF 컨트롤을 호스트합니다.  
  
-   맞춤선을 사용하여 WPF 컨트롤을 맞춥니다.  
  
-   WPF 컨트롤을 고정 및 도킹합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)].  
  
## <a name="creating-the-project"></a>프로젝트 만들기  
 첫 번째 단계에서는 Windows Forms 프로젝트를 만듭니다.  
  
> [!NOTE]
>  WPF 콘텐츠를 호스트하는 경우 C# 및 Visual Basic 프로젝트만 지원됩니다.  
  
#### <a name="to-create-the-project"></a>프로젝트를 만들려면  
  
-   Visual Basic 또는 Visual C# 라는 새 Windows Forms 응용 프로그램 프로젝트 만들기 `ArrangeElementHost`합니다.  
  
## <a name="creating-the-wpf-control"></a>WPF 컨트롤 만들기  
 프로젝트에 WPF 컨트롤을 추가한 후 폼에 정렬할 수 있습니다.  
  
#### <a name="to-create-wpf-controls"></a>WPF 컨트롤을 만들려면  
  
1.  프로젝트에 새 WPF <xref:System.Windows.Controls.UserControl>을 추가합니다. 컨트롤 형식의 기본 이름인 `UserControl1.xaml`을 사용합니다. 자세한 내용은 참조 [연습: 새 WPF 콘텐츠 만들기 디자인 타임에 Windows Forms](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)합니다.  
  
2.  디자인 뷰에서 `UserControl1`이 선택되었는지 확인합니다. 자세한 내용은 참조 [하는 방법: 선택 하 고 디자인 화면에서 요소 이동](http://msdn.microsoft.com/library/54cb70b6-b35b-46e4-a0cc-65189399c474)합니다.  
  
3.  에 **속성** 창의 설정의 값은 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 속성을 `200`합니다.  
  
4.  <xref:System.Windows.Controls.Control.Background%2A> 속성 값을 `Blue`로 설정합니다.  
  
5.  프로젝트를 빌드합니다.  
  
## <a name="hosting-wpf-controls-in-a-layout-panel"></a>레이아웃 패널에서 WPF 컨트롤 호스트  
 다른 Windows Forms 컨트롤을 사용하는 것과 동일한 방식으로 레이아웃 패널에서 WPF 컨트롤을 사용할 수 있습니다.  
  
#### <a name="to-host-wpf-controls-in-a-layout-panel"></a>레이아웃 패널에서 WPF 컨트롤을 호스트하려면  
  
1.  Windows Forms 디자이너에서 `Form1`을 엽니다.  
  
2.  에 **도구 상자**를 끌어 한 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 폼으로 합니다.  
  
3.  에 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 스마트 태그 패널에서 선택 **마지막 행 제거**합니다.  
  
4.  <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 더 큰 너비와 높이로 조정합니다.  
  
5.  에 **도구 상자**를 두 번 클릭 `UserControl1` 의 인스턴스를 만드는 `UserControl1` 의 첫 번째 셀에는 <xref:System.Windows.Forms.TableLayoutPanel> 제어 합니다.  
  
     `UserControl1` 인스턴스가 `elementHost1`이라는 새 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 호스트됩니다.  
  
6.  에 **도구 상자**를 두 번 클릭 `UserControl1` 의 두 번째 셀에 다른 인스턴스를 만들 수는 <xref:System.Windows.Forms.TableLayoutPanel> 제어 합니다.  
  
7.  에 **문서 개요** 창에서 `tableLayoutPanel1`합니다. 자세한 내용은 참조 [문서 개요 창](http://msdn.microsoft.com/library/9054f2bc-f6f8-4242-9fe0-be71089b12f8)합니다.  
  
8.  에 **속성** 창의 설정의 값은 <xref:System.Windows.Forms.Control.Padding%2A> 속성을 `10, 10, 10, 10`합니다.  
  
     두 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤 모두 새 레이아웃에 맞게 크기가 조정됩니다.  
  
## <a name="using-snaplines-to-align-wpf-controls"></a>맞춤선을 사용하여 WPF 컨트롤 맞춤  
 맞춤선을 사용하여 폼에서 컨트롤을 쉽게 맞출 수 있습니다. 맞춤선을 사용하여 WPF 컨트롤도 맞출 수 있습니다. 자세한 내용은 참조 [연습: 맞춤선 Windows Forms에서 사용 하 여 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)합니다.  
  
#### <a name="to-use-snaplines-to-align-wpf-controls"></a>맞춤선을 사용하여 WPF 컨트롤을 맞추려면  
  
1.  **도구 상자**의 인스턴스를 끌어 `UserControl1` 폼 아래 공간에 배치 하 고는 <xref:System.Windows.Forms.TableLayoutPanel> 제어 합니다.  
  
     `UserControl1` 인스턴스가 `elementHost3`이라는 새 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 호스트됩니다.  
  
2.  맞춤선을 사용하여 `elementHost3`의 왼쪽 가장자리를 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 왼쪽 가장자리에 맞춥니다.  
  
3.  맞춤선을 사용하여 `elementHost3`의 크기를 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤과 동일한 너비로 조정합니다.  
  
4.  가운데 맞춤선이 컨트롤 사이에 나타날 때까지 `elementHost3`을 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤 쪽으로 이동합니다.  
  
5.  에 **속성** 여백 속성의 값을 설정 하는 창 `20, 20, 20, 20`합니다.  
  
6.  가운데 맞춤선이 다시 나타날 때까지 `elementHost3`을 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤에서 멀리 이동합니다. 이제 가운데 맞춤선이 여백 20을 나타냅니다.  
  
7.  왼쪽 가장자리가 `elementHost1`의 왼쪽 가장자리와 맞춰질 때까지 `elementHost3`을 오른쪽으로 이동합니다.  
  
8.  오른쪽 가장자리가 `elementHost2`의 오른쪽 가장자리와 맞춰질 때까지 `elementHost3`의 너비를 변경합니다.  
  
## <a name="anchoring-and-docking-wpf-controls"></a>WPF 컨트롤 고정 및 도킹  
 폼에 호스트된 WPF 컨트롤은 다른 Windows Forms 컨트롤과 동일한 고정 및 도킹 동작을 갖습니다.  
  
#### <a name="to-anchor-and-dock-wpf-controls"></a>WPF 컨트롤을 고정 및 도킹하려면  
  
1.  `elementHost1`를 선택합니다.  
  
2.  에 **속성** 창에서 설정 된 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 **위쪽, 아래쪽, 왼쪽, 오른쪽**합니다.  
  
3.  <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 더 큰 크기로 조정합니다.  
  
     `elementHost1` 컨트롤의 크기가 조정되어 셀을 채웁니다.  
  
4.  `elementHost2`를 선택합니다.  
  
5.  에 **속성** 창의 설정의 값은 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Fill>합니다.  
  
     `elementHost2` 컨트롤의 크기가 조정되어 셀을 채웁니다.  
  
6.  <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 선택합니다.  
  
7.  <xref:System.Windows.Forms.Control.Dock%2A> 속성의 값을 <xref:System.Windows.Forms.DockStyle.Top>로 설정합니다.  
  
8.  `elementHost3`를 선택합니다.  
  
9. <xref:System.Windows.Forms.Control.Dock%2A> 속성의 값을 <xref:System.Windows.Forms.DockStyle.Fill>로 설정합니다.  
  
     `elementHost3` 컨트롤의 크기가 조정되어 폼의 나머지 공간을 채웁니다.  
  
10. 폼의 크기를 조정합니다.  
  
     <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤 3개의 크기가 모두 적절하게 조정됩니다.  
  
     자세한 내용은 참조 [하는 방법: 앵커 및 TableLayoutPanel 컨트롤의 자식 컨트롤을 도킹](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [방법: TableLayoutPanel 컨트롤의 자식 컨트롤 고정 및 도킹](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [방법: 디자인 타임에 컨트롤을 양식의 가장자리에 맞춤](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
 [연습: Windows Forms에서 맞춤선을 사용하여 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [마이그레이션 및 상호 운용성](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [WPF 컨트롤 사용](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [WPF 디자이너](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)
