---
title: Windows Forms MenuStrip 컨트롤의 메뉴 항목 병합
ms.date: 03/30/2017
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- merging [Windows Forms], general concepts
ms.assetid: 95e113ba-f362-4dda-8a76-6d95ddc45cee
ms.openlocfilehash: 2782ae483d673f8f1eccab10876aca858737260a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="merging-menu-items-in-the-windows-forms-menustrip-control"></a>Windows Forms MenuStrip 컨트롤의 메뉴 항목 병합
(mdi 다중) 다중 문서 인터페이스 응용 프로그램의 경우 부모 폼의 메뉴에 메뉴 항목이 나 자식 폼에서 전체 메뉴를 병합할 수 있습니다.  
  
 이 항목에서는 MDI 응용 프로그램에서 메뉴 항목 병합에 연결 된 기본 개념을 설명 합니다.  
  
## <a name="general-concepts"></a>일반 개념  
 대상 및 소스 제어 병합 과정에 포함 됩니다.  
  
-   대상이 <xref:System.Windows.Forms.MenuStrip> 를 병합 하는 메뉴 항목 main 또는 MDI 부모 폼에 컨트롤입니다.  
  
-   원본이 <xref:System.Windows.Forms.MenuStrip> 병합할 대상 메뉴에 메뉴 항목이 포함 된 MDI 자식 폼에서 컨트롤입니다.  
  
 <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> 속성은 현재 MDI의 제목으로 채울 드롭다운 목록이 해당 부모 폼의 MDI 자식 메뉴 항목을 식별 합니다. 예를 들어 목록을 일반적으로에서 현재 열려 있는 MDI 자식 폼의 **창** 메뉴.  
  
 <xref:System.Windows.Forms.ToolStripMenuItem.IsMdiWindowListEntry%2A> 속성에서 제공 되는 메뉴 항목을 식별 한 <xref:System.Windows.Forms.MenuStrip> MDI 자식 폼에 있습니다.  
  
 수동 또는 자동으로 메뉴 항목을 병합할 수 있습니다. 두 방법에 대 한 동일한 방식으로 메뉴 항목 병합 하지만 병합이이 항목의 뒷부분에 나오는 "수동 병합" 및 "자동 병합" 섹션에 설명 된 대로 다르게 활성화 됩니다. 각 병합 작업을 수동 및 자동 병합, 다음 병합 작업을 영향을 줍니다.  
  
 <xref:System.Windows.Forms.MenuStrip> 하나에서 메뉴 항목을 이동 병합 <xref:System.Windows.Forms.ToolStrip> 다른 경우와 같이 복제 하는 대신 <xref:System.Windows.Forms.MainMenu>합니다.  
  
## <a name="mergeaction-values"></a>MergeAction 값  
 메뉴 항목 소스에 대해 병합 작업을 설정할 <xref:System.Windows.Forms.MenuStrip> 를 사용 하는 <xref:System.Windows.Forms.MergeAction> 속성입니다.  
  
 다음 표에서 사용할 수 있는 병합 작업의 의미와 일반적인 용도 설명합니다.  
  
