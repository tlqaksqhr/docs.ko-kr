---
title: "연습: 폼에 표준 메뉴 항목 제공"
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
- menu items [Windows Forms], standard
- toolbars [Windows Forms], walkthroughs
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: dac37d98-589e-4d6d-9673-6437e8943122
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 89089617a62ab079dd4cccf3ddf6e1e774bac8ba
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a>연습: 폼에 표준 메뉴 항목 제공
<xref:System.Windows.Forms.MenuStrip> 컨트롤을 사용하여 폼에 표준 메뉴를 제공할 수 있습니다.  
  
 이 연습에서는 사용 하는 방법을 보여 줍니다.는 <xref:System.Windows.Forms.MenuStrip> 표준 메뉴를 만들 수 있습니다. 사용자가 메뉴 항목을 선택할 때에 폼 응답 합니다. 같은 작업을이 연습에서 설명 합니다.  
  
-   Windows Forms 프로젝트를 만드는 중입니다.  
  
-   표준 메뉴를 만듭니다.  
  
-   만들기는 <xref:System.Windows.Forms.StatusStrip> 제어 합니다.  
  
-   메뉴 항목 선택을 처리 합니다.  
  
 작업을 완료 하는 경우 메뉴 항목에서 표시 하는 표준 메뉴를 사용 하 여 폼 것는 <xref:System.Windows.Forms.StatusStrip> 제어 합니다.  
  
 단일 목록으로이 항목의 코드를 복사 하려면 참조 [하는 방법: 폼에 표준 메뉴 항목 제공](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md)합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 완료하려면 다음 사항이 필요합니다.  
  
-   만들고 컴퓨터에 Windows Forms 응용 프로그램 프로젝트를 실행할 수 있는 충분 한 권한이 있는 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] 가 설치 되어 있습니다.  
  
## <a name="creating-the-project"></a>프로젝트 만들기  
 첫 번째 단계는 프로젝트를 만들고 폼을 설정하는 것입니다.  
  
#### <a name="to-create-the-project"></a>프로젝트를 만들려면  
  
1.  호출 하는 Windows 응용 프로그램 프로젝트 만들기 **StandardMenuForm**합니다.  
  
     자세한 내용은 [방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)를 참조하세요.  
  
2.  Windows Forms 디자이너에서 폼을 선택 합니다.  
  
## <a name="creating-a-standard-menu"></a>표준 메뉴 만들기  
 Windows Forms 디자이너가 자동으로 채울 수는 <xref:System.Windows.Forms.MenuStrip> 표준 메뉴 항목 컨트롤입니다.  
  
#### <a name="to-create-a-standard-menu"></a>표준 메뉴를 만들려면  
  
1.  **도구 상자**를 끌어 한 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 폼으로 합니다.  
  
2.  클릭는 <xref:System.Windows.Forms.MenuStrip> 컨트롤의 스마트 태그 문자 모양 (![스마트 태그 문자 모양](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))을 선택 하 고 **표준 항목 삽입**합니다.  
  
     <xref:System.Windows.Forms.MenuStrip> 컨트롤이 표준 메뉴 항목으로 채워집니다.  
  
3.  클릭는 **파일** 메뉴 항목의 기본 메뉴 항목과 해당 아이콘을 확인 합니다.  
  
## <a name="creating-a-statusstrip-control"></a>StatusStrip 컨트롤 만들기  
 사용 된 <xref:System.Windows.Forms.StatusStrip> 컨트롤에 Windows Forms 응용 프로그램에 대 한 상태를 표시 합니다. 현재 예제에서는 사용자가 선택한 메뉴 항목에 표시 됩니다는 <xref:System.Windows.Forms.StatusStrip> 제어 합니다.  
  
#### <a name="to-create-a-statusstrip-control"></a>StatusStrip 컨트롤을 만들려면  
  
1.  **도구 상자**를 끌어 한 <xref:System.Windows.Forms.StatusStrip> 컨트롤을 폼으로 합니다.  
  
     <xref:System.Windows.Forms.StatusStrip> 자동으로 폼의 아래쪽에 도킹 합니다.  
  
2.  클릭는 <xref:System.Windows.Forms.StatusStrip> 컨트롤의 드롭다운 단추 및 선택 **StatusLabel** 추가 하는 <xref:System.Windows.Forms.ToolStripStatusLabel> 컨트롤을 <xref:System.Windows.Forms.StatusStrip> 제어 합니다.  
  
## <a name="handling-item-selection"></a>항목 선택 처리  
 처리는 <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> 이벤트를 사용자가 메뉴 항목을 선택할 때 응답 합니다.  
  
#### <a name="to-handle-item-selection"></a>항목 선택을 처리 하려면  
  
1.  클릭는 **파일** 메뉴 항목 만들기에서 만든 표준 메뉴 섹션.  
  
2.  에 **속성** 창 클릭 **이벤트**합니다.  
  
3.  두 번 클릭 하 여 <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> 이벤트입니다.  
  
     Windows Forms 디자이너에 대 한 이벤트 처리기가 생성 된 <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> 이벤트입니다.  
  
4.  이벤트 처리기에 다음 코드를 삽입 합니다.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]  
  
5.  삽입 된 `UpdateStatus` 양식에 유틸리티 메서드 정의 합니다.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]  
  
## <a name="checkpoint"></a>검사점  
  
#### <a name="to-test-your-form"></a>폼을 테스트 하려면  
  
1.  F5 키를 눌러를 컴파일 및 폼을 실행 합니다.  
  
2.  클릭는 **파일** 메뉴 항목 메뉴를 엽니다.  
  
3.  에 **파일** 메뉴에서 선택 항목 중 하나를 클릭 합니다.  
  
     <xref:System.Windows.Forms.StatusStrip> 컨트롤 선택한 항목을 표시 합니다.  
  
## <a name="next-steps"></a>다음 단계  
 이 연습에서는 표준 메뉴가 있는 폼을 만들었습니다. 사용할 수는 <xref:System.Windows.Forms.ToolStrip> 패밀리 등과 같은 용도로 컨트롤:  
  
-   사용자 컨트롤에 대 한 바로 가기 메뉴 만들기 <xref:System.Windows.Forms.ContextMenuStrip>합니다. 자세한 내용은 참조 [ContextMenu 구성 요소 개요](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md)합니다.  
  
-   도킹 된 다중 문서 MDI (인터페이스) 폼 만들기 <xref:System.Windows.Forms.ToolStrip> 컨트롤입니다. 자세한 내용은 참조 [연습: 메뉴 병합 및 ToolStrip 컨트롤을 사용 하 여 MDI 폼 만들기](../../../../docs/framework/winforms/controls/walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)합니다.  
  
-   지정 하면 <xref:System.Windows.Forms.ToolStrip> 전문적인 모양 제어 합니다. 자세한 내용은 참조 [하는 방법: 응용 프로그램에 대 한 ToolStrip 렌더러 설정](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [MenuStrip 컨트롤](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)
