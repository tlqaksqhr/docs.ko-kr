---
title: "방법: 디자이너를 사용하여 도구 모음 단추의 아이콘 정의"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- toolbars [Windows Forms], adding icons to buttons
- examples [Windows Forms], toolbars
- images [Windows Forms], toolbar buttons
- buttons [Windows Forms], images
- icons [Windows Forms], toolbar buttons
- ToolBar control [Windows Forms], adding icons to buttons
ms.assetid: d848f38e-67f2-49d4-8e88-01c845c06c02
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 90e72b2516efab3bc5b5d8cc7cacb66f149f3a66
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-define-an-icon-for-a-toolbar-button-using-the-designer"></a>방법: 디자이너를 사용하여 도구 모음 단추의 아이콘 정의
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStrip> 컨트롤은 <xref:System.Windows.Forms.ToolBar> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.ToolBar> 컨트롤을 계속 유지하도록 선택할 수 있습니다.  
  
 <xref:System.Windows.Forms.ToolBar>단추는 사용자가 쉽게 식별 하기 위해 그 안에서 아이콘을 표시할 수 있습니다. 이미지에 추가 통해 그렇게는 <xref:System.Windows.Forms.ImageList> 구성 요소에 연결 합니다는 <xref:System.Windows.Forms.ToolBar> 제어 합니다.  
  
 다음 절차를 수행 하려면는 **Windows 응용 프로그램** 포함 된 폼을 사용 하 여 프로젝트는 <xref:System.Windows.Forms.ToolBar> 제어 및 <xref:System.Windows.Forms.ImageList> 구성 요소입니다. 이러한 프로젝트 설정에 대 한 정보를 참조 하십시오. [하는 방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [하는 방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-set-an-icon-for-a-toolbar-button-at-design-time"></a>디자인 타임에 도구 모음 단추의 아이콘을 설정 하려면  
  
1.  에 이미지를 추가 <xref:System.Windows.Forms.ImageList> 구성 요소입니다. 자세한 내용은 참조 [하는 방법: 디자이너와 ImageList 이미지 추가 또는 제거](../../../../docs/framework/winforms/controls/how-to-add-or-remove-imagelist-images-with-the-designer.md)합니다.  
  
2.  선택 된 <xref:System.Windows.Forms.ToolBar> 폼의 컨트롤로 합니다.  
  
3.  에 **속성** 창의 설정는 <xref:System.Windows.Forms.ToolBar> 컨트롤의 <xref:System.Windows.Forms.ToolBar.ImageList%2A> 속성을는 <xref:System.Windows.Forms.ImageList> 구성 요소입니다.  
  
4.  클릭는 <xref:System.Windows.Forms.ToolBar> 컨트롤의 <xref:System.Windows.Forms.ToolBar.Buttons%2A> 속성을 선택 하 고 줄임표를 클릭 (![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton"))는 열려는단추**ToolBarButton 컬렉션 편집기**합니다.  
  
5.  사용 하 여는 **추가** 단추를 추가 하는 단추는 <xref:System.Windows.Forms.ToolBar> 제어 합니다.  
  
6.  에 **속성** 창 오른쪽에 있는 창에 표시 되는 **ToolBarButton 컬렉션 편집기**설정는 <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> 속성 목록에서 값 중 하나를 각 도구 모음 단추는 에 추가 하는 이미지에서 출발 하 여 <xref:System.Windows.Forms.ImageList> 구성 요소입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.ToolBar>  
 [방법: Toolbar 단추의 메뉴 이벤트 트리거](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)  
 [ToolBar 컨트롤](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)  
 [ImageList 구성 요소](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)
