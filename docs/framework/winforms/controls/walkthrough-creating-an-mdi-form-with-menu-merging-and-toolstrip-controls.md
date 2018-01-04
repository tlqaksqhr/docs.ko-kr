---
title: "연습: 메뉴 병합 및 ToolStrip 컨트롤을 사용하여 MDI 폼 만들기"
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
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms]
- MDI [Windows Forms], creating forms
- multiple document interface forms
- MDI forms
- ToolStrip control [Windows Forms]
- MDI forms [Windows Forms], creating
- MDI forms [Windows Forms], walkthroughs
ms.assetid: fbab4221-74af-42d0-bbf4-3c97f7b2e544
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b170c3e3311dbbfb070a66107bd4f22407647bae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a>연습: 메뉴 병합 및 ToolStrip 컨트롤을 사용하여 MDI 폼 만들기
<xref:System.Windows.Forms?displayProperty=nameWithType> 네임스페이스는 MDI(다중 문서 인터페이스) 응용 프로그램을 지원하고 <xref:System.Windows.Forms.MenuStrip> 컨트롤은 메뉴 병합을 지원합니다. MDI 폼은 <xref:System.Windows.Forms.ToolStrip> 컨트롤일 수도 있습니다.  
  
 이 연습에서는 사용 하는 방법을 보여 줍니다. <xref:System.Windows.Forms.ToolStripPanel> MDI 폼을 사용 하 여 컨트롤입니다. 폼은 자식 메뉴와 메뉴 병합도 지원합니다. 같은 작업을이 연습에서 설명 합니다.  
  
-   Windows Forms 프로젝트를 만드는 중입니다.  
  
-   폼에 대 한 주 메뉴 만들기 메뉴의 실제 이름 달라 집니다.  
  
-   추가 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 **도구 상자**합니다.  
  
-   자식 폼 만들기  
  
-   정렬 <xref:System.Windows.Forms.ToolStripPanel> z 순서를 기준으로 컨트롤입니다.  
  
 작업을 완료 하는 경우 메뉴 병합 및 이동할 수 있는 지 원하는 MDI 폼 것 <xref:System.Windows.Forms.ToolStrip> 컨트롤입니다.  
  
 단일 목록으로이 항목의 코드를 복사 하려면 참조 [하는 방법: 메뉴 병합 및 ToolStrip 컨트롤 MDI 폼 만들기](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 완료하려면 다음 사항이 필요합니다.  
  
-   만들고 컴퓨터에 Windows Forms 응용 프로그램 프로젝트를 실행할 수 있는 충분 한 권한이 있는 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] 가 설치 되어 있습니다.  
  
## <a name="creating-the-project"></a>프로젝트 만들기  
 첫 번째 단계는 프로젝트를 만들고 폼을 설정하는 것입니다.  
  
#### <a name="to-create-the-project"></a>프로젝트를 만들려면  
  
1.  호출 하는 Windows 응용 프로그램 프로젝트 만들기 **MdiForm**합니다.  
  
     자세한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)을 참조하세요.  
  
2.  Windows Forms 디자이너에서 폼을 선택 합니다.  
  
3.  속성 창에서 설정의 값은 <xref:System.Windows.Forms.Form.IsMdiContainer%2A> 를 `true`합니다.  
  
## <a name="creating-the-main-menu"></a>주 메뉴 만들기  
 MDI 부모 폼의 주 메뉴를 포함합니다. 주 메뉴에는 하나의 이라는 메뉴 항목이 **창**합니다. 와 **창** 메뉴 항목을 자식 폼을 만들 수 있습니다. 주 메뉴에 자식 폼의 메뉴 항목 병합 됩니다.  
  
#### <a name="to-create-the-main-menu"></a>주 메뉴를 만들려면  
  
1.  **도구 상자**를 끌어 한 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 폼으로 합니다.  
  
2.  추가 <xref:System.Windows.Forms.ToolStripMenuItem> 에 <xref:System.Windows.Forms.MenuStrip> 제어 하 고 이름을 **창**합니다.  
  
3.  <xref:System.Windows.Forms.MenuStrip> 컨트롤을 선택합니다.  
  
4.  속성 창에서 설정의 값은 <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> 속성을 `ToolStripMenuItem1`합니다.  
  
5.  하위 항목을 추가 **창** 메뉴 항목을 선택한 후 이름을 하위 항목 **새로**합니다.  
  
6.  속성 창에서 클릭 **이벤트**합니다.  
  
7.  두 번 클릭 하 여 <xref:System.Windows.Forms.ToolStripItem.Click> 이벤트입니다.  
  
     Windows Forms 디자이너에 대 한 이벤트 처리기가 생성 된 <xref:System.Windows.Forms.ToolStripItem.Click> 이벤트입니다.  
  
8.  이벤트 처리기에 다음 코드를 삽입 합니다.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]  
  
