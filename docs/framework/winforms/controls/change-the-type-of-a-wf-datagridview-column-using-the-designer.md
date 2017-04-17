---
title: "방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤의 형식 변경 | Microsoft Docs"
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
  - "열[Windows Forms], 형식"
  - "데이터[Windows Forms], 표시"
  - "DataGridView 컨트롤[Windows Forms], 열 형식 변경"
  - "Windows Forms, 열"
ms.assetid: 7f994d45-600d-4190-a187-35803214b40c
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤의 형식 변경
Windows Forms <xref:System.Windows.Forms.DataGridView> 컨트롤에 이미 추가된 열의 형식을 바꾸려는 경우가 있습니다.  예를 들어, 컨트롤을 데이터 소스에 바인딩할 때 자동으로 생성된 일부 열의 형식을 수정하려는 경우가 있습니다.  이러한 작업은 표시되는 테이블에 관련 테이블의 행에 대한 외래 키가 포함된 열이 있는 경우에 유용합니다.  이 경우 이러한 외래 키가 표시되는 텍스트 상자 열을 관련 테이블에서 더 의미 있는 값이 표시되는 콤보 상자 열로 바꿔야 할 수 있습니다.  
  
 다음 절차를 수행하려면 <xref:System.Windows.Forms.DataGridView> 컨트롤이 포함된 폼이 있는 **Windows 응용 프로그램** 프로젝트가 필요합니다.  이러한 프로젝트를 설정하는 데 대한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)를 참조하십시오.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 디자이너를 사용하여 열의 형식을 변경하려면  
  
1.  <xref:System.Windows.Forms.DataGridView> 컨트롤의 오른쪽 위 모퉁이에 있는 스마트 태그 문자 모양\(![스마트 태그 문자 모양](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\)을 클릭한 다음 **열 편집**을 선택합니다.  
  
2.  **선택한 열** 목록에서 열을 선택합니다.  
  
3.  **열 속성** 표에서 `ColumnType` 속성을 새 열 형식으로 설정합니다.  
  
    > [!NOTE]
    >  `ColumnType` 속성은 열 형식을 나타내는 클래스를 가리키는 디자인 타임 전용 속성입니다.  이 속성은 열 클래스에 실제 정의된 속성이 아닙니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewColumn>   
 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa)   
 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)