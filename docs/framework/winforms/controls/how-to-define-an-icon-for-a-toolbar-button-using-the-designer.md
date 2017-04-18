---
title: "방법: 디자이너를 사용하여 도구 모음 단추의 아이콘 정의 | Microsoft Docs"
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
  - "단추[Windows Forms], 이미지"
  - "예제[Windows Forms], 도구 모음"
  - "아이콘[Windows Forms], 도구 모음 단추"
  - "이미지[Windows Forms], 도구 모음 단추"
  - "ToolBar 컨트롤[Windows Forms], 단추에 아이콘 추가"
  - "도구 모음[Windows Forms], 단추에 아이콘 추가"
ms.assetid: d848f38e-67f2-49d4-8e88-01c845c06c02
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: 디자이너를 사용하여 도구 모음 단추의 아이콘 정의
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStrip> 컨트롤은 <xref:System.Windows.Forms.ToolBar> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.ToolBar> 컨트롤을 계속 유지하도록 선택할 수 있습니다.  
  
 사용자가 쉽게 식별할 수 있도록 <xref:System.Windows.Forms.ToolBar> 단추에 아이콘을 표시할 수 있습니다.  이렇게 하려면 <xref:System.Windows.Forms.ImageList> 구성 요소에 이미지를 추가한 다음 구성 요소를 <xref:System.Windows.Forms.ToolBar> 컨트롤에 연결합니다.  
  
 다음 절차를 수행하려면 <xref:System.Windows.Forms.ToolBar> 컨트롤과 <xref:System.Windows.Forms.ImageList> 구성 요소가 포함된 폼이 있는 **Windows 응용 프로그램** 프로젝트가 필요합니다.  이러한 프로젝트를 설정하는 데 대한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)를 참조하십시오.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 디자인 타임에 도구 모음 단추의 아이콘을 설정하려면  
  
1.  이미지를 <xref:System.Windows.Forms.ImageList> 구성 요소에 추가합니다.  자세한 내용은 [방법: 디자이너를 사용하여 ImageList 이미지 추가 또는 제거](../../../../docs/framework/winforms/controls/how-to-add-or-remove-imagelist-images-with-the-designer.md)를 참조하십시오.  
  
2.  폼에서 <xref:System.Windows.Forms.ToolBar> 컨트롤을 선택합니다.  
  
3.  **속성** 창에서 <xref:System.Windows.Forms.ToolBar> 컨트롤의 <xref:System.Windows.Forms.ToolBar.ImageList%2A> 속성을 <xref:System.Windows.Forms.ImageList> 구성 요소로 설정합니다.  
  
4.  <xref:System.Windows.Forms.ToolBar> 컨트롤의 <xref:System.Windows.Forms.ToolBar.Buttons%2A> 속성을 클릭하여 선택하고 줄임표 단추\(![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\)를 클릭하여 **ToolBarButton 컬렉션 편집기**를 엽니다.  
  
5.  **추가** 단추를 사용하여 단추를 <xref:System.Windows.Forms.ToolBar> 컨트롤에 추가합니다.  
  
6.  **ToolBarButton 컬렉션 편집기**의 오른쪽 창에 나타나는 **속성** 창에서 각 도구 모음 단추의 <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> 속성을 목록에 있는 값 중 하나로 설정합니다. 이 값 목록은 <xref:System.Windows.Forms.ImageList> 구성 요소에 추가한 이미지로부터 생성됩니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.ToolBar>   
 [방법: 도구 모음 단추에 대한 메뉴 이벤트 발생](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)   
 [ToolBar 컨트롤](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)   
 [ImageList 구성 요소](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)