## <a name="adding-the-toolstrippanel-control-to-the-toolbox"></a>ToolStripPanel 컨트롤을 도구 상자에 추가  
 사용 하는 경우 <xref:System.Windows.Forms.MenuStrip> 있어야 MDI 폼을 사용 하 여 컨트롤의 <xref:System.Windows.Forms.ToolStripPanel> 제어 합니다. 추가 해야 합니다는 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 **도구 상자** Windows Forms 디자이너에서 MDI 폼을 작성 합니다.  
  
#### <a name="to-add-the-toolstrippanel-control-to-the-toolbox"></a>ToolStripPanel 컨트롤을 도구 상자에 추가 하려면  
  
1.  열기는 **도구 상자**, 클릭 하 고는 **모든 Windows Forms** 탭을 사용할 수 있는 Windows Forms 컨트롤을 표시 합니다.  
  
2.  바로 가기 메뉴를 열려면 마우스 오른쪽 단추로 클릭 하 고 선택 **항목 선택**합니다.  
  
3.  에 **도구 상자 항목 선택** 대화 상자에서 아래쪽으로 스크롤하여는 **이름** 열을 찾을 때까지 **ToolStripPanel**합니다.  
  
4.  확인란을 선택 **ToolStripPanel**, 클릭 하 고 **확인**합니다.  
  
     <xref:System.Windows.Forms.ToolStripPanel> 컨트롤이에 표시 되는 **도구 상자**합니다.  
  
## <a name="creating-a-child-form"></a>자식 폼 만들기  
 이 절차에서는 별도 자식 폼 클래스에는 자체를 정의 합니다 <xref:System.Windows.Forms.MenuStrip> 제어 합니다. 이 폼에 대 한 메뉴 항목 부모 폼의 병합 됩니다.  
  
#### <a name="to-define-a-child-form"></a>자식 폼을 정의 하려면  
  
