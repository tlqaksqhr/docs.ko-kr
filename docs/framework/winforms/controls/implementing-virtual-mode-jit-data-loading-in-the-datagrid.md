---
title: "Windows Forms DataGridView 컨트롤에서 Just-In-Time 데이터 로드를 사용하여 가상 모드 구현 | Microsoft Docs"
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
  - "예제[Windows Forms], just-in-time 데이터 로드"
  - "just-in-time 데이터 로드"
  - "가상 모드, just-in-time 데이터 로드"
ms.assetid: c2a052b9-423c-4ff7-91dc-d8c7c79345f6
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Windows Forms DataGridView 컨트롤에서 Just-In-Time 데이터 로드를 사용하여 가상 모드 구현
<xref:System.Windows.Forms.DataGridView> 컨트롤에서 가상 모드를 구현하는 이유 중 하나는 필요한 경우에만 데이터를 검색하기 위해서입니다.  이를  *Just\-In\-Time 데이터 로드*라고 합니다.  
  
 예를 들어, 원격 데이터베이스에서 매우 큰 테이블을 사용하는 경우 표시할 데이터만 검색하고 사용자가 새 행을 뷰로 스크롤할 때만 데이터를 추가로 검색하여 시작이 지연되지 않게 할 수 있습니다.  응용 프로그램을 실행하는 클라이언트 컴퓨터의 데이터 저장 메모리 양이 제한된 경우 데이터베이스에서 새 값을 검색할 때 사용되지 않는 데이터를 삭제할 수도 있습니다.  
  
 다음 단원에서는 Just\-In\-Time 캐시로 <xref:System.Windows.Forms.DataGridView> 컨트롤을 사용하는 방법에 대해 설명합니다.  
  
 이 항목의 코드를 단일 목록으로 복사하려면 [방법: Windows Forms DataGridView 컨트롤에서 Just\-In\-Time 데이터 로드를 사용하여 가상 모드 구현](../../../../docs/framework/winforms/controls/virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)을 참조하십시오.  
  
## 폼  
 다음 코드 예제에서는 <xref:System.Windows.Forms.DataGridView.CellValueNeeded> 이벤트 처리기를 통해 `Cache` 개체와 상호 작용하는 읽기 전용 <xref:System.Windows.Forms.DataGridView> 컨트롤을 포함하는 폼을 정의합니다.  `Cache` 개체는 로컬로 저장된 값을 관리하고 `DataRetriever` 개체를 사용하여 샘플 Northwind 데이터베이스의 Orders 테이블에서 값을 검색합니다.  `Cache` 클래스에 필요한 `IDataPageRetriever` 인터페이스를 구현하는 `DataRetriever` 개체는 <xref:System.Windows.Forms.DataGridView> 컨트롤 행 및 열을 초기화하는 데에도 사용됩니다.  
  
 `IDataPageRetriever`, `DataRetriever` 및 `Cache` 형식에 대한 설명은 이 항목의 뒷부분을 참조하십시오.  
  
> [!NOTE]
>  연결 문자열에 중요한 정보\(예: 암호\)를 저장하면 응용 프로그램 보안 문제가 발생할 수 있습니다.  데이터베이스 액세스를 제어할 경우에는 통합 보안이라고도 하는 Windows 인증을 사용하는 방법이 더 안전합니다.  자세한 내용은 [연결 정보 보호](../../../../docs/framework/data/adonet/protecting-connection-information.md)을 참조하십시오.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#100)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#100)]  
  
## IDataPageRetriever 인터페이스  
 다음 코드 예제에서는 `DataRetriever` 클래스에서 구현하는 `IDataPageRetriever` 인터페이스를 정의합니다.  이 인터페이스에 선언된 유일한 메서드는 `SupplyPageOfData` 메서드이며 이 메서드에는 데이터의 단일 페이지에 있는 초기 행 인덱스 및 행 수가 필요합니다.  이러한 값은 데이터 소스에서 데이터 하위 집합을 검색하기 위해 구현자에서 사용됩니다.  
  
 `Cache` 개체는 데이터의 두 초기 페이지를 로드하기 위해 생성하는 동안 이 인터페이스 구현을 사용합니다.  캐시되지 않은 값이 필요할 때마다 캐시는 이러한 페이지 중 하나를 삭제하고 `IDataPageRetriever`의 값을 포함하는 새 페이지를 요청합니다.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#201)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#201)]  
  
