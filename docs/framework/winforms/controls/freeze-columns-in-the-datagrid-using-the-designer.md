---
title: "방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 고정 | Microsoft Docs"
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
  - "열[Windows Forms], 고정"
  - "데이터[Windows Forms], 표시"
  - "DataGridView 컨트롤[Windows Forms], 열 고정"
  - "Windows Forms, 열"
ms.assetid: 87412dd2-478f-4751-af87-dafc591fc215
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# 방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 고정
사용자가 Windows Forms <xref:System.Windows.Forms.DataGridView> 컨트롤에 표시된 데이터를 볼 때 반복적으로 참조해야 하는 열 하나 또는 집합이 있는 경우가 있습니다.  예를 들어, 많은 열이 포함된 고객 정보 테이블을 표시하는 경우 다른 열이 표시 영역 밖으로 스크롤될 때에도 고객 이름은 항상 표시되도록 하는 것이 유용합니다.  
  
 이렇게 하려면 컨트롤에서 열을 고정하면 됩니다.  열을 고정하면 해당 열 왼쪽\(오른쪽에서 왼쪽으로 쓰기 언어 스크립트의 경우 오른쪽\)에 있는 모든 열이 함께 고정됩니다.  다른 모든 열은 스크롤할 수 있지만 고정된 열은 그대로 유지됩니다.  열 다시 정렬을 사용하는 경우 고정된 열은 고정되지 않은 열과 구분되는 그룹으로 처리됩니다.  그룹 내에서는 사용자가 열 위치를 변경할 수 있지만 그룹 간에 열을 이동할 수는 없습니다.  
  
 다음 절차를 수행하려면 <xref:System.Windows.Forms.DataGridView> 컨트롤이 포함된 폼이 있는 **Windows 응용 프로그램** 프로젝트가 필요합니다.  이러한 프로젝트를 설정하는 데 대한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)를 참조하십시오.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 디자이너를 사용하여 열을 고정하려면  
  
1.  <xref:System.Windows.Forms.DataGridView> 컨트롤의 오른쪽 위 모퉁이에 있는 스마트 태그 문자 모양\(![스마트 태그 문자 모양](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\)을 클릭한 다음 **열 편집**을 선택합니다.  
  
2.  **선택한 열** 목록에서 열을 선택합니다.  
  
3.  **열 속성** 표에서 <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> 속성을 `true`로 설정합니다.  
  
    > [!NOTE]
    >  **열 추가** 대화 상자에서 **고정** 상자를 선택하여 열을 추가할 때도 열을 고정할 수 있습니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=fullName>   
 [방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 추가 및 제거](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)   
 [방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 다시 정렬 사용](../../../../docs/framework/winforms/controls/enable-column-reordering-in-the-datagrid-using-the-designer.md)   
 [How to: Display Right\-to\-Left Text in Windows Forms for Globalization](http://msdn.microsoft.com/ko-kr/f0663385-2354-4c65-8676-706422283b14)   
 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa)   
 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)