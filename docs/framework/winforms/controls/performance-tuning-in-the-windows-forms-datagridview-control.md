---
title: "Windows Forms DataGridView 컨트롤의 성능 조정 | Microsoft Docs"
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
  - "DataGridView 컨트롤[Windows Forms], 성능 조정"
  - "성능 조정, 데이터 표"
  - "성능, DataGridView 컨트롤"
ms.assetid: 6ccbff28-a0ff-41e4-b601-61b31b61851d
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Windows Forms DataGridView 컨트롤의 성능 조정
대용량 데이터 작업을 수행할 때 주의하지 않으면 `DataGridView` 컨트롤이 많은 양의 메모리를 과도하게 소비할 수 있습니다.  제한된 메모리를 사용하는 클라이언트에서는 메모리가 많이 사용되는 기능을 사용하지 않음으로써 이러한 오버헤드를 피할 수 있습니다.  또한 가상 모드를 사용하여 데이터 유지 관리 및 검색 작업 중 일부 또는 전체를 직접 관리하여 메모리 사용을 시나리오에 맞게 사용자 지정할 수 있습니다.  
  
## 단원 내용  
 [Windows Forms DataGridView 컨트롤의 크기를 조정하는 최선의 방법](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 불필요한 메모리 사용을 줄여서 대용량 데이터 작업을 수행할 때 성능이 저하되지 않도록 `DataGridView` 컨트롤을 사용하는 방법을 설명합니다.  
  
 [Windows Forms DataGridView 컨트롤의 가상 모드](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)  
 가상 모드를 사용하여 표준 데이터 바인딩 메커니즘을 보완하거나 대체하는 방법을 설명합니다.  
  
 [연습: Windows Forms DataGridView 컨트롤에서 가상 모드 구현](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)  
 여러 가상 모드 이벤트에 대한 처리기를 구현하는 방법을 설명합니다.  또한 사용자 편집에 대한 행 수준 롤백 및 커밋을 구현하는 방법을 보여 줍니다.  
  
 [Windows Forms DataGridView 컨트롤에서 Just\-In\-Time 데이터 로드를 사용하여 가상 모드 구현](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 요청에 따라 데이터를 로드하는 방법을 설명합니다. 이 방법은 클라이언트 메모리에 저장할 수 있는 양보다 많은 데이터를 표시해야 하는 경우에 유용합니다.  
  
## 참조  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조 설명서를 제공합니다.  
  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 속성에 대한 참조 설명서를 제공합니다.  
  
## 참고 항목  
 [DataGridView 컨트롤](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)   
 [Windows Forms DataGridView 컨트롤의 데이터 디스플레이 모드](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)