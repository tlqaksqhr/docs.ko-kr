---
title: "연습: 전문적인 스타일의 ToolStrip 컨트롤 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStripRenderer class [Windows Forms]
- toolbars [Windows Forms], walkthroughs
- ToolStrip control [Windows Forms], creating professionally styled controls
ms.assetid: b52339ae-f1d3-494e-996e-eb455614098a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0fbc03ad16bcc0d63a75df5478f7da8abbf19193
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-creating-a-professionally-styled-toolstrip-control"></a>연습: 전문적인 스타일의 ToolStrip 컨트롤 만들기
응용 프로그램을 제공할 수 있습니다 <xref:System.Windows.Forms.ToolStrip> 에서 파생 되는 고유한 클래스를 작성 하 여 전문적인 모양과 동작을 제어는 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 유형입니다.  
  
 이 연습에서는 사용 하는 방법을 보여 줍니다. <xref:System.Windows.Forms.ToolStrip> 비슷한 복합 컨트롤을 만드는 컨트롤은 **탐색 창** Microsoft® Outlook®에서 제공 합니다. 같은 작업을이 연습에서 설명 합니다.  
  
-   Windows 컨트롤 라이브러리 프로젝트를 만듭니다.  
  
-   StackView 컨트롤을 디자인 합니다.  
  
-   사용자 지정 렌더러를 구현 합니다.  
  
 작업을 완료 하는 경우 Microsoft Office® XP 컨트롤의 전문적인 모양으로 다시 사용할 수 있는 사용자 지정 클라이언트 제어를 해야 합니다.  
  
 단일 목록으로이 항목의 코드를 복사 하려면 참조 [하는 방법: 전문적인 스타일의 ToolStrip 컨트롤 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-professionally-styled-toolstrip-control.md)합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 완료하려면 다음 사항이 필요합니다.  
  
-   만들고 컴퓨터에 Windows Forms 응용 프로그램 프로젝트를 실행할 수 있는 충분 한 권한이 있는 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] 가 설치 되어 있습니다.  
  
## <a name="creating-a-windows-control-library-project"></a>Windows 컨트롤 라이브러리 프로젝트 만들기  
 첫 번째 단계는 컨트롤 라이브러리 프로젝트를 만드는 것입니다.  
  
#### <a name="to-create-the-control-library-project"></a>컨트롤 라이브러리 프로젝트를 만들려면  
  
1.  라는 새 Windows 컨트롤 라이브러리 프로젝트를 만듭니다 `StackViewLibrary`합니다.  
  
