---
title: "방법: 디자이너를 사용하여 Windows Forms ListView 컨트롤에서 항목 추가 및 제거 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "ListView 컨트롤[Windows Forms], 목록 항목 추가"
  - "ListView 컨트롤[Windows Forms], 채우기"
ms.assetid: 217611ee-fd11-4d39-9a54-a37c3e781be1
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# 방법: 디자이너를 사용하여 Windows Forms ListView 컨트롤에서 항목 추가 및 제거
Windows Forms <xref:System.Windows.Forms.ListView> 컨트롤에 항목을 추가하는 프로세스는 주로 항목을 지정하고 이 항목에 속성을 할당하는 프로세스로 구성됩니다.  언제든지 목록 항목을 추가하거나 제거할 수 있습니다.  
  
 다음 절차를 수행하려면 <xref:System.Windows.Forms.ListView> 컨트롤이 포함된 폼이 있는 **Windows 응용 프로그램** 프로젝트가 필요합니다.  이러한 프로젝트를 설정하는 데 대한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)를 참조하십시오.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 디자이너를 사용하여 항목을 추가하거나 제거하려면  
  
1.  <xref:System.Windows.Forms.ListView> 컨트롤을 선택합니다.  
  
2.  **속성** 창에서 <xref:System.Windows.Forms.ListView.Items%2A> 속성 옆의 **줄임표**\(![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) 단추를 클릭합니다.  
  
     **ListViewItem 컬렉션 편집기**가 나타납니다.  
  
3.  항목을 추가하려면 **추가** 단추를 클릭합니다.  그런 다음 <xref:System.Windows.Forms.ListView.Text%2A> 및 <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> 속성과 같은 새 항목의 속성을 설정할 수 있습니다.  
  
4.  항목을 제거하려면 해당 항목을 선택한 다음 **제거** 단추를 클릭합니다.  
  
## 참고 항목  
 [ListView 컨트롤 개요](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)   
 [방법: Windows Forms ListView 컨트롤에 열 추가](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)   
 [방법: Windows Forms ListView 컨트롤을 사용하여 열에 하위 항목 표시](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)   
 [방법: Windows Forms ListView 컨트롤의 아이콘 표시](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)   
 [방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가\(Windows Forms\)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)   
 [방법: Windows Forms ListView 컨트롤에서 항목 그룹화](../../../../docs/framework/winforms/controls/how-to-group-items-in-a-windows-forms-listview-control.md)