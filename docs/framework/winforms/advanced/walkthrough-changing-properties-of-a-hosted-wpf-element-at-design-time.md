---
title: "연습: 디자인 타임에 호스팅된 WPF 요소의 속성 변경"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WPF content [Windows Forms], changing properties at design time
- Windows Forms, changing properties of WPF content at design time
- WPF content [Windows Forms], hosting in Windows Forms
- interoperability [WPF]
ms.assetid: a1f7a90c-0bbb-4781-8c3c-8cc8bef2488d
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 027fb2efaff5cfdd4d6962798a85923631fa4e9b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-changing-properties-of-a-hosted-wpf-element-at-design-time"></a>연습: 디자인 타임에 호스팅된 WPF 요소의 속성 변경
이 연습에서는 Windows Forms에 호스트된 WPF(Windows Presentation Foundation) 컨트롤의 속성 값을 변경하는 방법을 보여 줍니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   프로젝트를 만듭니다.  
  
-   WPF 컨트롤을 만듭니다.  
  
-   Windows Form에서 WPF 컨트롤을 호스트합니다.  
  
-   Visual Studio용 WPF 디자이너를 사용하여 속성 값을 변경합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)].  
  
## <a name="creating-the-project"></a>프로젝트 만들기  
 첫 번째 단계에서는 Windows Forms 프로젝트를 만듭니다.  
  
> [!NOTE]
>  WPF 콘텐츠를 호스트하는 경우 C# 및 Visual Basic 프로젝트만 지원됩니다.  
  
#### <a name="to-create-the-project"></a>프로젝트를 만들려면  
  
-   Visual Basic 또는 Visual C# 라는 새 Windows Forms 응용 프로그램 프로젝트 만들기 `WpfHost`합니다.  
  
## <a name="creating-the-wpf-control"></a>WPF 컨트롤 만들기  
 프로젝트에 WPF 컨트롤을 추가한 후 폼에 정렬할 수 있습니다.  
  
#### <a name="to-create-wpf-controls"></a>WPF 컨트롤을 만들려면  
  
1.  프로젝트에 새 WPF <xref:System.Windows.Controls.UserControl>을 추가합니다. 컨트롤 형식의 기본 이름인 `UserControl1.xaml`을 사용합니다. 자세한 내용은 참조 [연습: 새 WPF 콘텐츠 만들기 디자인 타임에 Windows Forms](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)합니다.  
  
2.  에 **속성** 창의 설정의 값은 <xref:System.Windows.Controls.Control.Background%2A> 속성을 `Blue`합니다.  
  
3.  프로젝트를 빌드합니다.  
  
## <a name="changing-property-values-on-the-wpf-control"></a>WPF 컨트롤의 속성 값 변경  
 <xref:System.Windows.Forms.Integration.ElementHost> 스마트 태그를 사용하면 WPF 디자이너에서 호스트된 WPF의 속성을 쉽게 변경할 수 있습니다.  
  
#### <a name="to-host-a-wpf-control"></a>WPF 컨트롤을 호스트하려면  
  
1.  Windows Forms 디자이너에서 `Form1`을 엽니다.  
  
2.  에 **도구 상자**에 **WPF 사용자 정의 컨트롤** 탭을 두 번 클릭 `UserControl1` 의 인스턴스를 만드는 `UserControl1` 폼에 있습니다.  
  
     `UserControl1` 인스턴스가 `elementHost1`이라는 새 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 호스트됩니다.  
  
3.  에 **ElementHost 작업** 스마트 태그 패널 **호스팅된 콘텐츠 편집**합니다.  
  
     UserControl1.xaml이 WPF 디자이너에서 열립니다.  
  
4.  에 **속성** 창의 설정의 값은 <xref:System.Windows.Controls.Control.Background%2A> 속성을 `Red`합니다.  
  
5.  프로젝트를 다시 빌드합니다.  
  
6.  Windows Forms 디자이너에서 `Form1`을 엽니다.  
  
     `UserControl1` 인스턴스의 배경색이 빨간색입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [방법: TableLayoutPanel 컨트롤의 자식 컨트롤 고정 및 도킹](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [방법: 디자인 타임에 컨트롤을 양식의 가장자리에 맞춤](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
 [연습: Windows Forms에서 맞춤선을 사용하여 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [마이그레이션 및 상호 운용성](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [WPF 컨트롤 사용](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [WPF 디자이너](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)
