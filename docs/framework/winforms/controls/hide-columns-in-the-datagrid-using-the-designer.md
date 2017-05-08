---
title: "방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 숨기기 | Microsoft Docs"
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
  - "열[Windows Forms], 숨기기"
  - "데이터[Windows Forms], 표시"
  - "DataGridView 컨트롤[Windows Forms], 열 숨기기"
  - "Windows Forms, 열"
ms.assetid: a81c38e6-2527-426a-bcb1-be691403be04
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 숨기기
Windows Forms <xref:System.Windows.Forms.DataGridView> 컨트롤에서 사용 가능한 열의 일부만 표시하려는 경우가 있습니다.  예를 들어, 직원 급여 열을 다른 사용자에게는 숨기고 관리 자격 증명이 있는 사용자에게 표시할 수 있습니다.  또는 컨트롤을 여러 열이 포함된 데이터 소스에 바인딩하여 원하는 일부 열만 표시할 수도 있습니다.  이 경우 일반적으로 사용자는 표시하지 않으려는 열을 숨기기는 것이 아니라 제거합니다.  자세한 내용은 [방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 추가 및 제거](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)를 참조하십시오.  
  
 다음 절차를 수행하려면 <xref:System.Windows.Forms.DataGridView> 컨트롤이 포함된 폼이 있는 **Windows 응용 프로그램** 프로젝트가 필요합니다.  이러한 프로젝트를 설정하는 데 대한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)를 참조하십시오.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 디자이너를 사용하여 열을 숨기려면  
  
1.  <xref:System.Windows.Forms.DataGridView> 컨트롤의 오른쪽 위 모퉁이에 있는 스마트 태그 문자 모양\(![스마트 태그 문자 모양](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\)을 클릭한 다음 **열 편집**을 선택합니다.  
  
2.  **선택한 열** 목록에서 열을 선택합니다.  
  
3.  **열 속성** 표에서 <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> 속성을 `false`로 설정합니다.  
  
    > [!NOTE]
    >  또한 열을 추가할 때 **열 추가** 대화 상자에서 **표시** 확인란의 선택을 취소하여 열을 숨길 수도 있습니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=fullName>   
 [방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 추가 및 제거](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)   
 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa)   
 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)