---
title: "Windows Forms DataGridView 컨트롤의 성능 조정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], performance tuning
- performance [Windows Forms], DataGridView control
- performance tuning [Windows Forms], data grids
ms.assetid: 6ccbff28-a0ff-41e4-b601-61b31b61851d
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 452c55d38a896ec96e0992a4b9826f08dc4caa0e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="performance-tuning-in-the-windows-forms-datagridview-control"></a>Windows Forms DataGridView 컨트롤의 성능 조정
많은 양의 데이터를 작업할 때의 `DataGridView` 신중 하 게 사용 하지 않는 한 컨트롤 많은 양의 메모리를에서 사용할 수 있습니다. 제한 된 메모리와 클라이언트에 메모리가 많이 있는 기능을 방지 하 여 이러한 오버 헤드 방지할 수 있습니다. 또한 데이터 유지 관리의 일부 또는 전부를 관리할 수 있습니다와 가상 모드를 사용 하 여 메모리 사용 시나리오에 대 한 사용자 지정 하기 위해 직접 검색 작업을 합니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [Windows Forms DataGridView 컨트롤의 크기를 조정하는 최선의 방법](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 사용 하는 방법에 설명 된 `DataGridView` 많은 양의 데이터를 작업할 때는 불필요 한 메모리 사용량 및 성능 저하를 방지 하는 방법에 대 한 제어 합니다.  
  
 [Windows Forms DataGridView 컨트롤의 가상 모드](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)  
 가상 모드 보완 하거나 바꿀 표준 데이터 바인딩 메커니즘을 사용 하는 방법을 설명 합니다.  
  
 [연습: Windows Forms DataGridView 컨트롤에서 가상 모드 구현](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)  
 여러 개의 가상 모드 이벤트에 대 한 처리기를 구현 하는 방법을 설명 합니다. 또한 행 수준 rollback 및 commit 사용자 편집에 대 한 구현 하는 방법을 보여 줍니다.  
  
 [Windows Forms DataGridView 컨트롤에서 Just-In-Time 데이터 로드를 사용하여 가상 모드 구현](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 필요할 때에는 표시할 사용 가능한 클라이언트 메모리에 저장할 수 있는 것 보다 더 많은 데이터가 있는 경우 데이터를 로드 하는 방법을 설명 합니다.  
  
## <a name="reference"></a>참조  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조 설명서를 제공합니다.  
  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 에 대 한 참조 설명서를 제공는 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 속성입니다.  
  
## <a name="see-also"></a>참고 항목  
 [DataGridView 컨트롤](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [Windows Forms DataGridView 컨트롤의 데이터 디스플레이 모드](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)
