---
title: "방법: 디자인 타임에 ElementHost 컨트롤 복사하여 붙여넣기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ffe7d050de84eba8c7962a62a8604a72f78bc2bc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-copy-and-paste-an-elementhost-control-at-design-time"></a>방법: 디자인 타임에 ElementHost 컨트롤 복사하여 붙여넣기
이 절차에서는 Windows Form에 Windows Presentation Foundation (WPF) 컨트롤을 복사 하는 방법을 보여 줍니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-copy-and-paste-an-elementhost-control-at-design-time"></a>복사 하 여 디자인 타임에 ElementHost 컨트롤을 붙여 넣습니다.  
  
1.  새 WPF 추가 <xref:System.Windows.Controls.UserControl> Windows Forms 프로젝트. 컨트롤 형식의 기본 이름인 `UserControl1.xaml`을 사용합니다. 자세한 내용은 참조 [연습: 새 WPF 콘텐츠 만들기 디자인 타임에 Windows Forms](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)합니다.  
  
2.  에 **속성** 창의 설정의 값은 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 의 속성 `UserControl1` 를 `200`합니다.  
  
3.  <xref:System.Windows.Controls.Control.Background%2A> 속성 값을 `Blue`로 설정합니다.  
  
4.  프로젝트를 빌드합니다.  
  
5.  Windows Forms 디자이너에서 `Form1`을 엽니다.  
  
6.  **도구 상자**의 인스턴스를 끌어 `UserControl1` 폼입니다.  
  
     `UserControl1` 인스턴스가 `elementHost1`이라는 새 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 호스트됩니다.  
  
7.  `elementHost1`을 선택하고 Ctrl+C를 눌러 클립보드에 복사합니다.  
  
8.  CTRL + V를 붙여 복사한 컨트롤을 폼으로 키를 누릅니다.  
  
     새 <xref:System.Windows.Forms.Integration.ElementHost> 라는 컨트롤 `elementHost2` 폼에 만들어집니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [연습: ElementHost 컨트롤을 복사하여 다른 Windows Forms에 붙여넣기](../../../../docs/framework/winforms/advanced/copy--paste-an-elementhost-control-into-forms.md)  
 [마이그레이션 및 상호 운용성](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [WPF 컨트롤 사용](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [WPF 디자이너](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)
