---
title: "방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 순서 변경 | Microsoft Docs"
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
  - "열[Windows Forms], 순서"
  - "데이터[Windows Forms], 표시"
  - "DataGridView 컨트롤[Windows Forms], 열 순서"
  - "Windows Forms, 열"
ms.assetid: 7fe52a98-75d6-448c-97a5-65ca2c568c1a
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 순서 변경
Windows Forms <xref:System.Windows.Forms.DataGridView> 컨트롤을 데이터 소스에 바인딩하는 경우 자동으로 생성된 열의 표시 순서가 데이터 소스에 따라 결정됩니다.  이 순서가 원하는 순서와 다른 경우 디자이너를 사용하여 열 순서를 변경할 수 있습니다.  또한 바인딩되지 않은 열을 컨트롤에 추가하고 해당 열의 표시 순서를 변경하려는 경우도 있습니다.  프로그래밍 방식으로 열 순서를 변경하는 방법에 대한 자세한 내용은 [방법: Windows Forms DataGridView 컨트롤에서 열 순서 변경](../../../../docs/framework/winforms/controls/how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)을 참조하십시오.  
  
 다음 절차를 수행하려면 <xref:System.Windows.Forms.DataGridView> 컨트롤이 포함된 폼이 있는 **Windows 응용 프로그램** 프로젝트가 필요합니다.  이러한 프로젝트를 설정하는 데 대한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)를 참조하십시오.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)를 참조하십시오.  
  
### 디자이너를 사용하여 열 순서를 변경하려면  
  
1.  <xref:System.Windows.Forms.DataGridView> 컨트롤의 오른쪽 위 모퉁이에 있는 스마트 태그 문자 모양\(![스마트 태그 문자 모양](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\)을 클릭한 다음 **열 편집**을 선택합니다.  
  
2.  **선택한 열** 목록에서 열을 선택합니다.  
  
3.  선택한 열이 원하는 위치에 올 때까지 **선택한 열** 목록 오른쪽의 위쪽\/아래쪽 화살표를 클릭합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 [방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 추가 및 제거](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)   
 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa)   
 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)