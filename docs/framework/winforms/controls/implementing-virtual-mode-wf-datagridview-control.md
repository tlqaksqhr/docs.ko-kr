---
title: "연습: Windows Forms DataGridView 컨트롤에서 가상 모드 구현 | Microsoft Docs"
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
  - "데이터[Windows Forms], 큰 데이터 집합 관리"
  - "DataGridView 컨트롤[Windows Forms], 큰 데이터 집합"
  - "DataGridView 컨트롤[Windows Forms], 가상 모드"
  - "가상 모드, 연습"
  - "연습[Windows Forms], DataGridView 컨트롤"
ms.assetid: 74eb5276-5ab8-4ce0-8005-dae751d85f7c
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 연습: Windows Forms DataGridView 컨트롤에서 가상 모드 구현
표 형식의 대용량 데이터를 <xref:System.Windows.Forms.DataGridView> 컨트롤에 표시하려는 경우 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 속성을 `true`로 설정하고 컨트롤과 해당 데이터 저장소의 상호 작용을 명시적으로 관리할 수 있습니다.  이 방법을 사용하면 이 상황에서 컨트롤의 성능을 세밀하게 조정할 수 있습니다.  
  
 <xref:System.Windows.Forms.DataGridView> 컨트롤은 사용자 지정 데이터 저장소와 상호 작용하기 위해 처리할 수 있는 여러 가지 이벤트를 제공합니다.  이 연습에서는 이러한 이벤트 처리기를 구현하는 과정을 보여 줍니다.  이 항목의 코드 예제에서는 매우 간단한 데이터 소스를 사용합니다.  프로덕션 설정에서는 일반적으로 표시해야 하는 행만 캐시에 로드한 다음 <xref:System.Windows.Forms.DataGridView> 이벤트를 처리하여 캐시와 상호 작용하고 캐시를 업데이트합니다.  자세한 내용은 [Windows Forms DataGridView 컨트롤에서 Just\-In\-Time 데이터 로드를 사용하여 가상 모드 구현](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)를 참조하십시오.  
  
 이 항목의 코드를 단일 목록으로 복사하려면 [방법: Windows Forms DataGridView 컨트롤에서 가상 모드 구현](../../../../docs/framework/winforms/controls/how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)을 참조하십시오.  
  
## 폼 만들기  
  
#### 가상 모드를 구현하려면  
  
