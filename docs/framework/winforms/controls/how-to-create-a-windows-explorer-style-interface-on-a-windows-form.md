---
title: "방법: Windows Form에 Windows 탐색기 스타일 인터페이스 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Explorer [Windows Forms], creating with Windows Forms
- SplitContainer control [Windows Forms], Explorer-style interface
- forms [Windows Forms], Windows Explorer type
ms.assetid: 9a3d5f4f-5dda-4350-9ad5-57ce5976dc47
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 96f2ca8189d6840bc68f063ef9b97539c24b0e6c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-windows-explorerstyle-interface-on-a-windows-form"></a>방법: Windows Form에 Windows 탐색기 스타일 인터페이스 만들기
Windows 탐색기는 쉽게 사용할 수 있으므로 응용 프로그램을 일반 사용자 인터페이스 선택입니다.  
  
 Windows 탐색기는 기본적으로, 한 <xref:System.Windows.Forms.TreeView> 제어 및 <xref:System.Windows.Forms.ListView> 별도 패널에는 컨트롤입니다. 패널은 분할자 여 조정할 수 있습니다. 이 컨트롤 배열을 표시 하 고 정보를 찾는를 매우 효율적입니다.  
  
 다음 단계에는 Windows 탐색기와 유사한 폼에서에서 컨트롤을 정렬 하는 방법을 보여 줍니다. Windows 탐색기 응용 프로그램의 파일 검색 기능을 추가 하는 방법을 표시 하지 않습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-create-a-windows-explorer-style-windows-form"></a>Windows 탐색기 스타일 Windows Form을 만들려면  
  
1.  새 Windows 응용 프로그램 프로젝트를 만듭니다. 자세한 내용은 [방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)를 참조하세요.  
  
2.  **도구 상자**:  
  
    1.  끌어서는 <xref:System.Windows.Forms.SplitContainer> 컨트롤을 폼으로 합니다.  
  
    2.  끌어서는 <xref:System.Windows.Forms.TreeView> 컨트롤을 **SplitterPanel1** (의 패널은 <xref:System.Windows.Forms.SplitContainer> 표시 제어 **패널 1**).  
  
    3.  끌어서는 <xref:System.Windows.Forms.ListView> 컨트롤을 **SplitterPanel2** (의 패널은 <xref:System.Windows.Forms.SplitContainer> 표시 제어 **Panel2**).  
  
3.  CTRL 키를 차례로 클릭 하 여 모든 세 가지 컨트롤을 선택 합니다. 선택 하는 경우는 <xref:System.Windows.Forms.SplitContainer> 제어 패널 보다는 분할 막대를 클릭 합니다.  
  
    > [!NOTE]
    >  사용 하지 않는 **모두 선택** 명령을 **편집** 메뉴. 이렇게 하면 다음 단계에 필요한 속성이에 표시 되지 것입니다는 **속성** 창.  
  
4.  에 **속성** 창에서 설정 된 <xref:System.Windows.Forms.SplitContainer.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Fill>합니다.  
  
5.  F5 키를 눌러 응용 프로그램을 실행합니다.  
  
     폼의 Windows 탐색기와 비슷한 두 부분으로 구성 사용자 인터페이스를 표시합니다.  
  
    > [!NOTE]
    >  분할자를 끌 때 패널 크기가 자동으로 조정 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.SplitContainer>  
 [방법: Windows Forms으로 다중 창 사용자 인터페이스 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-multipane-user-interface-with-windows-forms.md)  
 [방법: 분할 창에서 크기 조정 및 위치 지정 동작 정의](../../../../docs/framework/winforms/controls/how-to-define-resize-and-positioning-behavior-in-a-split-window.md)  
 [방법: 가로로 창 분할](../../../../docs/framework/winforms/controls/how-to-split-a-window-horizontally.md)  
 [SplitContainer 컨트롤](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)
