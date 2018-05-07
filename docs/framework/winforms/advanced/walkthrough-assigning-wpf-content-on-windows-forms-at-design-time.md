---
title: '연습: 디자인 타임에 Windows Forms에서 WPF 콘텐츠 할당'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF content [Windows Forms], assigning at design time
- ElementHost control [Windows Forms], assigning WPF content at design time
- interoperability [WPF]
- Windows Forms, content assignments
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: b3e9ef93-7e0f-4a2f-8f1e-3437609a1eb7
ms.openlocfilehash: abdeb2e77486d4f94f3d0543d94186168baae31c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-assigning-wpf-content-on-windows-forms-at-design-time"></a>연습: 디자인 타임에 Windows Forms에서 WPF 콘텐츠 할당
이 연습에서는 폼에 표시할 WPF(Windows Presentation Foundation) 컨트롤 형식을 선택하는 방법을 보여 줍니다. 프로젝트에 포함된 모든 WPF 컨트롤 형식을 선택할 수 있습니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   프로젝트를 만듭니다.  
  
-   WPF 컨트롤 형식을 만듭니다.  
  
-   WPF 컨트롤을 선택합니다.  
  
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
  
-   Visual Basic 또는 Visual C# 라는 새 Windows Forms 응용 프로그램 프로젝트 만들기 `SelectingWpfContent`합니다.  
  
## <a name="creating-the-wpf-control-types"></a>WPF 컨트롤 형식 만들기  
 프로젝트에 WPF 컨트롤 형식을 추가한 후 다양한 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 호스트할 수 있습니다.  
  
#### <a name="to-create-wpf-control-types"></a>WPF 컨트롤 형식을 만들려면 다음을 수행합니다.  
  
1.  새 WPF <xref:System.Windows.Controls.UserControl> 프로젝트를 솔루션에 추가합니다. 컨트롤 형식의 기본 이름인 `UserControl1.xaml`을 사용합니다. 자세한 내용은 참조 [연습: 새 WPF 콘텐츠 만들기 디자인 타임에 Windows Forms](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)합니다.  
  
2.  디자인 뷰에서 `UserControl1`이 선택되었는지 확인합니다. 자세한 내용은 참조 [하는 방법: 선택 하 고 디자인 화면에서 요소 이동](http://msdn.microsoft.com/library/54cb70b6-b35b-46e4-a0cc-65189399c474)합니다.  
  
3.  에 **속성** 창의 설정의 값은 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 속성을 `200`합니다.  
  
4.  추가 <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> 컨트롤을 <xref:System.Windows.Controls.UserControl> 의 값을 설정 하 고는 <xref:System.Windows.Controls.TextBox.Text%2A> 속성을 **호스팅된 콘텐츠**합니다.  
  
5.  프로젝트에 두 번째 WPF <xref:System.Windows.Controls.UserControl>을 추가합니다. 컨트롤 형식의 기본 이름인 `UserControl2.xaml`을 사용합니다.  
  
6.  에 **속성** 창의 설정의 값은 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 속성을 `200`합니다.  
  
7.  추가 <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> 컨트롤을 <xref:System.Windows.Controls.UserControl> 의 값을 설정 하 고는 <xref:System.Windows.Controls.TextBox.Text%2A> 속성을 **Hosted Content 2**합니다.  
  
 **참고** 일반적으로 더 복잡 한 WPF 콘텐츠를 호스트 해야 합니다. <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> 컨트롤은 여기서 설명 목적으로만 사용됩니다.  
  
1.  프로젝트를 빌드합니다.  
  
## <a name="selecting-wpf-controls"></a>WPF 컨트롤 선택  
 이미 콘텐츠를 호스트하고 있는 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에 다른 WPF 콘텐츠를 할당할 수 있습니다.  
  
#### <a name="to-select-wpf-controls"></a>WPF 컨트롤을 선택하려면  
  
1.  Windows Forms 디자이너에서 `Form1`을 엽니다.  
  
2.  에 **도구 상자**, 두 번 클릭 `UserControl1` 의 인스턴스를 만드는 `UserControl1` 폼에 있습니다.  
  
     `UserControl1` 인스턴스가 `elementHost1`이라는 새 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 호스트됩니다.  
  
3.  에 대 한 스마트 태그 패널에서 `elementHost1`열고는 **호스트 된 콘텐츠 선택** 드롭 다운 목록입니다.  
  
4.  선택 **UserControl2** 드롭 다운 목록 상자에서 합니다.  
  
     이제 `elementHost1` 컨트롤이 `UserControl2` 형식의 인스턴스를 호스트합니다.  
  
5.  에 **속성** 창 확인는 <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> 속성이로 설정 되어 **UserControl2**합니다.  
  
6.  **도구 상자**에 **WPF 상호 운용성** 그룹에서 끌어는 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤을 폼으로 합니다.  
  
     새 컨트롤의 기본 이름은 `elementHost2`입니다.  
  
7.  에 대 한 스마트 태그 패널에서 `elementHost2`열고는 **호스트 된 콘텐츠 선택** 드롭 다운 목록입니다.  
  
8.  선택 **UserControl1** 드롭 다운 목록에서 합니다.  
  
9. 이제 `elementHost2` 컨트롤이 `UserControl1` 형식의 인스턴스를 호스트합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [마이그레이션 및 상호 운용성](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [WPF 컨트롤 사용](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [WPF 디자이너](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)