1.  <xref:System.Windows.Forms.Form>에서 파생되고 <xref:System.Windows.Forms.DataGridView> 컨트롤을 포함하는 클래스를 만듭니다.  
  
     다음 코드에는 기본 초기화 과정이 들어 있습니다.  초기화 과정에서는 클래스 생성자에서 이후 단계에 사용할 몇 가지 변수를 선언하고, `Main` 메서드를 제공하며, 단순한 폼 레이아웃을 제공합니다.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#001](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#001)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#001](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#001)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#001](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#001)]  
    [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#002](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#002)]
    [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#002](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#002)]
    [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#002](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#002)]  
  
2.  <xref:System.Windows.Forms.DataGridView> 컨트롤을 초기화하고 샘플 값으로 데이터 저장소를 채우는 폼의 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기를 구현합니다.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#110](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#110)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#110)]  
  
3.  요청된 셀 값을 데이터 저장소나 현재 편집 중인 `Customer` 개체에서 검색하는 <xref:System.Windows.Forms.DataGridView.CellValueNeeded> 이벤트 처리기를 구현합니다.  
  
     이 이벤트는 <xref:System.Windows.Forms.DataGridView> 컨트롤이 셀을 그려야할 때마다 발생합니다.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#120](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#120)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#120)]  
  
4.  편집 행을 나타내는 `Customer` 개체에 편집된 셀 값을 저장하는 <xref:System.Windows.Forms.DataGridView.CellValuePushed> 이벤트 처리기를 구현합니다.  이 이벤트는 사용자가 셀 값 변경을 커밋할 때마다 발생합니다.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#130](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#130)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#130)]  
  
5.  새로 만들어진 행을 나타내는 새 `Customer` 개체를 만드는 <xref:System.Windows.Forms.DataGridView.NewRowNeeded> 이벤트 처리기를 구현합니다.  
  
     이 이벤트는 사용자가 새 레코드에 대한 행을 입력할 때마다 발생합니다.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#140](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#140)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#140](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#140)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#140](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#140)]  
  
6.  새 행이나 수정된 행을 데이터 저장소에 저장하는 <xref:System.Windows.Forms.DataGridView.RowValidated> 이벤트 처리기를 구현합니다.  
  
     이 이벤트는 사용자가 현재 행을 변경할 때마다 발생합니다.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#150](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#150)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#150](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#150)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#150](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#150)]  
  
7.  사용자가 Esc 키를 편집 모드에서 두 번 누르거나 편집 모드 이외의 모드에서 한 번 눌러 행 되돌리기 신호를 보내는 경우 <xref:System.Windows.Forms.DataGridView.CancelRowEdit> 이벤트가 발생하는지 여부를 나타내는 <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> 이벤트 처리기를 구현합니다.  
  
     기본적으로 <xref:System.Windows.Forms.DataGridView.CancelRowEdit>는 <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> 이벤트 처리기에서 <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=fullName> 속성이 `true`로 설정되어 있지 않고 현재 행의 셀이 수정된 경우 행 되돌리기 작업이 수행되는 즉시 발생합니다.  이 이벤트는 커밋 범위가 런타임에 결정되는 경우에 유용합니다.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#160](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#160)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#160](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#160)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#160](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#160)]  
  
8.  현재 행을 나타내는 `Customer` 개체의 값을 삭제하는 <xref:System.Windows.Forms.DataGridView.CancelRowEdit> 이벤트 처리기를 구현합니다.  
  
     이 이벤트는 사용자가 Esc 키를 편집 모드에서 두 번 누르거나 편집 모드 이외의 모드에서 한 번 눌러 행 되돌리기 신호를 보낼 때 발생합니다.  현재 행에 수정된 셀이 없거나 <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> 이벤트 처리기에서 <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=fullName> 속성 값이 `false`로 설정된 경우에는 이 이벤트가 발생하지 않습니다.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#170](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#170)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#170](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#170)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#170](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#170)]  
  
9. 기존 `Customer` 개체를 데이터 저장소에서 삭제하거나 새로 만들어진 행을 나타내는 저장되지 않은 `Customer` 개체를 삭제하는 <xref:System.Windows.Forms.DataGridView.UserDeletingRow> 이벤트 처리기를 구현합니다.  
  
     이 이벤트는 사용자가 행 머리글을 클릭하고 Delete 키를 눌러 행을 삭제할 때마다 발생합니다.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#180](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#180)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#180](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#180)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#180](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#180)]  
  
10. 이 코드 예제에서 사용하는 데이터 항목을 나타내기 위한 간단한 `Customers` 클래스를 구현합니다.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#200](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#200)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#200](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#200)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#200](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#200)]  
  
## 응용 프로그램 테스트  
 이제 폼을 테스트하여 예상한 대로 동작하는지 확인할 수 있습니다.  
  
#### 폼을 테스트하려면  
  
-   응용 프로그램을 컴파일하여 실행합니다.  
  
     세 개의 고객 레코드로 채워진 <xref:System.Windows.Forms.DataGridView> 컨트롤이 표시됩니다.  행의 여러 셀 값을 수정한 다음 Esc 키를 편집 모드에서 두 번 누르거나 편집 모드 이외의 모드에서 한 번 눌러 전체 행을 원래 값으로 되돌릴 수 있습니다.  컨트롤에서 행을 수정, 추가 또는 삭제하면 데이터 저장소에 있는 `Customer` 개체도 수정, 추가 또는 삭제됩니다.  
  
## 다음 단계  
 이 응용 프로그램에서는 <xref:System.Windows.Forms.DataGridView> 컨트롤에서 가상 모드를 구현하기 위해 처리해야 하는 이벤트에 대한 기본적인 이해를 제공합니다.  다양한 방법으로 이 기본 응용 프로그램을 향상시킬 수 있습니다.  
  
-   외부 데이터베이스의 값을 캐시하는 데이터 저장소를 구현합니다.  이 캐시는 클라이언트 컴퓨터의 메모리를 적게 소비하면서 표시해야 할 내용만 포함할 수 있도록 필요에 따라 값을 검색하고 삭제할 수 있어야 합니다.  
  
-   요구 사항에 따라 데이터 저장소의 성능을 세밀하게 조정합니다.  예를 들어, 캐시 크기를 크게하고 데이터베이스 쿼리 수를 최소화하여 클라이언트 컴퓨터 메모리를 제한하기 보다는 네트워크 연결 부하를 줄여야 할 수 있습니다.  
  
 외부 데이터베이스의 값을 캐시하는 방법에 대한 자세한 내용은 [방법: Windows Forms DataGridView 컨트롤에서 Just\-In\-Time 데이터 로드를 사용하여 가상 모드 구현](../../../../docs/framework/winforms/controls/virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>   
 <xref:System.Windows.Forms.DataGridView.CellValueNeeded>   
 <xref:System.Windows.Forms.DataGridView.CellValuePushed>   
 <xref:System.Windows.Forms.DataGridView.NewRowNeeded>   
 <xref:System.Windows.Forms.DataGridView.RowValidated>   
 <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>   
 <xref:System.Windows.Forms.DataGridView.CancelRowEdit>   
 <xref:System.Windows.Forms.DataGridView.UserDeletingRow>   
 [Windows Forms DataGridView 컨트롤의 성능 조정](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)   
 [Windows Forms DataGridView 컨트롤의 크기를 조정하는 최선의 방법](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)   
 [Windows Forms DataGridView 컨트롤에서 Just\-In\-Time 데이터 로드를 사용하여 가상 모드 구현](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)   
 [방법: Windows Forms DataGridView 컨트롤에서 가상 모드 구현](../../../../docs/framework/winforms/controls/how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)