2.  **솔루션 탐색기**, 선택한 언어에 따라 이름이 "UserControl1.cs" 또는 "UserControl1.vb", 원본 파일을 삭제 하 여 프로젝트의 기본 컨트롤을 삭제 합니다.  
  
     자세한 내용은 참조 [NIB: 방법: 제거, 삭제 및 항목 제외](http://msdn.microsoft.com/en-us/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73)합니다.  
  
3.  새로 추가 <xref:System.Windows.Forms.UserControl> 항목의 **StackViewLibrary** 프로젝트. 새 소스 파일의 기본 이름 지정 `StackView`합니다.  
  
## <a name="designing-the-stackview-control"></a>StackView 컨트롤 디자인  
 `StackView` 컨트롤은 하나의 자식에서 합성 컨트롤 <xref:System.Windows.Forms.ToolStrip> 제어 합니다. 복합 컨트롤에 대 한 자세한 내용은 참조 [종류의 사용자 지정 컨트롤](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)합니다.  
  
#### <a name="to-design-the-stackview-control"></a>StackView 컨트롤을 디자인 하려면  
  
1.  **도구 상자**를 끌어 한 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 디자인 화면입니다.  
  
2.  에 **속성** 창의 설정의 <xref:System.Windows.Forms.ToolStrip> 다음 표에 따라 컨트롤의 속성입니다.  
  
    |속성|값|  
    |--------------|-----------|  
    |이름|`stackStrip`|  
    |CanOverflow|`false`|  
    |도킹|<xref:System.Windows.Forms.DockStyle.Bottom>|  
    |글꼴|`Tahoma, 10pt, style=Bold`|  
    |GripStyle|<xref:System.Windows.Forms.ToolStripGripStyle.Hidden>|  
    |LayoutStyle|<xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow>|  
    |안쪽 여백|`0, 7, 0, 0`|  
    |RenderMode|<xref:System.Windows.Forms.ToolStripRenderMode.Professional>|  
  
3.  Windows Forms 디자이너에서 클릭는 <xref:System.Windows.Forms.ToolStrip> 컨트롤의 **추가** 단추와 추가 <xref:System.Windows.Forms.ToolStripButton> 에 `stackStrip` 컨트롤입니다.  
  
4.  에 **속성** 창의 설정의 <xref:System.Windows.Forms.ToolStripButton> 다음 표에 따라 컨트롤의 속성입니다.  
  
    |속성|값|  
    |--------------|-----------|  
    |이름|`mailStackButton`|  
    |CheckOnClick|true|  
    |CheckState|<xref:System.Windows.Forms.CheckState.Checked>|  
    |DisplayStyle|<xref:System.Windows.Forms.ToolStripItemDisplayStyle.ImageAndText>|  
    |ImageAlign|<xref:System.Drawing.ContentAlignment.MiddleLeft>|  
    |ImageScaling|<xref:System.Windows.Forms.ToolStripItemImageScaling.None>|  
    |ImageTransparentColor|`238, 238, 238`|  
    |여백|`0, 0, 0, 0`|  
    |안쪽 여백|`3, 3, 3, 3`|  
    |텍스트|**메일**|  
    |TextAlign|<xref:System.Drawing.ContentAlignment.MiddleLeft>|  
  
5.  세 개의 추가 대 한 7 단계를 반복 <xref:System.Windows.Forms.ToolStripButton> 컨트롤입니다.  
  
     컨트롤 이름을 `calendarStackButton`, `contactsStackButton`, 및 `tasksStackButton`합니다. 값을 설정할는 <xref:System.Windows.Forms.Control.Text%2A> 속성을 **달력**, **연락처**, 및 **작업**각각.  
  
## <a name="handling-events"></a>이벤트 처리  
 두 개의 이벤트를 확인 해야는 `StackView` 컨트롤이 올바르게 동작 합니다. 처리는 <xref:System.Windows.Forms.UserControl.Load> 이벤트를 올바르게 지정 합니다. 처리는 <xref:System.Windows.Forms.ToolStripItem.Click> 각각에 대 한 이벤트 <xref:System.Windows.Forms.ToolStripButton> 제공 하는 `StackView` 와 유사한 상태 동작을 제어는 <xref:System.Windows.Forms.RadioButton> 제어 합니다.  
  
#### <a name="to-handle-events"></a>이벤트를 처리 하려면  
  
1.  Windows Forms 디자이너에서 선택 된 `StackView` 제어 합니다.  
  
2.  에 **속성** 창 클릭 **이벤트**합니다.  
  
3.  Load 이벤트 생성에 두 번 클릭 하 여 `StackView_Load` 이벤트 처리기입니다.  
  
4.  `StackView_Load` 이벤트 처리기에서 다음 코드를 복사하여 붙여 넣습니다.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#3)]  
  
5.  Windows Forms 디자이너에서 선택 된 `mailStackButton` 제어 합니다.  
  
6.  에 **속성** 창 클릭 **이벤트**합니다.  
  
7.  Click 이벤트를 두 번 클릭 합니다.  
  
     Windows Forms 디자이너에서는 오류가 발생 하는 `mailStackButton_Click` 이벤트 처리기입니다.  
  
8.  이름 바꾸기는 `mailStackButton_Click` 이벤트 처리기를 `stackButton_Click`합니다.  
  
     자세한 내용은 참조 [하는 방법: (Visual Basic) 식별자 이름 바꾸기](http://msdn.microsoft.com/en-us/e5a5edf8-3dba-4119-81f4-fc2aba180e0c)합니다.  
  
9. 에 다음 코드를 삽입은 `stackButton_Click` 이벤트 처리기입니다.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#4)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#4)]  
  
10. Windows Forms 디자이너에서 선택 된 `calendarStackButton` 제어 합니다.  
  
11. 에 **속성** 창의을 Click 이벤트를 설정의 `stackButton_Click` 이벤트 처리기입니다.  
  
12. 10과 11에 대 한 단계를 반복 하는 `contactsStackButton` 및 `tasksStackButton` 컨트롤입니다.  
  
## <a name="defining-icons"></a>아이콘 정의  
 각 `StackView` 단추에 연결 된 아이콘입니다. 편의 위해 각 아이콘으로 표현 되는 Base64 인코딩 문자열 하기 전에 deserialize 되는 한 <xref:System.Drawing.Bitmap> 에서 만들어집니다. 프로덕션 환경에서 리소스로 바운딩되어야 비트맵 데이터를 저장 하 고 Windows Forms 디자이너에 아이콘이 나타납니다. 자세한 내용은 참조 [하는 방법: Windows Forms에 배경 이미지 추가](http://msdn.microsoft.com/en-us/7a509ba2-055c-4ae6-b88a-54625c6d9aff)합니다.  
  
#### <a name="to-define-icons"></a>아이콘을 정의 하려면  
  
1.  코드 편집기에서 다음 코드를 삽입은 `StackView` 클래스 정의 합니다. 이 코드에 대 한 비트맵을 초기화는 <xref:System.Windows.Forms.ToolStripButton> 아이콘입니다.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#2)]  
  
2.  에 대 한 호출 추가 `InitializeImages` 에서 메서드는 `StackView` 클래스 생성자입니다.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]  
  
## <a name="implementing-a-custom-renderer"></a>사용자 지정 렌더러를 구현합니다.  
 대부분의 요소를 사용자 지정할 수는 `StackView` 에서 파생 되는 클래스를 구현 제어는 <xref:System.Windows.Forms.ToolStripRenderer> 클래스입니다. 이 절차에서는 구현는 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 그립을 사용자 지정 하며 그라데이션 배경을 그리는 <xref:System.Windows.Forms.ToolStripButton> 컨트롤입니다.  
  
#### <a name="to-implement-a-custom-renderer"></a>사용자 지정 렌더러를 구현 하려면  
  
1.  에 다음 코드를 삽입는 `StackView` 정의 제어 합니다.  
  
     이 대 한 정의는 `StackRenderer` 재정의 하는 <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>, <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder>, 및 <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> 메서드를 사용자 지정 모양을 생성 합니다.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#10)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#10)]  
  
2.  에 `StackView` 컨트롤의 생성자의 새 인스턴스를 만들고는 `StackRenderer` 클래스 하 고이 인스턴스를 할당는 `stackStrip` 컨트롤의 <xref:System.Windows.Forms.ToolStrip.Renderer%2A> 속성입니다.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]  
  
## <a name="testing-the-stackview-control"></a>StackView 컨트롤 테스트  
 `StackView` 컨트롤에서 파생 되는 <xref:System.Windows.Forms.UserControl> 클래스입니다. 따라서 사용 하 여 컨트롤을 테스트할 수 있습니다는 **UserControl Test Container**합니다. 자세한 내용은 [방법: UserControl의 런타임 동작 테스트](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)를 참조하세요.  
  
#### <a name="to-test-the-stackview-control"></a>StackView 컨트롤을 테스트 하려면  
  
1.  F5 키를 눌러 프로젝트를 빌드하고 시작 하는 **UserControl Test Container**합니다.  
  
2.  단추 위로 포인터를 이동는 `StackView` 컨트롤을 선택한 상태로의 모양을 보려면 단추를 클릭 합니다.  
  
## <a name="next-steps"></a>다음 단계  
 이 연습에서는 Office XP 컨트롤의 전문적인 모양으로 다시 사용할 수 있는 사용자 지정 클라이언트 컨트롤을 만들었습니다. 사용할 수는 <xref:System.Windows.Forms.ToolStrip> 패밀리 등과 같은 용도로 컨트롤:  
  
-   사용자 컨트롤에 대 한 바로 가기 메뉴 만들기 <xref:System.Windows.Forms.ContextMenuStrip>합니다. 자세한 내용은 참조 [ContextMenu 구성 요소 개요](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md)합니다.  
  
-   자동으로 채워지는 표준 메뉴가 있는 폼을 만듭니다. 자세한 내용은 참조 [연습: 폼에 표준 메뉴 항목 제공](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md)합니다.  
  
-   도킹 된 다중 문서 MDI (인터페이스) 폼 만들기 <xref:System.Windows.Forms.ToolStrip> 컨트롤입니다. 자세한 내용은 참조 [하는 방법: 메뉴 병합 및 ToolStrip 컨트롤 MDI 폼 만들기](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [ToolStrip 컨트롤](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)  
 [방법: 양식에 표준 메뉴 항목 제공](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md)
