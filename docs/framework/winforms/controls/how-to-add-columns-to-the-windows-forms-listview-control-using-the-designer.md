---
title: "방법: 디자이너를 사용하여 Windows Forms ListView 컨트롤에 열 추가 | Microsoft Docs"
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
  - "열[Windows Forms], ListView 컨트롤에 추가"
  - "ListView 컨트롤[Windows Forms], 열 머리글 추가"
ms.assetid: 5b1a8b4d-587e-479a-95c1-f9b90884f13a
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# 방법: 디자이너를 사용하여 Windows Forms ListView 컨트롤에 열 추가
Windows Forms <xref:System.Windows.Forms.ListView> 컨트롤을 사용하면 **자세히** 보기에서 각 목록 항목에 대해 여러 개의 열을 표시할 수 있습니다.  여러 개의 열을 사용하면 각 목록 항목에 대한 여러 유형의 정보를 표시할 수 있습니다.  예를 들어, 파일 목록에 파일 이름, 파일 형식, 파일 크기 및 파일을 마지막으로 수정한 날짜를 표시할 수 있습니다.  만들어진 열을 채우는 방법에 대한 자세한 내용은 [방법: Windows Forms ListView 컨트롤을 사용하여 열에 하위 항목 표시](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)를 참조하십시오.  
  
 다음 절차를 수행하려면 <xref:System.Windows.Forms.ListView> 컨트롤이 포함된 폼이 있는 **Windows 응용 프로그램** 프로젝트가 필요합니다.  이러한 프로젝트를 설정하는 데 대한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)를 참조하십시오.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 디자이너에서 열을 추가하려면  
  
1.  **속성** 창에서 컨트롤의 <xref:System.Windows.Forms.ListView.View%2A> 속성을 <xref:System.Windows.Forms.View>로 설정합니다.  
  
2.  **속성** 창에서 <xref:System.Windows.Forms.ListView.Columns%2A> 속성 옆의 **줄임표** 단추\(![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\)를 클릭합니다.  
  
     **ColumnHeader 컬렉션 편집기**가 나타납니다.  
  
3.  **추가** 단추를 사용하여 새 열을 추가합니다.  그런 다음 열 머리글을 선택하여 텍스트\(열의 캡션\), 텍스트 맞춤 및 너비를 설정할 수 있습니다.  
  
## 참고 항목  
 [ListView 컨트롤 개요](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)   
 [방법: Windows Forms ListView 컨트롤을 사용하여 항목 추가 및 제거](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)   
 [방법: Windows Forms ListView 컨트롤을 사용하여 열에 하위 항목 표시](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)   
 [방법: Windows Forms ListView 컨트롤의 아이콘 표시](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)   
 [방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가\(Windows Forms\)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)