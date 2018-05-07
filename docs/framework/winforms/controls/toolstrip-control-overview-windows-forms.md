---
title: ToolStrip 컨트롤 개요(Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- Toolstrip
helpviewer_keywords:
- ToolStrip control [Windows Forms], about ToolStrip control
- toolbars [Windows Forms], what's new in Windows Forms
- toolbars [Windows Forms]
- what's new [Windows Forms], toolbars
ms.assetid: 81d067ed-297c-4dad-90de-1bcac15336ec
ms.openlocfilehash: 3927f180e738541f2f2f8af6d03d281f6a601167
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="toolstrip-control-overview-windows-forms"></a>ToolStrip 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.ToolStrip> 컨트롤과 연결 된 클래스 도구 모음, 상태 표시줄 및 메뉴에 사용자 인터페이스 요소를 결합 하기 위한 공통 프레임 워크를 제공 합니다. <xref:System.Windows.Forms.ToolStrip> 컨트롤에 가로 또는 세로 공간을 공유할 수 있는 도구 모음에 내부 활성화 및 편집, 사용자 지정 레이아웃 및 래프팅 (rafting)을 포함 하는 풍부한 디자인 타임 환경을 제공 합니다.  
  
 하지만 <xref:System.Windows.Forms.ToolStrip> 대체 하 고 이전 버전에서 컨트롤에 기능을 추가 <xref:System.Windows.Forms.ToolBar> 원하는 경우 이전 버전과 호환성을 유지 합니다.  
  
## <a name="features-of-the-toolstrip-controls"></a>ToolStrip 컨트롤의 기능  
 사용 하 여는 <xref:System.Windows.Forms.ToolStrip> 를 제어 합니다.  
  
-   컨테이너 간에 공통 사용자 인터페이스를 제공 합니다.  
  
-   쉽게 사용자 지정 된, 지 원하는 일반적인된 도구 모음 고급 사용자 인터페이스 및 레이아웃 기능을 텍스트 및 이미지, 드롭다운 단추 및 컨트롤 도킹, 래프팅 (rafting), 단추, 등 오버플로 단추 및 다시 정렬 런타임에 <xref:System.Windows.Forms.ToolStrip> 항목입니다.  
  
-   오버플로 및 런타임 항목 다시 정렬을 지원 합니다. 오버플로 기능 이동 항목 드롭다운 메뉴에 공간이 충분 하지 않은 경우는 <xref:System.Windows.Forms.ToolStrip>합니다.  
  
-   일반적인 모양 및 동작의 일반적인 렌더링 모델을 통해 운영 체제를 지원 합니다.  
  
-   다른 컨트롤에 대 한 이벤트를 처리 하는 동일한 방식으로, 모든 컨테이너 및 포함 된 항목에는 일관성 있게 이벤트를 처리 합니다.  
  
-   항목을 끌어올 <xref:System.Windows.Forms.ToolStrip> 간 또는 한 <xref:System.Windows.Forms.ToolStrip>합니다.  
  
-   고급 레이아웃으로 드롭다운 목록 컨트롤 및 사용자 인터페이스 형식 편집기를 만듭니다는 <xref:System.Windows.Forms.ToolStripDropDown>합니다.  
  
 사용 하 여는 <xref:System.Windows.Forms.ToolStripControlHost> 에 다른 컨트롤을 사용 하는 클래스는 <xref:System.Windows.Forms.ToolStrip> 깨고 <xref:System.Windows.Forms.ToolStrip> 기능을 합니다.  
  
 기능을 확장 하 고 사용 하 여 모양 및 동작을 수정할 수 있습니다는 <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>, 및 <xref:System.Windows.Forms.ToolStripManager> 와 함께 <xref:System.Windows.Forms.ToolStripRenderMode> 및 <xref:System.Windows.Forms.ToolStripManagerRenderMode> 열거형입니다.  
  
 <xref:System.Windows.Forms.ToolStrip> 컨트롤은 고도로 구성 가능 하며 확장 가능 하 고 여러 속성, 메서드 및 모양 및 동작을 사용자 지정 하는 이벤트를 제공 합니다. 다음은 몇 가지 중요 한 멤버입니다.  
  
### <a name="important-toolstrip-members"></a>중요 한 ToolStrip 멤버  
  
|이름|설명|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStrip.Dock%2A>|부모 컨테이너의 가장자리를 가져오거나 설정 합니다.는 <xref:System.Windows.Forms.ToolStrip> 에 도킹 합니다.|  
|<xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>|<xref:System.Windows.Forms.ToolStrip> 클래스를 통해 끌어서 놓기와 항목 다시 정렬을 전용으로 처리할지를 나타내는 값을 가져오거나 설정합니다.|  
|<xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A>|나타내는 값을 가져오거나 방법을 <xref:System.Windows.Forms.ToolStrip> 항목을 레이아웃 하 합니다.|  
|<xref:System.Windows.Forms.ToolStripItem.Overflow%2A>|가져오거나 여부는 <xref:System.Windows.Forms.ToolStripItem> 에 연결 되어는 <xref:System.Windows.Forms.ToolStrip> 또는 <xref:System.Windows.Forms.ToolStripOverflowButton> 둘 사이 부동 수 또는 합니다.|  
|<xref:System.Windows.Forms.ToolStrip.IsDropDown%2A>|나타내는 값을 가져옵니다 여부는 <xref:System.Windows.Forms.ToolStripItem> 드롭다운 목록에서 다른 항목을 표시할지 때 목록을 <xref:System.Windows.Forms.ToolStripItem> 를 클릭 합니다.|  
|<xref:System.Windows.Forms.ToolStrip.OverflowButton%2A>|오버플로가 활성화된 <xref:System.Windows.Forms.ToolStrip>에 대한 오버플로 단추인 <xref:System.Windows.Forms.ToolStripItem>을 가져옵니다.|  
|<xref:System.Windows.Forms.ToolStrip.Renderer%2A>|가져오거나는 <xref:System.Windows.Forms.ToolStripRenderer> 모양 및 동작 (모양 및 느낌)의 사용자 지정 하는 데 사용 된 <xref:System.Windows.Forms.ToolStrip>합니다.|  
|<xref:System.Windows.Forms.ToolStrip.RenderMode%2A>|그리기 스타일을 적용할 수를 가져오거나 설정 합니다.는 <xref:System.Windows.Forms.ToolStrip>합니다.|  
|<xref:System.Windows.Forms.ToolStrip.RendererChanged>|발생 시기는 <xref:System.Windows.Forms.ToolStrip.Renderer%2A> 속성 변경 합니다.|  
  
 <xref:System.Windows.Forms.ToolStrip> 컨트롤의 유연성은 다양 한 도우미 클래스를 사용 하 여 수행 됩니다. 다음은 몇 가지 가장 중요 합니다.  
  
### <a name="important-toolstrip-companion-classes"></a>ToolStrip에 중요 한 역할 클래스  
  
|이름|설명|  
|----------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip>|대체 하 고 여기에 새로운 기능이 추가 된 <xref:System.Windows.Forms.MainMenu> 클래스입니다.|  
|<xref:System.Windows.Forms.StatusStrip>|대체 하 고 여기에 새로운 기능이 추가 된 <xref:System.Windows.Forms.StatusBar> 클래스입니다.|  
|<xref:System.Windows.Forms.ContextMenuStrip>|대체 하 고 여기에 새로운 기능이 추가 된 <xref:System.Windows.Forms.ContextMenu> 클래스입니다.|  
|<xref:System.Windows.Forms.ToolStripItem>|이벤트 및 모든 요소에 대 한 레이아웃 관리 되는 추상 기본 클래스는 한 <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripControlHost>, 또는 <xref:System.Windows.Forms.ToolStripDropDown> 포함 될 수 있습니다.|  
|<xref:System.Windows.Forms.ToolStripContainer>|다양 한 방법으로 제어를 정렬할 수 있는 폼의 양쪽에 패널에는 컨테이너를 제공 합니다.|  
|<xref:System.Windows.Forms.ToolStripRenderer>|그리기 기능을 처리 <xref:System.Windows.Forms.ToolStrip> 개체입니다.|  
|<xref:System.Windows.Forms.ToolStripProfessionalRenderer>|Microsoft Office 스타일 모양을 제공합니다.|  
|<xref:System.Windows.Forms.ToolStripManager>|컨트롤 <xref:System.Windows.Forms.ToolStrip> 렌더링 및 래프팅 및 병합을 <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ToolStripDropDownMenu>, 및 <xref:System.Windows.Forms.ToolStripMenuItem> 개체입니다.|  
|<xref:System.Windows.Forms.ToolStripManagerRenderMode>|여러에 적용 된 그리기 스타일 (사용자 지정, Windows XP 또는 Microsoft Office Professional)을 지정 <xref:System.Windows.Forms.ToolStrip> 폼에 포함 된 개체입니다.|  
|<xref:System.Windows.Forms.ToolStripRenderMode>|하나에 적용 된 그리기 스타일 (사용자 지정, Windows XP 또는 Microsoft Office Professional)을 지정 <xref:System.Windows.Forms.ToolStrip> 폼에 포함 된 개체입니다.|  
|<xref:System.Windows.Forms.ToolStripControlHost>|구체적으로 다른 컨트롤을 호스트 <xref:System.Windows.Forms.ToolStrip> 컨트롤 하지만 보려는 <xref:System.Windows.Forms.ToolStrip> 기능입니다.|  
|<xref:System.Windows.Forms.ToolStripItemPlacement>|지정 여부는 <xref:System.Windows.Forms.ToolStripItem> 주 배치 하는 <xref:System.Windows.Forms.ToolStrip>, 오버플로 <xref:System.Windows.Forms.ToolStrip>, 하거나 둘 다 합니다.|  
  
 자세한 내용은 참조 [ToolStrip 기술 요약](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md) 및 [ToolStrip 컨트롤 아키텍처](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 <xref:System.Windows.Forms.ToolStripItem>  
 <xref:System.Windows.Forms.ToolStripDropDown>