|MergeAction 값|설명|일반적인 용도|  
|-----------------------|-----------------|-----------------|  
|<xref:System.Windows.Forms.MergeAction.Append>|(기본값) 대상 항목 컬렉션의 끝에 소스 항목을 추가합니다.|프로그램의 특정 부분 활성화 될 때 메뉴의 끝에 메뉴 항목을 추가 합니다.|  
|<xref:System.Windows.Forms.MergeAction.Insert>|소스 항목으로 지정 된 위치에서 대상 항목의 컬렉션에 추가 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> 소스 항목에서 속성을 설정 합니다.|중간 이나 프로그램의 특정 부분 활성화 될 때 메뉴의 시작 부분에 메뉴 항목을 추가 합니다.<br /><br /> 하는 경우의 값 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> 동일 메뉴 항목 모두에 대해 추가 된 반대 순서로 합니다. 설정 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> 적절 하 게 원래 순서를 보존 합니다.|  
|<xref:System.Windows.Forms.MergeAction.Replace>|일치 하는 텍스트를 찾거나 사용 하 여는 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> 값이 텍스트 일치 항목이 없는 발견 되 고 원본 메뉴 항목과 일치 하는 대상 메뉴 항목을 다음으로 바꿉니다.|이름이 같은 다른 작업을 수행 하는 소스 메뉴 항목 대상 메뉴 항목을 대체 됩니다.|  
|<xref:System.Windows.Forms.MergeAction.MatchOnly>|일치 하는 텍스트를 찾거나 사용 하 여는 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> 값이 텍스트 일치 항목이 없는 발견 되 고 대상에 원본의 모든 드롭다운 목록 항목을 추가 합니다.|메뉴 구조를 구축 삽입 되 또는 하위 메뉴에 메뉴 항목을 추가 하거나 하위 메뉴에서 메뉴 항목을 제거 합니다. 기본에서 MDI 자식 메뉴 항목을 추가할 수는 예를 들어 <xref:System.Windows.Forms.MenuStrip> **다른 이름으로 저장** 메뉴.<br /><br /> <xref:System.Windows.Forms.MergeAction.MatchOnly> 작업을 수행 하지 않고 메뉴 구조를 탐색할 수 있습니다. 다음 항목을 평가 하는 방법을 제공 합니다.|  
|<xref:System.Windows.Forms.MergeAction.Remove>|일치 하는 텍스트를 찾거나 사용 하 여는 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> 값이 텍스트 일치 항목이 없는 발견 되 고 다음 항목을 대상에서 제거 합니다.|대상에서 메뉴 항목을 제거 <xref:System.Windows.Forms.MenuStrip>합니다.|  
  
## <a name="manual-merging"></a>수동 병합  
 만 <xref:System.Windows.Forms.MenuStrip> 컨트롤이 자동 병합에 참여 합니다. 와 같은 다른 컨트롤의 항목을 결합 하 <xref:System.Windows.Forms.ToolStrip> 및 <xref:System.Windows.Forms.StatusStrip> 컨트롤을 병합 해야 해당를 직접 호출 하 여는 <xref:System.Windows.Forms.ToolStripManager.Merge%2A> 및 <xref:System.Windows.Forms.ToolStripManager.RevertMerge%2A> 필요에 따라 코드 메서드.  
  
## <a name="automatic-merging"></a>자동 병합  
 소스 폼을 활성화 하 여 MDI 응용 프로그램에 대 한 자동 병합을 사용할 수 있습니다. 사용 하는 <xref:System.Windows.Forms.MenuStrip> MDI 응용 프로그램 설정의 <xref:System.Windows.Forms.Form.MainMenuStrip%2A> 속성을 대상 <xref:System.Windows.Forms.MenuStrip> 소스에 병합 작업이 수행 되도록 <xref:System.Windows.Forms.MenuStrip> 대상에 반영 <xref:System.Windows.Forms.MenuStrip>합니다.  
  
 활성화 하 여 자동 병합을 트리거할 수 있습니다는 <xref:System.Windows.Forms.MenuStrip> MDI 소스에서 합니다. 활성화 되 면 원본 <xref:System.Windows.Forms.MenuStrip> MDI 대상 파티션으로 병합 되며 병합 합니다. 새 폼 활성화 되 면 마지막 폼에 병합 되돌아가고 새 폼에 트리거됩니다. 설정 하 여이 동작을 제어할 수는 <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> 각 필요에 따라 속성 <xref:System.Windows.Forms.ToolStripItem>를 설정 하 여는 <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> 각 속성 <xref:System.Windows.Forms.MenuStrip>합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.ToolStripManager>  
 <xref:System.Windows.Forms.MenuStrip>  
 [MenuStrip 컨트롤](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)  
 [방법: MenuStrip이 포함된 MDI 창 목록 만들기](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md)  
 [방법: MDI 응용 프로그램의 자동 메뉴 병합 설정](../../../../docs/framework/winforms/controls/how-to-set-up-automatic-menu-merging-for-mdi-applications.md)
