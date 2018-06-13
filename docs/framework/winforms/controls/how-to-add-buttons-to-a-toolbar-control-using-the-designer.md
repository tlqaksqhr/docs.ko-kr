---
title: '방법: 디자이너를 사용하여 ToolBar 컨트롤에 단추 추가'
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding separators
- examples [Windows Forms], toolbars
- ToolBar control [Windows Forms], adding drop-down menus
ms.assetid: d9ce3040-3e21-4e2d-80ae-b430982b2db8
ms.openlocfilehash: e90732329a0d78421d09da1c405ed93d5cb82f23
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527536"
---
# <a name="how-to-add-buttons-to-a-toolbar-control-using-the-designer"></a>방법: 디자이너를 사용하여 ToolBar 컨트롤에 단추 추가
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStrip> 컨트롤은 <xref:System.Windows.Forms.ToolBar> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.ToolBar> 컨트롤을 계속 유지하도록 선택할 수 있습니다.  
  
 핵심은 <xref:System.Windows.Forms.ToolBar> 컨트롤은 단추를 추가 합니다. 또는 메뉴 명령에 쉽게 액세스할을 사용할 수 있습니다 이러한 또는 명령을 메뉴 구조에서 사용할 수 없는 사용자에 게 노출 하는 응용 프로그램의 사용자 인터페이스의 다른 영역에 배치 될 수 있습니다.  
  
 다음 절차를 수행 하려면는 **Windows 응용 프로그램** 포함 된 폼을 사용 하 여 프로젝트는 <xref:System.Windows.Forms.ToolBar> 제어 합니다. 이러한 프로젝트 설정에 대 한 정보를 참조 하십시오. [하는 방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [하는 방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-add-buttons-at-design-time"></a>디자인 타임에 단추를 추가 하려면  
  
1.  <xref:System.Windows.Forms.ToolBar> 컨트롤을 선택합니다.  
  
2.  에 **속성** 창 클릭는 <xref:System.Windows.Forms.ToolBar.Buttons%2A> 속성을 선택 하 고 클릭는 **줄임표** (![VisualStudioEllipsesButton 스크린 샷] (../../../../docs/framework/winforms/media/vbellipsesbutton.png " vbEllipsesButton")) 버튼을 클릭은 **ToolBarButton 컬렉션 편집기**합니다.  
  
3.  사용 하 여는 **추가** 및 **제거** 단추에서 추가 하거나 제거 하는 단추는 <xref:System.Windows.Forms.ToolBar> 제어 합니다.  
  
4.  에 있는 개별 단추의 속성을 구성에서 **속성** 편집기의 오른쪽에 있는 창에 나타나는 창입니다. 다음 표에서 고려해 야 할 몇 가지 중요 한 속성을 보여 줍니다.  
  
    |속성|설명|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A>|드롭다운 목록 도구 모음 단추에 표시할 메뉴를 설정 합니다. 도구 모음 단추 <xref:System.Windows.Forms.ToolBarButton.Style%2A> 속성으로 설정 되어 있어야 <xref:System.Windows.Forms.ToolBarButtonStyle.DropDownButton>합니다. 이 속성의 인스턴스를 사용 하는 <xref:System.Windows.Forms.ContextMenu> 클래스를 참조 합니다.|  
    |<xref:System.Windows.Forms.ToolBarButton.PartialPush%2A>|토글 스타일 도구 모음 단추 부분적으로 눌린 있는지 여부를 설정 합니다. 도구 모음 단추 <xref:System.Windows.Forms.ToolBarButton.Style%2A> 속성으로 설정 되어 있어야 <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton>합니다.|  
    |<xref:System.Windows.Forms.ToolBarButton.Pushed%2A>|토글 스타일 도구 모음 단추 현재 푸시된 상태에 있는지 여부를 설정 합니다. 도구 모음 단추 <xref:System.Windows.Forms.ToolBarButton.Style%2A> 속성으로 설정 되어 있어야 <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton> 또는 <xref:System.Windows.Forms.ToolBarButtonStyle.PushButton>합니다.|  
    |<xref:System.Windows.Forms.ToolBarButton.Style%2A>|도구 모음 단추 스타일을 설정합니다. 값 중 하나 여야 합니다는 <xref:System.Windows.Forms.ToolBarButtonStyle> 열거형입니다.|  
    |<xref:System.Windows.Forms.ToolBarButton.Text%2A>|단추에 표시 되는 텍스트 문자열입니다.|  
    |<xref:System.Windows.Forms.ToolBarButton.ToolTipText%2A>|단추의 도구 설명으로 표시 되는 텍스트입니다.|  
  
5.  클릭 **확인** 을 대화 상자를 닫고을 지정한 패널을 만듭니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.ToolBar>  
 [방법: ToolBar 단추의 아이콘 정의](../../../../docs/framework/winforms/controls/how-to-define-an-icon-for-a-toolbar-button.md)  
 [방법: Toolbar 단추의 메뉴 이벤트 트리거](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)  
 [ToolBar 컨트롤 개요](../../../../docs/framework/winforms/controls/toolbar-control-overview-windows-forms.md)  
 [ToolBar 컨트롤](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)
