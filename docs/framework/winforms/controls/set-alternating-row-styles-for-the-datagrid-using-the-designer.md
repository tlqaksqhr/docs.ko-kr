---
title: "방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에 교대로 반복되는 행 스타일 설정 | Microsoft Docs"
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
  - "데이터[Windows Forms], 표시"
  - "DataGridView 컨트롤[Windows Forms], 행 스타일 교대로 반복"
  - "장부 형식"
  - "행, 교대로 반복"
  - "Windows Forms, 행"
ms.assetid: 02373442-bf94-4470-9f8a-e44c4a9d5b88
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에 교대로 반복되는 행 스타일 설정
표 형식 데이터는 행의 배경색이 교대로 반복되는 장부 형식으로 표시되는 경우가 많습니다.  이 형식을 사용하면 특히 많은 열이 포함된 너비가 넓은 표에서 각 행의 셀을 쉽게 구분할 수 있습니다.  
  
 <xref:System.Windows.Forms.DataGridView> 컨트롤을 사용하여 교대로 반복되는 행에 대한 전체 스타일 정보를 지정할 수 있습니다.  배경색 이외에 전경색 및 글꼴과 같은 스타일 특성을 사용하여 교대로 반복되는 행을 구분할 수 있습니다.  자세한 내용은 [Windows Forms DataGridView 컨트롤의 셀 스타일](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)을 참조하십시오.  
  
 다음 절차를 수행하려면 <xref:System.Windows.Forms.DataGridView> 컨트롤이 포함된 폼이 있는 **Windows 응용 프로그램** 프로젝트가 필요합니다.  이러한 프로젝트를 설정하는 데 대한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)를 참조하십시오.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 교대로 반복되는 행의 스타일 정의  
  
1.  디자이너에서 <xref:System.Windows.Forms.DataGridView> 컨트롤을 선택합니다.  
  
2.  **속성** 창에서 <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> 속성 옆에 있는 줄임표 단추\(![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\)를 클릭합니다.  
  
3.  **CellStyle 작성기** 대화 상자에서 속성을 설정하여 스타일을 정의하고 **미리 보기** 창을 사용하여 선택 사항을 확인합니다.  지정한 스타일은 두 번째 행부터 시작하여 컨트롤에 표시되는 모든 다른 행에 사용됩니다.  
  
4.  나머지 행의 스타일을 정의하려면 <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> 속성을 사용하여 2단계와 3단계를 반복합니다.  
  
    > [!NOTE]
    >  셀은 여러 속성으로부터 상속된 스타일을 사용하여 표시됩니다.  스타일 상속에 대한 자세한 내용은 [Windows Forms DataGridView 컨트롤의 셀 스타일](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 [Windows Forms DataGridView 컨트롤의 셀 스타일](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)   
 [Windows Forms DataGridView 컨트롤의 기본 형식 및 스타일 지정](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)   
 [Windows Forms DataGridView 컨트롤에 디자이너 사용](../../../../docs/framework/winforms/controls/using-the-designer-with-the-windows-forms-datagridview-control.md)   
 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa)   
 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)