1.  라는 새 폼을 추가 `ChildForm` 프로젝트에 있습니다.  
  
     자세한 내용은 참조 [하는 방법: Windows Forms 프로젝트에 추가](http://msdn.microsoft.com/en-us/3d7bb25f-fd90-47cf-9378-fa0d764686c1)합니다.  
  
2.  **도구 상자**를 끌어 한 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 자식 폼입니다.  
  
3.  클릭는 <xref:System.Windows.Forms.MenuStrip> 컨트롤의 스마트 태그 문자 모양 (![스마트 태그 문자 모양](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))를 선택한 후 **항목 편집**합니다.  
  
4.  에 **항목 컬렉션 편집기** 대화 상자에서 새 추가 <xref:System.Windows.Forms.ToolStripMenuItem> 라는 **ChildMenuItem** 하위 메뉴에 있습니다.  
  
     자세한 내용은 참조 [ToolStrip 항목 컬렉션 편집기](http://msdn.microsoft.com/en-us/e681f3ab-94ba-4b2b-ac64-1dfad46caa25)합니다.  
  
## <a name="testing-the-form"></a>테스트 폼  
  
#### <a name="to-test-your-form"></a>폼을 테스트 하려면  
  
1.  F5 키를 눌러를 컴파일 및 폼을 실행 합니다.  
  
2.  클릭는 **창** 메뉴 항목을 클릭 하 고 메뉴를 연 **새로**합니다.  
  
     새 자식 폼을 폼의 MDI 클라이언트 영역에서 만들어집니다. 자식 폼의 메뉴가 주 메뉴와 병합 됩니다.  
  
3.  자식 폼을 닫습니다.  
  
     자식 폼의 메뉴가 주 메뉴에서 제거 됩니다.  
  
4.  클릭 **새로** 여러 번입니다.  
  
     자식 폼 W가 자동으로 나열**창** 때문에 메뉴 항목의 <xref:System.Windows.Forms.MenuStrip> 컨트롤의 <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> 속성에 할당 됩니다.  
  
## <a name="adding-toolstrip-support"></a>ToolStrip 지원 추가  
 이 절차에서 추가한 4 <xref:System.Windows.Forms.ToolStrip> MDI 부모 폼에 컨트롤을 합니다. 각 <xref:System.Windows.Forms.ToolStrip> 내부 컨트롤에 추가 됩니다 한 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 폼의 가장자리에 도킹 됩니다.  
  
#### <a name="to-add-toolstrip-controls-to-the-mdi-parent-form"></a>ToolStrip 컨트롤 MDI 부모 폼을 추가 하려면  
  
1.  **도구 상자**를 끌어 한 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 폼으로 합니다.  
  
2.  와 <xref:System.Windows.Forms.ToolStripPanel> 선택 컨트롤을 두 번 클릭은 <xref:System.Windows.Forms.ToolStrip> 컨트롤에 **도구 상자**합니다.  
  
     A <xref:System.Windows.Forms.ToolStrip> 컨트롤에서 만드는 <xref:System.Windows.Forms.ToolStripPanel> 제어 합니다.  
  
3.  <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 선택합니다.  
  
4.  속성 창에서 컨트롤의 값을 변경 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Left>합니다.  
  
     <xref:System.Windows.Forms.ToolStripPanel> 주 메뉴 아래 폼의 왼쪽에 도킹을 제어 합니다. MDI 클라이언트 영역에 맞게 조정 된 <xref:System.Windows.Forms.ToolStripPanel> 제어 합니다.  
  
5.  1-4 단계를 반복 합니다.  
  
     새 도킹 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 폼의 맨 위로 이동 합니다.  
  
     <xref:System.Windows.Forms.ToolStripPanel> 주 메뉴 아래 하지만 첫 번째의 오른쪽에 컨트롤 도킹 <xref:System.Windows.Forms.ToolStripPanel> 제어 합니다. 이 단계 올바른 배치에 z 순서의 중요성을 보여 줍니다. <xref:System.Windows.Forms.ToolStripPanel> 컨트롤입니다.  
  
6.  두 개 이상의 대해 1-4 단계를 반복 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤입니다.  
  
     새 도킹 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 폼의 아래쪽에 있습니다.  
  
## <a name="arranging-toolstrippanel-controls-by-z-order"></a>ToolStripPanel 컨트롤 Z 순서 정렬  
 도킹 된 위치 <xref:System.Windows.Forms.ToolStripPanel> MDI 폼의 컨트롤을 z-순서에서 컨트롤의 위치에 따라 결정 됩니다. 문서 개요 창에서 컨트롤의 z 순서를 쉽게 정렬할 수 있습니다.  
  
#### <a name="to-arrange-toolstrippanel-controls-by-z-order"></a>Z 순서 ToolStripPanel 컨트롤을 정렬 하려면  
  
1.  에 **보기** 메뉴를 클릭 **다른 창**, 클릭 하 고 **문서 개요**합니다.  
  
     배열을 프로그램 <xref:System.Windows.Forms.ToolStripPanel> 이전 절차에서 컨트롤은 표준이 아닙니다. 즉, z-순서 올바르지 않습니다. 컨트롤의 z 순서를 변경 하려면 문서 개요 창을 사용 합니다.  
  
2.  문서 개요 창에서 선택한 **ToolStripPanel4**합니다.  
  
3.  아래쪽 화살표 단추를 클릭 때까지 반복 해 서 **ToolStripPanel4** 목록의 아래쪽에 있습니다.  
  
     **ToolStripPanel4** 컨트롤이 다른 컨트롤 아래 폼의 아래쪽에 도킹 합니다.  
  
4.  선택 **ToolStripPanel2**합니다.  
  
5.  목록에서 세 번째 컨트롤을 이동 하려면 아래쪽 화살표 단추 한 번 클릭 합니다.  
  
     **ToolStripPanel2** 컨트롤 주 메뉴 아래 및 다른 컨트롤 위에 폼의 위쪽에 도킹 합니다.  
  
6.  다양 한 컨트롤을 선택는 **문서 개요** 창이 z-순서에서 다른 위치로 이동 하 고 있습니다. Note z-순서 도킹 된 컨트롤의 배치에 미치는 영향입니다. CTRL + Z를 사용 하 여 또는 **실행 취소** 에 **편집** 변경 내용을 취소 하는 메뉴입니다.  
  
## <a name="checkpoint"></a>검사점  
  
#### <a name="to-test-your-form"></a>폼을 테스트 하려면  
  
1.  F5 키를 눌러를 컴파일 및 폼을 실행 합니다.  
  
2.  그립을 클릭 한 <xref:System.Windows.Forms.ToolStrip> 제어 하 고 양식에서 컨트롤을 다른 위치로 끕니다.  
  
     끌 수는 <xref:System.Windows.Forms.ToolStrip> 하나에서 제어 <xref:System.Windows.Forms.ToolStripPanel> 다른 제어 합니다.  
  
## <a name="next-steps"></a>다음 단계  
 이 연습에서 사용 하 여 MDI 부모 폼을 만든 <xref:System.Windows.Forms.ToolStrip> 컨트롤과 메뉴 병합 합니다. 사용할 수는 <xref:System.Windows.Forms.ToolStrip> 패밀리 등과 같은 용도로 컨트롤:  
  
-   사용자 컨트롤에 대 한 바로 가기 메뉴 만들기 <xref:System.Windows.Forms.ContextMenuStrip>합니다. 자세한 내용은 참조 [ContextMenu 구성 요소 개요](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md)합니다.  
  
-   자동으로 채워지는 표준 메뉴를 사용 하 여 폼을 만든 합니다. 자세한 내용은 참조 [연습: 폼에 표준 메뉴 항목 제공](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md)합니다.  
  
-   지정 하면 <xref:System.Windows.Forms.ToolStrip> 전문적인 모양 제어 합니다. 자세한 내용은 참조 [하는 방법: 응용 프로그램에 대 한 ToolStrip 렌더러 설정](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [방법: MDI 상위 폼 만들기](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [방법: MDI 자식 폼 만들기](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [방법: MDI 드롭다운 메뉴에 MenuStrip 삽입](../../../../docs/framework/winforms/controls/how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)  
 [ToolStrip 컨트롤](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
