---
title: "방법: 디자이너를 사용하여 Windows Forms 패널의 배경 설정 | Microsoft Docs"
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
  - "배경색, Windows Forms Panel 컨트롤"
  - "배경 이미지, Windows Forms Panel 컨트롤"
  - "색, Windows Forms Panel 컨트롤"
  - "Panel 컨트롤[Windows Forms], 배경"
ms.assetid: db83cf54-3c69-4b08-ac6c-25b9b5abb1b0
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: 디자이너를 사용하여 Windows Forms 패널의 배경 설정
Windows Forms <xref:System.Windows.Forms.Panel> 컨트롤은 배경색과 배경 이미지를 모두 표시할 수 있습니다.  <xref:System.Windows.Forms.Control.BackColor%2A> 속성은 레이블이나 라디오 단추 등 패널에 포함된 컨트롤의 배경색을 설정합니다.  <xref:System.Windows.Forms.Control.BackgroundImage%2A> 속성이 설정되어 있지 않으면 전체 패널이 <xref:System.Windows.Forms.Control.BackColor%2A>에서 선택한 색으로 채워집니다.  <xref:System.Windows.Forms.Control.BackgroundImage%2A> 속성이 설정되어 있으면 패널에 포함된 컨트롤 뒤에 이미지가 표시됩니다.  
  
 다음 절차를 수행하려면 <xref:System.Windows.Forms.Panel> 컨트롤이 포함된 폼이 있는 **Windows 응용 프로그램** 프로젝트가 필요합니다.  이러한 프로젝트를 설정하는 방법에 대한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)를 참조하십시오.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### Windows Forms 디자이너에서 배경을 설정하려면  
  
1.  <xref:System.Windows.Forms.Panel> 컨트롤을 선택합니다.  
  
2.  **속성** 창에서 <xref:System.Windows.Forms.Control.BackColor%2A> 속성 옆에 있는 화살표 단추를 클릭하여 세 개의 탭이 있는 창을 표시합니다.  
  
3.  **사용자 지정** 탭을 선택하여 색상표를 표시합니다.  
  
4.  **웹** 또는 **시스템** 탭을 선택하여 미리 정의된 색 이름 목록을 표시한 다음 색을 선택합니다.  
  
5.  **속성** 창에서 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 속성 옆에 있는 화살표 단추를 클릭합니다.  
  
6.  **열기** 대화 상자에서 표시할 파일을 선택합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.Control.BackColor%2A>   
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>   
 [Panel 컨트롤](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)   
 [Panel 컨트롤 개요](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)   
 [방법: 디자이너에서 Windows Forms 패널 컨트롤을 사용하여 컨트롤 그룹화](../../../../docs/framework/winforms/controls/group-controls-with-wf-panel-control-using-the-designer.md)