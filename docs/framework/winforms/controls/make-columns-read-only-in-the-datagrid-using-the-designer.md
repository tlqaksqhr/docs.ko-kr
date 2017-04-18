---
title: "방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열을 읽기 전용으로 설정 | Microsoft Docs"
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
  - "열[Windows Forms], 읽기 전용"
  - "데이터[Windows Forms], 표시"
  - "DataGridView 컨트롤[Windows Forms], 읽기 전용 열"
  - "Windows Forms, 열"
ms.assetid: b4ef7a75-ab33-4ee3-b2cf-201530e454e9
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# 방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열을 읽기 전용으로 설정
기본적으로 사용자는 Windows Forms <xref:System.Windows.Forms.DataGridView> 컨트롤에 표시된 텍스트 및 숫자 데이터를 수정할 수 있습니다.  수정하지 않으려는 데이터를 표시하려면 해당 데이터가 포함된 열을 읽기 전용으로 설정해야 합니다.  컨트롤을 완전히 읽기 전용으로 설정하는 방법에 대한 자세한 내용은 [방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 행 추가 및 삭제 금지](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)를 참조하십시오.  
  
 다음 절차를 수행하려면 <xref:System.Windows.Forms.DataGridView> 컨트롤이 포함된 폼이 있는 **Windows 응용 프로그램** 프로젝트가 필요합니다.  이러한 프로젝트를 설정하는 데 대한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)를 참조하십시오.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 디자이너를 사용하여 열을 읽기 전용으로 설정하려면  
  
1.  <xref:System.Windows.Forms.DataGridView> 컨트롤의 오른쪽 위 모퉁이에 있는 스마트 태그 문자 모양\(![스마트 태그 문자 모양](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\)을 클릭한 다음 **열 편집**을 선택합니다.  
  
2.  **선택한 열** 목록에서 열을 선택합니다.  
  
3.  **열 속성** 표에서 <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> 속성을 `true`로 설정합니다.  
  
    > [!NOTE]
    >  또한 열을 추가할 때 **열 추가** 대화 상자에서 **읽기 전용** 확인란을 선택하여 열을 읽기 전용으로 설정할 수 있습니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=fullName>   
 [방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 추가 및 제거](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)   
 [방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 행 추가 및 삭제 금지](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)   
 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa)   
 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)