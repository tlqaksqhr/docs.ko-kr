---
title: "소유자가 그린 기본 제공 컨트롤 지원 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "그리기, 소유자"
  - "그리기, 사용자 지정"
  - "컨트롤 [Windows Forms] 모양 변경"
  - "사용자 지정 그리기"
  - "소유자 그리기"
ms.assetid: 3823d01e-9610-43e6-864d-99f9b7c2b351
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 소유자가 그린 기본 제공 컨트롤 지원
사용자 지정 그리기 라고도 하는 Windows Forms에 그리기 소유자는 특정 컨트롤의 시각적 모양을 변경 하는 것에 대 한 기술입니다.  
  
> [!NOTE]
>  이 항목의 "컨트롤" 라는 단어가 클래스 중 하나에서 파생 되는 데 사용 됩니다 <xref:System.Windows.Forms.Control> 또는 <xref:System.ComponentModel.Component>합니다.  
  
 일반적으로 Windows 그리기는 자동으로 처리와 같은 속성 설정을 사용 하 여 <xref:System.Windows.Forms.Control.BackColor%2A> 하는 컨트롤의 모양을 결정 합니다. 소유자 그리기를 사용 하면 인계 그리기 프로세스 모양의 속성을 사용 하 여 사용할 수 없는 요소를 변경 합니다. 예를 들어 많은 컨트롤이 표시 되는 텍스트의 색을 설정할 수 있지만 한 색으로 제한 됩니다. 소유자 그리기를 사용 하면 검정과 빨간색에서 부분에서 텍스트의 일부를 표시 하는 같은 작업을 수행할 수 있습니다.  
  
 실제로 소유자 그리기은 폼에 그래픽을 그리는 비슷합니다. 폼의에 대 한 처리기에서 그래픽 메서드를 사용할 수는 예를 들어 <xref:System.Windows.Forms.Control.Paint> 에뮬레이션 하는 이벤트는 `ListBox` 컨트롤 이지만 하면 모든 사용자 상호 작용을 처리 하는 코드를 작성 해야 합니다. 소유자 그리기를 컨트롤 코드를 사용 하 여 해당 내용을 그리는 데 있지만 내장 기능을 모두 유지 합니다. 각 항목의 다른 측면에 대 한 기본 모양을 사용 하는 동안 각 항목의 일부 측면을 사용자 지정 하거나 컨트롤의 각 항목을 그릴 수 있는 그래픽 메서드를 사용할 수 있습니다.  
  
## <a name="owner-drawing-in-windows-forms-controls"></a>소유자 그리기 windows에서 Forms 컨트롤  
 이 지 원하는 컨트롤의 소유자 그리기를 수행 하려면 일반적으로 하나의 속성을 설정를 하나 이상의 이벤트를 처리 합니다.  
  
 대부분의 컨트롤 그리기를 지원 소유자에 게는 `OwnerDraw` 또는 `DrawMode` 컨트롤 자체가 그려질 때 해당 그리기 관련 이벤트를 발생시킬지 여부를 나타내는 속성입니다.  
  
 가 없는 컨트롤은 `OwnerDraw` 또는 `DrawMode` 속성에는 `DataGridView` 자동으로 발생 하는 그리기 이벤트를 제공 하는 컨트롤 및 `ToolStrip` 컨트롤에는 자체 그리기 관련 이벤트는 외부 렌더링 클래스를 사용 하 여 그려집니다.  
  
 다양 한 종류의 그리기 이벤트가 있지만 컨트롤 내에서 단일 항목을 끌 수 있도록 일반적인 그리기 이벤트가 발생 합니다. 이벤트 처리기는 `EventArgs` 도구 그리고 항목에 대 한 정보를 포함 하는 개체는 그리기에 사용할 수 있습니다. 예를 들어,이 개체는 부모 컬렉션에서 항목의 인덱스 번호를 일반적으로 포함 한 <xref:System.Drawing.Rectangle> 항목의 경계를 표시 하는 것이 나타내는 및 <xref:System.Drawing.Graphics> 그리기 메서드를 호출 하는 것에 대 한 개체입니다. 일부 이벤트는 `EventArgs` 개체를 배경이 나 포커스 영역을 같은 기본적으로 항목의 일부 측면을 그리는 호출할 수 있는 메서드와 항목에 대 한 추가 정보를 제공 합니다.  
  
 소유자가 그린 사용자 지정 항목을 포함 하는 재사용 가능한 컨트롤을 만들려면 소유자 그리기를 지원 되는 컨트롤 클래스에서 파생 되는 새 클래스를 만듭니다. 그리기 이벤트를 처리 하는 대신 적절 한 작업에 대 한 재정의에 소유자 그리기 코드를 포함 `On` *EventName* 메서드 또는 새 클래스입니다. 기본 클래스를 호출 하십시오 `On` *EventName* 이 경우 메서드별로 컨트롤 사용자가 소유자 그리기 이벤트를 처리 하 고 추가 사용자 지정을 제공할 수 있도록 합니다.  
  
 다음 Windows Forms 소유자를 지 원하는 모든 버전의.NET Framework에서 그리기를 제어 합니다.  
  
