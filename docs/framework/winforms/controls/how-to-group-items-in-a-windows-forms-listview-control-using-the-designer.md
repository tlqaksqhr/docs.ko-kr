---
title: "방법: 디자이너를 사용하여 Windows Forms ListView 컨트롤에서 항목 그룹화 | Microsoft Docs"
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
  - "그룹화"
  - "그룹, Windows Forms 컨트롤"
  - "ListView 컨트롤[Windows Forms], 항목 그룹화"
ms.assetid: 8b615000-69d9-4c64-acaf-b54fa09b69e3
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: 디자이너를 사용하여 Windows Forms ListView 컨트롤에서 항목 그룹화
<xref:System.Windows.Forms.ListView> 컨트롤의 그룹화 기능을 사용하여 관련 항목 집합을 그룹으로 표시할 수 있습니다.  이러한 그룹은 그룹 제목이 포함된 가로 그룹 헤더에 의해 화면에서 분리됩니다.  <xref:System.Windows.Forms.ListView> 그룹을 사용하면 사전순, 날짜순 또는 기타 논리적 그룹화 기준으로 항목을 그룹화하여 긴 목록을 쉽게 탐색할 수 있습니다.  다음 이미지는 그룹화된 일부 항목을 보여 줍니다.  
  
 ![ListView 그룹](../../../../docs/framework/winforms/controls/media/listviewgroups.gif "ListViewGroups")  
  
 다음 절차를 수행하려면 <xref:System.Windows.Forms.ListView> 컨트롤이 포함된 폼이 있는 **Windows 응용 프로그램** 프로젝트가 필요합니다.  이러한 프로젝트를 설정하는 데 대한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)를 참조하십시오.  
  
 그룹화를 사용하려면 먼저 하나 이상의 <xref:System.Windows.Forms.ListViewGroup> 개체를 디자이너에서 또는 프로그래밍 방식으로 만들어야 합니다.  그룹을 정의한 다음에는 항목을 그룹에 할당할 수 있습니다.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ListView> 그룹은 응용 프로그램에서 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=fullName> 메서드를 호출할 때 [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)]에서만 사용할 수 있습니다.  이전 버전의 운영 체제에서는 그룹 관련 코드가 영향을 주지 않으며 그룹도 표시되지 않습니다.  자세한 내용은 <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=fullName>를 참조하십시오.  
>   
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 디자이너에서 그룹을 추가하거나 제거하려면  
  
1.  **속성** 창에서 <xref:System.Windows.Forms.ListView.Groups%2A> 속성 옆의 **줄임표**\(![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) 단추를 클릭합니다.  
  
     **ListViewItem 컬렉션 편집기**가 나타납니다.  
  
2.  그룹을 추가하려면 **추가** 단추를 클릭합니다.  그런 다음 <xref:System.Windows.Forms.ListViewGroup.Header%2A> 및 <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A> 속성과 같은 새 그룹의 속성을 설정할 수 있습니다.  그룹을 제거하려면 해당 그룹을 선택한 다음 **제거** 단추를 클릭합니다.  
  
### 디자이너에서 항목을 그룹에 할당하려면  
  
1.  **속성** 창에서 <xref:System.Windows.Forms.ListView.Items%2A> 속성 옆의 **줄임표**\(![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) 단추를 클릭합니다.  
  
     **ListViewItem 컬렉션 편집기**가 나타납니다.  
  
2.  새 항목을 추가하려면 **추가** 단추를 클릭합니다.  그런 다음 <xref:System.Windows.Forms.ListViewItem.Text%2A> 및 <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> 속성과 같은 새 항목의 속성을 설정할 수 있습니다.  
  
3.  <xref:System.Windows.Forms.ListViewItem.Group%2A> 속성을 선택하고 드롭다운 목록에서 그룹을 선택합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.ListView>   
 <xref:System.Windows.Forms.ListView.Groups%2A>   
 <xref:System.Windows.Forms.ListViewGroup>   
 [ListView 컨트롤](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)   
 [ListView 컨트롤 개요](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)   
 [Windows XP Features and Windows Forms Controls](http://msdn.microsoft.com/ko-kr/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)   
 [방법: Windows Forms ListView 컨트롤을 사용하여 항목 추가 및 제거](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)