---
title: "Windows Forms DataGridView 컨트롤의 열 및 행 크기 조정 | Microsoft Docs"
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
  - "열[Windows Forms], 표에서 크기 조정"
  - "데이터 표, 열 및 행 크기 조정"
  - "DataGridView 컨트롤[Windows Forms], 행 및 열 크기 조정"
ms.assetid: 7532764d-e5c1-4943-a08b-6377a722d3b6
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Windows Forms DataGridView 컨트롤의 열 및 행 크기 조정
`DataGridView` 컨트롤은 컨트롤의 열 및 행의 크기 조정 동작을 사용자 지정할 수 있는 많은 옵션을 제공합니다.  일반적으로 `DataGridView` 셀은 내용에 따라 크기가 조정되지 않습니다.  대신 셀보다 큰 모든 표시 값은 잘립니다.  문자열로 표시할 수 있는 내용인 경우 셀은 내용을 도구 설명에 표시합니다.  
  
 기본적으로 사용자는 마우스로 행, 열 및 머리글 구분선을 끌어서 추가 정보를 볼 수 있습니다.  또한 사용자는 구분선을 두 번 클릭하여 연결된 행, 열 또는 머리글 밴드의 내용을 기준으로 크기를 자동으로 조정할 수 있습니다.  
  
 `DataGridView` 컨트롤은 이러한 모든 사용자 조정 동작을 사용자 지정하거나 비활성화할 수 있는 속성, 메서드 및 이벤트를 제공합니다.  또는 행, 열 및 머리글의 크기를 내용에 맞도록 프로그래밍 방식으로 조정하거나 내용이 변경될 때마다 자동으로 조정되도록 구성할 수 있습니다.  컨트롤의 사용 가능한 너비를 지정한 비율로 자동으로 나누도록 열을 구성할 수도 있습니다.  
  
## 단원 내용  
 [Windows Forms DataGridView 컨트롤의 크기 조정 옵션](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)  
 행, 열 및 머리글의 크기 조정에 대한 옵션을 설명합니다.  크기 조정 관련 속성 및 메서드에 대해 자세히 설명하고 일반적인 사용 시나리오를 설명합니다.  
  
 [Windows Forms DataGridView 컨트롤의 열 채우기 모드](../../../../docs/framework/winforms/controls/column-fill-mode-in-the-windows-forms-datagridview-control.md)  
 열 채우기 모드에 대해 자세히 설명하고 열 채우기 모드 및 기타 모드를 사용하는 방법을 보여 주는 예제 코드를 제공합니다.  
  
 [방법: Windows Forms DataGridView 컨트롤의 크기 조정 모드 설정](../../../../docs/framework/winforms/controls/how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)  
 크기 조정 모드를 일반적인 용도로 구성하는 방법을 설명합니다.  
  
 [방법: Windows Forms DataGridView 컨트롤에서 내용에 맞게 프로그래밍 방식으로 셀 크기 조정](../../../../docs/framework/winforms/controls/programmatically-resize-cells-to-fit-content-in-the-datagrid.md)  
 프로그래밍 방식으로 크기를 조정하는 방법을 보여 주는 예제 코드를 제공합니다.  
  
 [방법: Windows Forms DataGridView 컨트롤에서 내용이 변경되는 경우 자동으로 셀 크기 조정](../../../../docs/framework/winforms/controls/automatically-resize-cells-when-content-changes-in-the-datagrid.md)  
 자동 크기 조정 모드를 사용하는 방법을 보여 주는 예제 코드를 제공합니다.  
  
## 참조  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조 설명서를 제공합니다.  
  
## 참고 항목  
 [DataGridView 컨트롤](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)