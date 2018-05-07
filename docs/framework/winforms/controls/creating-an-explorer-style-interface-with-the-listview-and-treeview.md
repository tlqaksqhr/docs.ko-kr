---
title: '연습: 디자이너를 사용하여 ListView 및 TreeView 컨트롤이 포함된 탐색기 스타일 인터페이스 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Explorer-style applications [Windows Forms], walkthroughs
- TreeView control [Windows Forms], ListView controls used with
- ListView control [Windows Forms], TreeView controls used with
- Explorer-style applications
- TreeView control [Windows Forms], using for explorer-style interface
- ListView control [Windows Forms], explorer style interface
- ListView control [Windows Forms], explorer-style interface
ms.assetid: 9e5e7721-19e2-4890-b273-a43589fe99ff
ms.openlocfilehash: 0a0208194bd6cf24f61c58ece88e41b674e924fc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-creating-an-explorer-style-interface-with-the-listview-and-treeview-controls-using-the-designer"></a>연습: 디자이너를 사용하여 ListView 및 TreeView 컨트롤이 포함된 탐색기 스타일 인터페이스 만들기
Visual Studio의 이점 중 하나를 짧은 시간 안에 전문적인 Windows Forms 응용 프로그램을 만들 수입니다. 일반적인 시나리오는 만드는 사용자 인터페이스 (UI) <xref:System.Windows.Forms.ListView> 및 <xref:System.Windows.Forms.TreeView> Windows 운영 체제의 Windows 탐색기 기능을 제어 합니다. Windows 탐색기 사용자의 컴퓨터에 파일 및 폴더의 계층 구조를 표시합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-create-the-form-containing-a-listview-and-treeview-control"></a>ListView 및 TreeView 컨트롤이 포함 된 폼을 만들려면  
  
1.  **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.  
  
2.  에 **새 프로젝트** 대화 상자에서 다음을 수행 합니다.  
  
    1.  선택 된 범주에 **Visual Basic** 또는 **Visual C#** 합니다.  
  
    2.  템플릿 목록에서 선택 **Windows Forms 응용 프로그램**합니다.  
  
3.  **확인**을 클릭합니다. 새 Windows Forms 프로젝트가 만들어집니다.  
  
4.  추가 <xref:System.Windows.Forms.SplitContainer> 폼에 컨트롤을 설정 해당 <xref:System.Windows.Forms.SplitContainer.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Fill>합니다.  
  
5.  추가 <xref:System.Windows.Forms.ImageList> 라는 `imageList1` 를 폼과 두 개의 이미지를 추가 하려면 속성 창 사용 하 여: 폴더 이미지와 그 순서 대로 문서 이미지입니다.  
  
6.  추가 <xref:System.Windows.Forms.TreeView> 라는 컨트롤 `treeview1` 을 폼으로의 왼쪽에 배치 하 고는 <xref:System.Windows.Forms.SplitContainer> 제어 합니다. 에 대 한 속성 창에서 `treeView1` 에서 다음을 수행 합니다.  
  
    1.  <xref:System.Windows.Forms.Control.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Fill>으로 설정합니다.  
  
    2.  <xref:System.Windows.Forms.TreeView.ImageList%2A> 속성을 `imagelist1.`로 설정합니다.  
  
7.  추가 <xref:System.Windows.Forms.ListView> 라는 컨트롤 `listView1` 을 폼으로의 오른쪽에 놓습니다는 <xref:System.Windows.Forms.SplitContainer> 제어 합니다. 에 대 한 속성 창에서 `listview1` 에서 다음을 수행 합니다.  
  
    1.  <xref:System.Windows.Forms.Control.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Fill>으로 설정합니다.  
  
    2.  <xref:System.Windows.Forms.ListView.View%2A> 속성을 <xref:System.Windows.Forms.View.Details>으로 설정합니다.  
  
    3.  줄임표를 클릭 하 여 열 머리글 컬렉션 편집기를 엽니다 (![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton"))에 <xref:System.Windows.Forms.ListView.Columns%2A> 속성**합니다.** 3 개의 열을 추가 하 고 설정의 <xref:System.Windows.Forms.ColumnHeader.Text%2A> 속성을 `Name`, `Type`, 및 `Last Modified`각각. **확인** 을 클릭하여 대화 상자를 닫습니다.  
  
    4.  <xref:System.Windows.Forms.ListView.SmallImageList%2A> 속성을 `imageList1.`로 설정합니다.  
  
8.  채우는 코드를 구현는 <xref:System.Windows.Forms.TreeView> 노드 및 하위 노드를 사용 합니다. 이 코드를 추가 하는 `Form1` 클래스입니다.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#1)]  
  
9. 적절 한 사용 추가 또는 앞의 코드에서 System.IO 네임 스페이스를 사용 하 않으므로 폼의 위쪽에 문을 가져옵니다.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#4)]  
  
10. 폼의 생성자에서 이전 단계에서 설정 메서드를 호출 하거나 <xref:System.Windows.Forms.Form.Load> 이벤트 처리 메서드. 폼 생성자에이 코드를 추가 합니다.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#2)]  
  
11. 처리는 <xref:System.Windows.Forms.TreeView.NodeMouseClick> 이벤트에 대 한 `treeview1` **,** 채우는 코드를 구현 하 고 `listview1` 노드를 클릭할 때 노드 내용으로 합니다. 이 코드를 추가 하는 `Form1` 클래스입니다.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#3)]  
  
     C#을 사용 하는 경우 있는지 확인은 <xref:System.Windows.Forms.TreeView.NodeMouseClick> 와 해당 이벤트 처리 메서드에 연결 된 이벤트입니다. 폼 생성자에이 코드를 추가 합니다.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#5)]  
  
## <a name="testing-the-application"></a>응용 프로그램 테스트  
 이제 예상 대로 동작 되도록 폼을 테스트할 수 있습니다.  
  
#### <a name="to-test-the-form"></a>양식을 테스트 하려면  
  
-   F5 키를 눌러 응용 프로그램을 실행합니다.  
  
     포함 된 분할 폼에 표시 됩니다는 <xref:System.Windows.Forms.TreeView> 프로젝트 디렉터리의 왼쪽에 표시 하는 컨트롤 및 <xref:System.Windows.Forms.ListView> 세 열이 있는 오른쪽에는 컨트롤입니다. 이동할 수는 <xref:System.Windows.Forms.TreeView> 디렉터리 노드를 선택 하 여 및 <xref:System.Windows.Forms.ListView> 선택한 디렉터리의 내용으로 채워집니다.  
  
## <a name="next-steps"></a>다음 단계  
 이 응용 프로그램을 사용할 수는 방법의 예로 제공 <xref:System.Windows.Forms.TreeView> 및 <xref:System.Windows.Forms.ListView> 함께 제어 합니다. 이러한 컨트롤에 대 한 자세한 내용은 다음 항목을 참조 합니다.  
  
-   [방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가(Windows Forms)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)  
  
-   [방법: ListView 컨트롤에 검색 기능 추가](../../../../docs/framework/winforms/controls/how-to-add-search-capabilities-to-a-listview-control.md)  
  
-   [방법: TreeView 노드에 바로 가기 메뉴 연결](../../../../docs/framework/winforms/controls/how-to-attach-a-shortcut-menu-to-a-treeview-node.md)  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.TreeView>  
 [ListView 컨트롤](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [방법: Windows Forms TreeView 컨트롤을 사용하여 노드 추가 및 제거](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)  
 [방법: Windows Forms ListView 컨트롤을 사용하여 항목 추가 및 제거](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)  
 [방법: Windows Forms ListView 컨트롤에 열 추가](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)
