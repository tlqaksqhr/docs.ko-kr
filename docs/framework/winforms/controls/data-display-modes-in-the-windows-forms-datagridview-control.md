---
title: "Windows Forms DataGridView 컨트롤의 데이터 디스플레이 모드 | Microsoft Docs"
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
  - "데이터[Windows Forms], 디스플레이 모드"
  - "데이터 표, 디스플레이 모드"
  - "DataGridView 컨트롤[Windows Forms], 디스플레이 모드"
ms.assetid: 9755a030-3f3f-4705-a661-ba5a48a81875
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Windows Forms DataGridView 컨트롤의 데이터 디스플레이 모드
<xref:System.Windows.Forms.DataGridView> 컨트롤은 바인딩된 모드, 바인딩되지 않은 모드 및 가상 모드의 세 가지 모드로 데이터를 표시할 수 있습니다.  요구 사항에 따라 가장 알맞은 모드를 선택합니다.  
  
## 바인딩되지 않은 모드  
 바인딩되지 않은 모드는 프로그래밍 방식으로 관리하는 적은 양의 데이터를 표시하는 경우 적합합니다.  이 모드에서는 바인딩된 모드에서처럼 데이터 소스에 <xref:System.Windows.Forms.DataGridView> 컨트롤을 직접 연결하지 않습니다.  대신 일반적으로 <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=fullName> 메서드를 사용하여 직접 컨트롤을 채워야 합니다.  
  
 바인딩되지 않은 모드는 정적 데이터나 읽기 전용 데이터 또는 외부 데이터 저장소와 상호 작용하는 사용자 코드를 제공하려는 경우 특히 유용합니다.  그러나 사용자가 외부 데이터 소스와 상호 작용하도록 하려는 경우에는 일반적으로 바인딩된 모드를 사용합니다.  
  
 읽기 전용의 바인딩되지 않은 <xref:System.Windows.Forms.DataGridView>를 사용하는 예는 [방법: 바인딩되지 않은 Windows Forms DataGridView 컨트롤 만들기](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md)를 참조하십시오.  
  
## 바인딩된 모드  
 바인딩된 모드는 데이터 저장소와의 자동 상호 작용을 사용하여 데이터를 관리하는 경우 적합합니다.  <xref:System.Windows.Forms.DataGridView.DataSource%2A> 속성을 설정하여 <xref:System.Windows.Forms.DataGridView> 컨트롤을 해당 데이터 소스에 직접 연결할 수 있습니다.  데이터 바인딩된 컨트롤의 경우 명시적으로 직접 관리하지 않아도 데이터 행을 푸시하거나 가져올 수 있습니다.  <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> 속성이 `true`인 경우 데이터 소스의 각 열에 해당하는 열이 컨트롤에 만들어집니다.  사용자 열을 만들려면 이 속성을 `false`로 설정하고 <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A> 속성을 사용하여 각 열을 구성할 때 해당 열을 바인딩합니다.  이는 기본적으로 생성되는 형식 이외의 열 형식을 사용하려는 경우 유용합니다.  자세한 내용은 [Windows Forms DataGridView 컨트롤의 열 형식](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)을 참조하십시오.  
  
 바인딩된 <xref:System.Windows.Forms.DataGridView> 컨트롤을 사용하는 예는 [연습: Windows Forms DataGridView 컨트롤의 데이터 유효성 검사](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)를 참조하십시오.  
  
 바인딩된 모드에서 바인딩되지 않은 열을 <xref:System.Windows.Forms.DataGridView> 컨트롤에 추가할 수도 있습니다.  이는 사용자가 특정 행에 대한 작업을 수행할 수 있는 단추 또는 링크 열을 표시하려는 경우 유용합니다.  바인딩된 열에서 계산된 값이 포함된 열을 표시하는 경우에도 유용합니다.  <xref:System.Windows.Forms.DataGridView.CellFormatting> 이벤트에 대한 처리기에서 계산된 열의 셀 값을 채울 수 있습니다.  그러나 <xref:System.Data.DataSet> 또는 <xref:System.Data.DataTable>을 데이터 소스로 사용하는 경우에는 <xref:System.Data.DataColumn.Expression%2A?displayProperty=fullName> 속성을 사용하여 대신 계산 열을 만드는 것이 좋습니다.  이 경우 <xref:System.Windows.Forms.DataGridView> 컨트롤은 계산 열을 데이터 소스의 다른 모든 열과 마찬가지로 처리합니다.  
  
 바인딩된 모드에서 바인딩되지 않은 열별로 정렬할 수는 없습니다.  바인딩된 모드에서 사용자가 편집 가능한 값을 포함하는 바인딩되지 않은 열을 만드는 경우 가상 모드를 구현하여 컨트롤이 바인딩된 열별로 정렬될 때 이러한 값을 유지 관리해야 합니다.  
  
## 가상 모드  
 가상 모드에서는 사용자 데이터 관리 작업을 구현할 수 있습니다.  이는 컨트롤이 바인딩된 열별로 정렬될 때 바인딩된 모드에서 바인딩되지 않은 열의 값을 유지 관리하는 경우 필요합니다.  그러나 가상 모드의 주 용도는 대량의 데이터와 상호 작용할 때 성능을 최적화하는 것입니다.  
  
 관리하는 캐시에 <xref:System.Windows.Forms.DataGridView> 컨트롤을 연결하면 코드가 데이터 행을 푸시하고 가져올 시기를 제어합니다.  캐시가 메모리에서 차지하는 공간 크기를 최소한으로 유지하려면 캐시가 현재 표시된 행 수와 비슷한 크기여야 합니다.  사용자가 새 행을 뷰로 스크롤하면 코드는 캐시에서 새 데이터를 요청하고 필요한 경우 메모리에서 이전 데이터를 플러시합니다.  
  
 가상 모드를 구현할 때는 데이터 모델에 새 행이 필요한 경우 및 새 행 추가를 롤백하는 하는 경우 추적을 수행해야 합니다.  이 기능의 정확한 구현은 데이터 모델의 구현 및 데이터 모델의 트랜잭션 의미, 커밋 범위가 셀 수준인지, 아니면 행 수준인지에 따라 달라집니다.  
  
 가상 모드에 대한 자세한 내용은 [Windows Forms DataGridView 컨트롤의 가상 모드](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)를 참조하십시오.  가상 모드 이벤트를 사용하는 방법에 대한 예는 [연습: Windows Forms DataGridView 컨트롤에서 가상 모드 구현](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.BindingSource>   
 <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A?displayProperty=fullName>   
 [Windows Forms DataGridView 컨트롤에서 데이터 표시](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)   
 [Windows Forms DataGridView 컨트롤의 열 형식](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)   
 [연습: 바인딩되지 않은 Windows Forms DataGridView 컨트롤 만들기](../../../../docs/framework/winforms/controls/walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)   
 [방법: Windows Forms DataGridView 컨트롤에 데이터 바인딩](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md)   
 [Windows Forms DataGridView 컨트롤의 가상 모드](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)   
 [연습: Windows Forms DataGridView 컨트롤에서 가상 모드 구현](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)