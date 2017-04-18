---
title: "Windows Forms DataGridView 컨트롤의 기본 기능 | Microsoft Docs"
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
  - "데이터 표, DataGridView 컨트롤의 기본 기능"
  - "DataGridView 컨트롤[Windows Forms], 기본 기능"
ms.assetid: 4405f697-cad1-4839-9bcd-8ddb09d9f00e
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Windows Forms DataGridView 컨트롤의 기본 기능
Windows Forms <xref:System.Windows.Forms.DataGridView> 컨트롤은 많은 기본 기능을 사용자에게 제공합니다.  
  
## 기본 기능  
 <xref:System.Windows.Forms.DataGridView> 컨트롤의 기본 기능은 다음과 같습니다.  
  
-   테이블을 세로로 스크롤할 때 계속 표시되는 열 머리글과 행 머리글을 자동으로 표시합니다.  
  
-   현재 행에 대한 선택 영역 표시기가 포함된 행 머리글이 있습니다.  
  
-   첫 번째 셀에 선택 영역 표시 직사각형이 있습니다.  
  
-   사용자가 열 구분선을 두 번 클릭하여 크기를 자동으로 조정할 수 있는 열이 있습니다.  
  
-   응용 프로그램의 `Main` 메서드에서 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> 메서드를 호출하는 경우에 Windows XP와 Windows Server 2003 제품군의 비주얼 스타일을 자동으로 지원합니다.  
  
 또한 다음과 같이 <xref:System.Windows.Forms.DataGridView> 컨트롤의 내용을 기본적으로 편집할 수 있습니다.  
  
-   사용자가 셀에서 두 번 클릭하거나 F2 키를 누르면 해당 셀이 자동으로 편집 모드로 바뀌며 사용자가 입력하는 대로 셀의 내용이 업데이트됩니다.  
  
-   사용자가 테이블 끝으로 스크롤하면 새 레코드를 추가하기 위한 행이 있음을 확인할 수 있습니다.  사용자가 이 행을 클릭하면 새 행이 기본값으로 <xref:System.Windows.Forms.DataGridView> 컨트롤에 추가됩니다.  사용자가 Esc 키를 누르면 이 새 행이 사라집니다.  
  
-   사용자가 행 머리글을 클릭하면 전체 행이 선택됩니다.  
  
 <xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Windows.Forms.DataGridView.DataSource%2A> 속성을 설정하여 이 컨트롤을 데이터 소스에 바인딩하면 컨트롤에서는 다음과 같은 작업을 수행합니다.  
  
-   자동으로 데이터 소스의 열 이름을 열 머리글 텍스트로 사용합니다.  
  
-   컨트롤이 데이터 소스의 내용으로 채워집니다.  데이터 소스의 각 열에 대해 <xref:System.Windows.Forms.DataGridView> 열이 자동으로 만들어집니다.  
  
-   테이블에 표시되는 각 행에 대한 행을 만듭니다.  
  
-   사용자가 열 머리글을 클릭하면 내부 데이터를 기준으로 행을 자동 정렬합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 [DataGridView 컨트롤](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)