-   <xref:System.Windows.Forms.ListBox>  
  
-   <xref:System.Windows.Forms.ComboBox>  
  
-   <xref:System.Windows.Forms.MenuItem> (에서 사용 하는 <xref:System.Windows.Forms.MainMenu> 및 <xref:System.Windows.Forms.ContextMenu>)  
  
-   <xref:System.Windows.Forms.TabControl>  
  
 다음 컨트롤은 지원 에서만 소유자 그리기 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]:  
  
-   <xref:System.Windows.Forms.ToolTip>  
  
-   <xref:System.Windows.Forms.ListView>  
  
-   <xref:System.Windows.Forms.TreeView>  
  
 다음 컨트롤의 새로운 되며 소유자 그리기를 지원 합니다. [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]:  
  
-   <xref:System.Windows.Forms.DataGridView>  
  
-   <xref:System.Windows.Forms.ToolStrip>  
  
 다음 섹션에서는 이러한 각각의이 컨트롤에 대 한 추가 세부 정보를 제공 합니다.  
  
### <a name="listbox-and-combobox-controls"></a>목록 상자 및 콤보 상자 컨트롤  
 <xref:System.Windows.Forms.ListBox> 및 <xref:System.Windows.Forms.ComboBox> 컨트롤을 사용 하면 다양 한 크기 또는 하나의 크기에 모든 컨트롤의 개별 항목을 그릴 수 있습니다.  
  
> [!NOTE]
>  하지만 <xref:System.Windows.Forms.CheckedListBox> 컨트롤에서 파생 되는 <xref:System.Windows.Forms.ListBox> 컨트롤을 지원 하지 않는 소유자 그리기.  
  
 그리려면 각 항목을 같은 크기로 설정 합니다는 `DrawMode` 속성을 <xref:System.Windows.Forms.DrawMode> 처리는 `DrawItem` 이벤트입니다.  
  
 다른 크기를 사용 하 여 각 항목을 그리려면 설정의 `DrawMode` 속성을 <xref:System.Windows.Forms.DrawMode> 모두 처리는 `MeasureItem` 및 `DrawItem` 이벤트입니다. `MeasureItem` 이벤트 앞에 있는 항목의 크기를 나타낼 수 있습니다는 `DrawItem` 해당 항목에 대 한 이벤트가 발생 합니다.  
  
 코드 예제를 비롯 한 자세한 내용은 다음 항목을 참조 합니다.  
  
-   <xref:System.Windows.Forms.ListBox.DrawMode%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.ListBox.MeasureItem?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.ListBox.DrawItem?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.ComboBox.DrawMode%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.ComboBox.MeasureItem?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.ComboBox.DrawItem?displayProperty=fullName>  
  
-   [방법: ComboBox 컨트롤에서 가변 크기 텍스트 만들기](../../../../docs/framework/winforms/controls/how-to-create-variable-sized-text-in-a-combobox-control.md)  
  
