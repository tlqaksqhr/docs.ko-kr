---
title: "연습: 디자이너를 사용하여 ListView 및 TreeView 컨트롤이 포함된 탐색기 스타일 인터페이스 만들기 | Microsoft Docs"
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
  - "탐색기 스타일 응용 프로그램"
  - "탐색기 스타일 응용 프로그램, 연습"
  - "ListView 컨트롤[Windows Forms], 탐색기 스타일 인터페이스"
  - "ListView 컨트롤[Windows Forms], explorer-style 인터페이스"
  - "ListView 컨트롤[Windows Forms], TreeView 컨트롤과 함께 사용"
  - "TreeView 컨트롤[Windows Forms], ListView 컨트롤과 함께 사용"
  - "TreeView 컨트롤[Windows Forms], 탐색기 스타일 인터페이스에 사용"
ms.assetid: 9e5e7721-19e2-4890-b273-a43589fe99ff
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# 연습: 디자이너를 사용하여 ListView 및 TreeView 컨트롤이 포함된 탐색기 스타일 인터페이스 만들기
Visual Studio의 장점 중 하나는 전문적인 Windows Forms 응용 프로그램을 신속하게 만들 수 있다는 것입니다.  일반적으로 Windows 운영 체제의 Windows 탐색기 기능과 유사한 <xref:System.Windows.Forms.ListView> 및 <xref:System.Windows.Forms.TreeView> 컨트롤로 UI\(사용자 인터페이스\)를 만듭니다.  Windows 탐색기에는 사용자 컴퓨터의 파일 및 폴더 계층 구조가 표시됩니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### ListView 및 TreeView 컨트롤이 포함된 폼을 만들려면  
  
1.  **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.  
  
2.  **새 프로젝트** 대화 상자에서 다음을 수행합니다.  
  
    1.  범주에서 **Visual Basic** 또는 **Visual C\#**을 선택합니다.  
  
    2.  템플릿 목록에서 **Windows Forms 응용 프로그램**을 선택합니다.  
  
3.  **확인**을 클릭합니다.  새 Windows Forms 프로젝트가 만들어집니다.  
  
4.  폼에 <xref:System.Windows.Forms.SplitContainer> 컨트롤을 추가하고 <xref:System.Windows.Forms.SplitContainer.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle>로 설정합니다.  
  
5.  `imageList1`이라는 <xref:System.Windows.Forms.ImageList>를 폼에 추가하고 속성 창을 사용하여 두 개의 이미지, 즉 폴더 이미지와 문서 이미지를 해당 순서로 추가합니다.  
  
6.  `treeview1`이라는 <xref:System.Windows.Forms.TreeView> 컨트롤을 폼에 추가하고 <xref:System.Windows.Forms.SplitContainer> 컨트롤의 왼쪽에 놓습니다.  `treeView1`에 대한 속성 창에서 다음을 수행합니다.  
  
    1.  <xref:System.Windows.Forms.Control.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle>으로 설정합니다.  
  
    2.  <xref:System.Windows.Forms.TreeView.ImageList%2A> 속성을 `imagelist1.`로 설정합니다.  
  
7.  `listView1`이라는 <xref:System.Windows.Forms.ListView> 컨트롤을 폼에 추가하고 <xref:System.Windows.Forms.SplitContainer> 컨트롤의 오른쪽에 놓습니다.  `listview1`에 대한 속성 창에서 다음을 수행합니다.  
  
    1.  <xref:System.Windows.Forms.Control.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle>으로 설정합니다.  
  
    2.  <xref:System.Windows.Forms.ListView.View%2A> 속성을 <xref:System.Windows.Forms.View>으로 설정합니다.  
  
    3.  <xref:System.Windows.Forms.ListView.Columns%2A> 속성의 줄임표\(![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\)를 클릭하여 ColumnHeader 컬렉션 편집기를 엽니다**.** 세 개의 열을 추가하고 해당 <xref:System.Windows.Forms.ColumnHeader.Text%2A> 속성을 `Name`, `Type` 및 `Last Modified`로 각각 설정합니다.  **확인**을 클릭하여 대화 상자를 닫습니다.  
  
    4.  <xref:System.Windows.Forms.ListView.SmallImageList%2A> 속성을 `imageList1.`로 설정합니다.  
  
8.  노드와 하위 노드로 <xref:System.Windows.Forms.TreeView>를 채우는 코드를 구현합니다.  `Form1` 클래스에 이 코드를 추가합니다.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#1)]  
  
9. 위 코드에서는 System.IO 네임스페이스를 사용하므로 폼 맨 위에 적절한 using 또는 import 문을 추가해야 합니다.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#4)]  
  
10. 폼의 생성자나 <xref:System.Windows.Forms.Form.Load> 이벤트 처리 메서드의 이전 단계에서 설정 메서드를 호출합니다.  폼 생성자에 이 코드를 추가합니다.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#2)]  
  
11. `treeview1` 에 대한 <xref:System.Windows.Forms.TreeView.NodeMouseClick> 이벤트를 처리한 다음 노드를 클릭하는 경우 노드의 내용으로`listview1`을채우는 코드를구현합니다.  `Form1` 클래스에 이 코드를 추가합니다.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#3)]  
  
     C\#을 사용하는 경우 <xref:System.Windows.Forms.TreeView.NodeMouseClick> 이벤트에 이벤트 처리 메서드를 연결해야 합니다.  폼 생성자에 이 코드를 추가합니다.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#5)]  
  
## 응용 프로그램 테스트  
 이제 폼을 테스트하여 예상한 대로 동작하는지 확인할 수 있습니다.  
  
#### 폼을 테스트하려면  
  
-   F5 키를 눌러 응용 프로그램을 실행합니다.  
  
     왼쪽에 프로젝트 디렉터리가 표시되는 <xref:System.Windows.Forms.TreeView> 컨트롤과 오른쪽에 세 개의 열을 포함하는 <xref:System.Windows.Forms.ListView> 컨트롤이 있는 분할 폼이 표시됩니다.  디렉터리 노드를 선택하여 <xref:System.Windows.Forms.TreeView>를 트래버스할 수 있으며<xref:System.Windows.Forms.ListView>에는 선택한 디렉터리의 내용이 채워집니다.  
  
## 다음 단계  
 이 응용 프로그램에서는 <xref:System.Windows.Forms.TreeView> 컨트롤과 <xref:System.Windows.Forms.ListView> 컨트롤을 함께 사용할 수 있는 방법에 대한 예를 보여 줍니다.  이러한 컨트롤에 대한 자세한 내용은 다음 항목을 참조하십시오.  
  
-   [방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가\(Windows Forms\)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)  
  
-   [방법: ListView 컨트롤에 검색 기능 추가](../../../../docs/framework/winforms/controls/how-to-add-search-capabilities-to-a-listview-control.md)  
  
-   [방법: TreeView 노드에 바로 가기 메뉴 연결](../../../../docs/framework/winforms/controls/how-to-attach-a-shortcut-menu-to-a-treeview-node.md)  
  
## 참고 항목  
 <xref:System.Windows.Forms.ListView>   
 <xref:System.Windows.Forms.TreeView>   
 [ListView 컨트롤](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)   
 [방법: Windows Forms TreeView 컨트롤을 사용하여 노드 추가 및 제거](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)   
 [방법: Windows Forms ListView 컨트롤을 사용하여 항목 추가 및 제거](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)   
 [방법: Windows Forms ListView 컨트롤에 열 추가](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)