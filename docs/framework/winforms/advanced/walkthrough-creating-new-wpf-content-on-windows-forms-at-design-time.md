---
title: '연습: 디자인 타임에 Windows Forms에서 새 WPF 콘텐츠 만들기'
ms.date: 08/18/2018
helpviewer_keywords:
- interoperability [Windows Forms], WPF and Windows Forms
- WPF content [Windows Forms], hosting in Windows Forms
- hosting WPF content in Windows Forms
- ElementHost control
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 2e92d8e8-f0e4-4df7-9f07-2acf35cd798c
ms.openlocfilehash: dd68911abfa6bd6315091fb4630134532053efa1
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2018
ms.locfileid: "42999873"
---
# <a name="walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time"></a>연습: 디자인 타임에 Windows Forms에서 새 WPF 콘텐츠 만들기

이 항목에서는 Windows Forms 기반 응용 프로그램에서 사용할 WPF(Windows Presentation Foundation) 컨트롤을 만드는 방법을 보여 줍니다.

이 연습에서는 다음 작업을 수행합니다.

- 프로젝트를 만듭니다.

- 새 WPF 컨트롤을 만듭니다.

- 새 WPF 컨트롤을 Windows Form에 추가합니다. WPF 컨트롤이 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 호스트됩니다.

## <a name="prerequisites"></a>전제 조건

이 연습을 완료하려면 다음 구성 요소가 필요합니다.

- Visual Studio 2017

## <a name="creating-the-project"></a>프로젝트 만들기

첫 번째 단계에서는 Windows Forms 프로젝트를 만듭니다. Visual Studio를 열고 새 **Windows Forms 앱 (.NET Framework)** Visual Basic 또는 Visual C# 프로젝트 `HostingWpf`합니다.

> [!NOTE]
> WPF 콘텐츠를 호스트하는 경우 C# 및 Visual Basic 프로젝트만 지원됩니다.

## <a name="creating-a-new-wpf-control"></a>새 WPF 컨트롤 만들기

새 WPF 컨트롤을 만들고 프로젝트에 추가하는 작업은 다른 항목을 프로젝트에 추가하는 것만큼 쉽습니다. Windows Forms 디자이너는 특정 종류의 명명 된 컨트롤을 사용 하 여 작동 *복합 컨트롤*, 또는 *사용자 정의 컨트롤*합니다. WPF 사용자 정의 컨트롤에 대한 자세한 내용은 <xref:System.Windows.Controls.UserControl>을 참조하세요.

> [!NOTE]
> WPF용 <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> 형식은 Windows Forms에서 제공하는 <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>이라는 사용자 정의 컨트롤 형식과 별개입니다.

### <a name="to-create-a-new-wpf-control"></a>새 WPF 컨트롤을 만들려면

1. **솔루션 탐색기**, 새 **WPF 사용자 정의 컨트롤 라이브러리 (.NET Framework)** 프로젝트를 솔루션입니다. 컨트롤 라이브러리의 기본 이름인 `WpfControlLibrary1`을 사용합니다. 기본 컨트롤 이름은 `UserControl1.xaml`입니다.

     새 컨트롤을 추가 하면 다음과 같은 같은 효과가 있습니다.

    - UserControl1.xaml 파일이 추가됩니다.

    - UserControl1.xaml.cs 또는 UserControl1.xaml.vb 파일이 추가됩니다. 이 파일에는 이벤트 처리기 및 기타 구현에 대한 코드 숨김이 포함됩니다.

    - WPF 어셈블리에 대한 참조가 추가됩니다.

    - UserControl1.xaml 파일이 [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)]에서 열립니다.

2. 디자인 뷰에서 `UserControl1`이 선택되었는지 확인합니다. 자세한 내용은 [방법: 선택 하 고 디자인 화면에서 요소 이동](http://msdn.microsoft.com/library/54cb70b6-b35b-46e4-a0cc-65189399c474)합니다.

3. 에 **속성** 창에서 값을 설정 합니다 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 속성을 **200**합니다.

4. **도구 상자**를 끌어를 <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> 컨트롤을 디자인 화면으로 합니다.

5. 에 **속성** 창에서 값을 설정 합니다 <xref:System.Windows.Controls.TextBox.Text%2A> 속성을 **Hosted Content**합니다.

    > [!NOTE]
    > 일반적으로 더 복잡한 WPF 콘텐츠를 호스트해야 합니다. <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> 컨트롤은 여기서 설명 목적으로만 사용됩니다.

6. 프로젝트를 빌드합니다.

## <a name="adding-a-wpf-control-to-a-windows-form"></a>Windows Form에 WPF 컨트롤 추가

폼에서 새 WPF 컨트롤을 사용할 준비가 되었습니다. Windows Forms에서 사용 하 여 <xref:System.Windows.Forms.Integration.ElementHost> WPF 콘텐츠를 호스트 하는 컨트롤입니다.

### <a name="to-add-a-wpf-control-to-a-windows-form"></a>Windows Form에 WPF 컨트롤을 추가하려면

1. Windows Forms 디자이너에서 `Form1`을 엽니다.

2. 에 **도구 상자**, 레이블이 지정 된 탭을 찾으려면 **WPFUserControlLibrary WPF 사용자 정의 컨트롤**합니다.

3. `UserControl1` 인스턴스를 폼으로 끕니다.

    - WPF 컨트롤을 호스트할 폼에 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤이 자동으로 만들어집니다.

    - <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤 이름이 `elementHost1` 및를 **속성** 보시 창 해당 <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> 속성이 **UserControl1**합니다.

    - WPF 어셈블리에 대한 참조가 프로젝트에 추가됩니다.

    - `elementHost1` 컨트롤에는 사용 가능한 호스팅 옵션을 표시하는 스마트 태그 패널이 있습니다.

4. 에 **ElementHost 작업** 스마트 태그 패널 **부모 컨테이너에서 도킹**합니다.

5. **F5** 키를 눌러 응용 프로그램을 빌드하고 실행합니다.

## <a name="next-steps"></a>다음 단계

Windows Forms와 WPF는 서로 다른 기술이지만 긴밀하게 상호 운용하도록 설계되었습니다. 다양 한 모양과 응용 프로그램에서 동작을 제공 하려면 다음을 시도 합니다.

- WPF 페이지에서 Windows Forms 컨트롤을 호스트합니다. 자세한 내용은 [연습: WPF에서 Windows Forms 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)합니다.

- WPF 콘텐츠에 Windows Forms 시각적 스타일을 적용합니다. 자세한 내용은 [방법: 혼합 응용 프로그램에서 비주얼 스타일 사용](../../../../docs/framework/wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md)을 참조하세요.

- WPF 콘텐츠의 스타일을 변경합니다. 자세한 내용은 [연습: WPF 콘텐츠 스타일 지정](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md)합니다.

## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [마이그레이션 및 상호 운용성](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)
- [WPF 컨트롤 사용](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)
- [WPF 디자이너](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)