## DataRetriever 클래스  
 다음 코드 예제에서는 서버에서 데이터 페이지를 검색할 수 있는 `IDataPageRetriever` 인터페이스를 구현하는 `DataRetriever` 클래스를 정의합니다.  또한 `DataRetriever` 클래스는 <xref:System.Windows.Forms.DataGridView> 컨트롤에서 필요한 열을 만들고 적절한 개수의 빈 행을 <xref:System.Windows.Forms.DataGridView.Rows%2A> 컬렉션에 추가하는 데 사용되는 `Columns` 및 `RowCount` 속성을 제공합니다.  컨트롤이 테이블의 모든 데이터를 포함하는 것처럼 동작하도록 빈 행을 추가해야 합니다.  즉, 스크롤 막대의 스크롤 상자에 적절한 크기가 지정되며 사용자가 테이블의 모든 행에 액세스할 수 있어야 합니다.  행을 뷰로 스크롤할 때만 <xref:System.Windows.Forms.DataGridView.CellValueNeeded> 이벤트 처리기에 의해 행이 채워집니다.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#200)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#200)]  
  
## Cache 클래스  
 다음 코드 예제에서는 `IDataPageRetriever` 구현을 통해 채워지는 데이터의 두 페이지를 관리하는 `Cache` 클래스를 정의합니다.  `Cache` 클래스는 단일 캐시 페이지에 값을 저장하는 <xref:System.Data.DataTable>을 포함하고 페이지의 상한 및 하한을 나타내는 행 인덱스를 계산하는 내부 `DataPage` 구조체를 정의합니다.  
  
 `Cache` 클래스는 생성 시 데이터의 두 페이지를 로드합니다.  <xref:System.Windows.Forms.DataGridView.CellValueNeeded> 이벤트에서 값을 요청할 때마다 `Cache` 개체는 두 페이지 중 하나에서 해당 값을 사용할 수 있는지를 확인하고 사용 가능한 경우 해당 값을 반환합니다.  값을 로컬에서 사용할 수 없으면 `Cache` 개체는 두 페이지 중 현재 표시된 행에서 좀 더 멀리 떨어진 페이지를 확인하여 요청된 값을 포함하는 새 페이지로 바꾸고 기존 페이지를 반환합니다.  
  
 데이터 페이지의 행 수가 화면에 한 번에 표시할 수 있는 행 수와 같다고 가정하면 사용자는 이 모델을 사용하여 테이블 단위로 페이지를 탐색하여 최근에 본 페이지로 효율적으로 되돌아갈 수 있습니다.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#300)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#300)]  
  
## 추가 고려 사항  
 위의 코드 예제는 Just\-In\-Time 데이터 로드를 설명하기 위해 제공된 것입니다.  효율성을 극대화하려면 이 코드를 사용자의 요구에 맞게 수정해야 합니다.  적어도 캐시의 데이터 페이지 당 행 수에 대해 적절한 값을 선택해야 합니다.  이 값은 `Cache` 생성자에 전달됩니다.  페이지 당 행 수는 <xref:System.Windows.Forms.DataGridView> 컨트롤에 동시에 표시할 수 있는 행 수와 같아야 합니다.  
  
 최상의 결과를 얻으려면 성능 테스트 및 기능성 테스트를 수행하여 시스템과 사용자의 요구 사항을 확인해야 합니다.  응용 프로그램을 실행하는 클라이언트 컴퓨터의 메모리 양, 네트워크 연결의 사용 가능한 대역폭, 서버의 대기 시간 등 몇 가지 요소를 고려해야 합니다.  대역폭 및 대기 시간은 사용량이 가장 많은 시간에 확인해야 합니다.  
  
 응용 프로그램의 스크롤 성능을 향상시키려면 로컬로 저장된 데이터의 양을 늘립니다.  시작 시간을 향상시키려면 처음에 너무 많은 데이터를 로드하지 말아야 합니다.  `Cache` 클래스를 수정하여 저장할 수 있는 데이터 페이지 수를 늘릴 수도 있습니다.  많은 수의 데이터 페이지를 사용하면 스크롤의 효율성을 향상시킬 수 있지만 사용 가능한 대역폭 및 서버 대기 시간에 따라 데이터 페이지에 가장 적절한 행의 수를 결정해야 합니다.  적은 수의 페이지를 사용하면 서버가 더 자주 액세스되지만 요청된 데이터를 반환하는 데 시간이 적게 걸립니다.  대역폭보다 대기 시간에 중점을 두는 경우 보다 큰 데이터 페이지를 사용할 수도 있습니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>   
 [Windows Forms DataGridView 컨트롤의 성능 조정](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)   
 [Windows Forms DataGridView 컨트롤의 크기를 조정하는 최선의 방법](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)   
 [Windows Forms DataGridView 컨트롤의 가상 모드](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)   
 [연습: Windows Forms DataGridView 컨트롤에서 가상 모드 구현](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)   
 [방법: Windows Forms DataGridView 컨트롤에서 Just\-In\-Time 데이터 로드를 사용하여 가상 모드 구현](../../../../docs/framework/winforms/controls/virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)