### <a name="menuitem-component"></a>MenuItem 구성 요소  
 <xref:System.Windows.Forms.MenuItem> 의 단일 메뉴 항목을 나타내는 구성 요소는 <xref:System.Windows.Forms.MainMenu> 또는 <xref:System.Windows.Forms.ContextMenu> 구성 요소입니다.  
  
 그릴는 <xref:System.Windows.Forms.MenuItem>설정, 해당 `OwnerDraw` 속성을 `true` 처리 하 고 해당 `DrawItem` 이벤트입니다. 앞에 나오는 메뉴 항목의 크기를 사용자 지정 하는 `DrawItem` 이벤트가 발생 하면 항목의 처리 `MeasureItem` 이벤트입니다.  
  
 코드 예제를 비롯 한 자세한 내용은 다음 참조 항목을 참조 하십시오.  
  
-   <xref:System.Windows.Forms.MenuItem.OwnerDraw%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.MenuItem.DrawItem?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.MenuItem.MeasureItem?displayProperty=fullName>  
  
### <a name="tabcontrol-control"></a>TabControl 컨트롤  
 <xref:System.Windows.Forms.TabControl> 컨트롤을 사용 하면 컨트롤에서 개별 탭을 그릴 수 있습니다. 소유자 그리기; 탭을 영향을 줍니다. <xref:System.Windows.Forms.TabPage> 내용에 영향을 받지 않습니다.  
  
 각 탭에 그릴 수는 <xref:System.Windows.Forms.TabControl>설정는 `DrawMode` 속성을 <xref:System.Windows.Forms.TabDrawMode> 처리는 `DrawItem` 이벤트입니다. 이 이벤트는 탭이 컨트롤에서 표시 하는 경우에 각 탭에 대해 한 번 발생 합니다.  
  
 코드 예제를 비롯 한 자세한 내용은 다음 참조 항목을 참조 하십시오.  
  
-   <xref:System.Windows.Forms.TabControl.DrawMode%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.TabControl.DrawItem?displayProperty=fullName>  
  
### <a name="tooltip-component"></a>ToolTip 구성 요소  
 <xref:System.Windows.Forms.ToolTip> 구성 요소를 사용 하면 표시 되 면 도구 설명 전체를 그릴 수 있습니다.  
  
 그릴는 <xref:System.Windows.Forms.ToolTip>설정, 해당 `OwnerDraw` 속성을 `true` 처리 하 고 해당 `Draw` 이벤트입니다. 크기를 사용자 지정 하는 <xref:System.Windows.Forms.ToolTip> 하기 전에 `Draw` 이벤트가 발생 하면 처리는 `Popup` 이벤트 집합과 <xref:System.Windows.Forms.PopupEventArgs.ToolTipSize%2A> 이벤트 처리기에서 속성입니다.  
  
 코드 예제를 비롯 한 자세한 내용은 다음 참조 항목을 참조 하십시오.  
  
-   <xref:System.Windows.Forms.ToolTip.OwnerDraw%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.ToolTip.Draw?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.ToolTip.Popup?displayProperty=fullName>  
  
### <a name="listview-control"></a>ListView 컨트롤  
 <xref:System.Windows.Forms.ListView> 컨트롤을 사용 하면 컨트롤에서 개별 항목, 하위 항목 및 열 머리글을 그릴 수 있습니다.  
  
 소유자 그리기 컨트롤에서을 사용 하려면는 `OwnerDraw` 속성을 `true`합니다.  
  
 컨트롤의 각 항목을 그리려면 처리는 `DrawItem` 이벤트입니다.  
  
 컨트롤에서 각 하위 항목 또는 열 머리글을 그릴 때는 <xref:System.Windows.Forms.ListView.View%2A> 속성이 <xref:System.Windows.Forms.View>, 처리는 `DrawSubItem` 및 `DrawColumnHeader` 이벤트입니다.  
  
 코드 예제를 비롯 한 자세한 내용은 다음 참조 항목을 참조 하십시오.  
  
-   <xref:System.Windows.Forms.ListView.OwnerDraw%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.ListView.DrawItem?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.ListView.DrawSubItem?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.ListView.DrawColumnHeader?displayProperty=fullName>  
  
### <a name="treeview-control"></a>TreeView 컨트롤  
 <xref:System.Windows.Forms.TreeView> 컨트롤을 사용 하면 컨트롤의 개별 노드를 그릴 수 있습니다.  
  
 각 노드에 표시 되는 텍스트에만 그리려면 설정는 `DrawMode` 속성을 <xref:System.Windows.Forms.TreeViewDrawMode> 처리는 `DrawNode` 이벤트 텍스트를 그릴 합니다.  
  
 각 노드의 모든 요소를 그리려면 설정는 `DrawMode` 속성을 <xref:System.Windows.Forms.TreeViewDrawMode> 처리는 `DrawNode` 텍스트, 아이콘, 확인란, 더하기 및 빼기 기호, 같은 및 노드를 연결 하는 선 필요한 모든 요소를 그리는 데는 이벤트입니다.  
  
 코드 예제를 비롯 한 자세한 내용은 다음 참조 항목을 참조 하십시오.  
  
-   <xref:System.Windows.Forms.TreeView.DrawMode%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.TreeView.DrawNode?displayProperty=fullName>  
  
### <a name="datagridview-control"></a>DataGridView 컨트롤  
 <xref:System.Windows.Forms.DataGridView> 컨트롤을 사용 하면 컨트롤에서 개별 셀 및 행을 그릴 수 있습니다.  
  
 개별 셀을 그리려면 처리는 `CellPainting` 이벤트입니다.  
  
 개별 행 이나 행의 요소를 그리려면 중 하나 또는 모두를 처리는 `RowPrePaint` 및 `RowPostPaint` 이벤트입니다. `RowPrePaint` 이벤트는 행의 셀은 그립니다 되기 전에 발생 하며 `RowPostPaint` 이벤트는 셀이 그려진 후에 발생 합니다. 두 이벤트를 처리할 수 및 `CellPainting` 별도로 행 배경, 개별 셀 및 행 전경을 그리는 데는 이벤트 또는 있습니다 필요 하 고 행의 다른 요소에 대 한 기본 표시를 사용 하 여 특정 사용자 지정을 제공할 수 있습니다.  
  
 코드 예제를 비롯 한 자세한 내용은 다음 항목을 참조 합니다.  
  
-   <xref:System.Windows.Forms.DataGridView.CellPainting>  
  
-   <xref:System.Windows.Forms.DataGridView.RowPrePaint>  
  
-   <xref:System.Windows.Forms.DataGridView.RowPostPaint>  
  
-   [방법: Windows Forms DataGridView 컨트롤에서 셀의 모양을 사용자 지정](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md)  
  
-   [방법: Windows Forms DataGridView 컨트롤에서 행의 모양을 사용자 지정](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md)  
  
### <a name="toolstrip-control"></a>ToolStrip 컨트롤  
 <xref:System.Windows.Forms.ToolStrip> 및 파생 된 컨트롤을 사용 하면 표시 되는 모든 측면을 사용자 지정할 수 있습니다.  
  
 에 대 한 사용자 지정 렌더링을 제공 하기 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 설정는 `Renderer` 속성은 <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripManager>, <xref:System.Windows.Forms.ToolStripPanel>, 또는 <xref:System.Windows.Forms.ToolStripContentPanel> 에 `ToolStripRenderer` 개체를 하나 이상에서 제공 하는 여러 그리기 이벤트 처리는 `ToolStripRenderer` 클래스. 설정 또는 `Renderer` 에서 파생 된 속성을 사용자 지정 클래스의 인스턴스로 `ToolStripRenderer`, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>, 또는 <xref:System.Windows.Forms.ToolStripSystemRenderer> 구현 하거나 특정 재정의 `On` *EventName* 메서드.  
  
 코드 예제를 비롯 한 자세한 내용은 다음 항목을 참조 합니다.  
  
-   <xref:System.Windows.Forms.ToolStripRenderer>  
  
-   [방법: Windows Forms의 ToolStrip 컨트롤에 대 한 사용자 지정 렌더러를 설정 하 고 만들기](../../../../docs/framework/winforms/controls/create-and-set-a-custom-renderer-for-the-toolstrip-control-in-wf.md)  
  
-   [방법: ToolStrip 컨트롤 그리기 사용자 지정](../../../../docs/framework/winforms/controls/how-to-custom-draw-a-toolstrip-control.md)  
  
## <a name="see-also"></a>참고 항목  
 [Windows Forms에서 사용할 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)