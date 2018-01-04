---
title: "Windows Forms DataGridView 컨트롤에서 Just-In-Time 데이터 로드를 사용하여 가상 모드 구현"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], just-in-time data loading
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- just-in-time data loading
- DataGridView control [Windows Forms], large data sets
- virtual mode [Windows Forms], just-in-time data loading
ms.assetid: c2a052b9-423c-4ff7-91dc-d8c7c79345f6
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2a830c11e8df73b71f16c1b9dfd1007461d910f5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="implementing-virtual-mode-with-just-in-time-data-loading-in-the-windows-forms-datagridview-control"></a>Windows Forms DataGridView 컨트롤에서 Just-In-Time 데이터 로드를 사용하여 가상 모드 구현
가상 모드 구현 하는 한 가지 이유는 <xref:System.Windows.Forms.DataGridView> 컨트롤 필요할 때에 데이터를 검색 하는 것입니다. 이 라고 *-just-in-time 데이터 로드*합니다.  
  
 원격 데이터베이스에서 매우 큰 테이블을 사용 하는 경우 표시 하기 위해 필요한 데이터만 검색 하 고 사용자는 새 행을 뷰로 스크롤합니다 하는 경우에 추가 데이터를 검색 하 여 시작이 지연 되지 않도록 하려는 예를 들어 있습니다. 응용 프로그램을 실행 하는 클라이언트 컴퓨터 데이터를 저장 하는 데 사용할 수 있는 메모리 양이 제한 되어 있으면 데이터베이스에서 새 값을 검색할 때 사용 되지 않는 데이터를 삭제할 수도 있습니다.  
  
 다음 섹션에서는 사용 하는 방법에 설명 된 <xref:System.Windows.Forms.DataGridView> 적시에 캐시 된 컨트롤입니다.  
  
 단일 목록으로이 항목의 코드를 복사 하려면 참조 [하는 방법: Windows Forms DataGridView 컨트롤에서 Just-In-Time 데이터 로드와 가상 모드 구현](../../../../docs/framework/winforms/controls/virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)합니다.  
  
## <a name="the-form"></a>폼  
 다음 코드 예제에서는 읽기 전용를 포함 하는 폼 정의 <xref:System.Windows.Forms.DataGridView> 제어와 상호 작용 하는 `Cache` 개체를 통해는 <xref:System.Windows.Forms.DataGridView.CellValueNeeded> 이벤트 처리기입니다. `Cache` 개체는 로컬에 저장 된 값을 관리 하 고 사용 하 여 한 `DataRetriever` Northwind 샘플 데이터베이스의 Orders 테이블에서 값을 검색 하는 개체입니다. `DataRetriever` 구현 하는 개체는 `IDataPageRetriever` 에 필요한 인터페이스는 `Cache` 클래스를 초기화 하는 데도 사용는 <xref:System.Windows.Forms.DataGridView> 행과 열을 제어 합니다.  
  
 `IDataPageRetriever`, `DataRetriever`, 및 `Cache` 형식은이 항목의 뒷부분에 설명 됩니다.  
  
> [!NOTE]
>  암호와 같은 중요한 정보를 연결 문자열 내에 저장하면 응용 프로그램 보안 문제가 발생할 수 있습니다. 데이터베이스 액세스를 제어할 경우에는 통합 보안이라고도 하는 Windows 인증을 사용하는 방법이 더 안전합니다. 자세한 내용은 [연결 정보 보호](../../../../docs/framework/data/adonet/protecting-connection-information.md)를 참조하세요.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#100)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#100)]  
  
## <a name="the-idatapageretriever-interface"></a>IDataPageRetriever 인터페이스  
 다음 코드 예제에서는 정의 `IDataPageRetriever` 에서 구현 하는 인터페이스는 `DataRetriever` 클래스입니다. 이 인터페이스에 선언 된 유일한 방법은 `SupplyPageOfData` 초기 행 인덱스 및 데이터의 단일 페이지의 행 수의 수가 시켜야 하는 방법입니다. 이러한 값은 데이터 원본에서 데이터 하위 집합을 검색 하려면 구현 자가 사용 됩니다.  
  
 A `Cache` 개체는 생성 되는 동안이 인터페이스의 구현을 로드할 데이터의 초기 두 페이지를 사용 하 여 합니다. 캐시 되지 않은 값 필요할 때마다 캐시 이러한 페이지 중 하나를 삭제 하 고 요청에서 값이 포함 된 새 페이지는 `IDataPageRetriever`합니다.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#201)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#201](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#201)]  
  
## <a name="the-dataretriever-class"></a>DataRetriever 클래스  
 다음 코드 예제에서는 정의 `DataRetriever` 클래스를 구현 하는 `IDataPageRetriever` 는 서버에서 데이터 페이지를 검색 하는 인터페이스입니다. `DataRetriever` 클래스 제공 `Columns` 및 `RowCount` 속성을 하는 <xref:System.Windows.Forms.DataGridView> 필요한 열을 만들고 적절 한 개수의에 빈 행을 추가 하려면 컨트롤에 사용 하 여는 <xref:System.Windows.Forms.DataGridView.Rows%2A> 컬렉션입니다. 빈 행을 추가 하는 데 필요 컨트롤은 테이블의 모든 데이터를 포함 하는 것 처럼 동작 합니다. 즉, 스크롤 막대의 스크롤 상자 적절 한 크기를 가집니다 하며 사용자는 테이블의 모든 행에 액세스할 수 됩니다. 행으로 채워집니다.는 <xref:System.Windows.Forms.DataGridView.CellValueNeeded> 뷰로 스크롤할 경우에 이벤트 처리기입니다.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#200)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#200](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#200)]  
  
## <a name="the-cache-class"></a>캐시 클래스  
 다음 코드 예제에서는 정의 `Cache` 통해 채워지는 데이터의 두 페이지를 관리 하는 클래스는 `IDataPageRetriever` 구현 합니다. `Cache` 클래스 정의 내부 조인 `DataPage` 포함 된 구조는 <xref:System.Data.DataTable> 페이지와 행 인덱스를 계산 하 나타내는 페이지의 위쪽과 아래쪽 경계는 단일 캐시에는 값을 저장 합니다.  
  
 `Cache` 클래스 생성 시 데이터의 두 페이지를 로드 합니다. 때마다는 <xref:System.Windows.Forms.DataGridView.CellValueNeeded> 값을 요청 하는 이벤트는 `Cache` 값에서 사용할 수 있는 경우 두 중 페이지 하 고,이 경우 반환 개체를 확인 합니다. 값을 로컬로 사용할 수 없는 경우는 `Cache` 페이지 그런 다음 반환 되는 요청 된 값을 포함 하는 새 항목으로 대체와 현재 표시 된 행에서 가장 먼 두 페이지는 개체를 결정 합니다.  
  
 이라고 가정 하면 데이터 페이지의 행 수가 한 번에 화면에 표시 될 수 있는 행의 수와 동일 하 게,이 모델에서는 가장 최근에 본된 페이지를 효율적으로 돌아가려면 사용자는 테이블을 통해 페이징 합니다.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#300)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#300](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#300)]  
  
## <a name="additional-considerations"></a>추가 고려 사항  
 이전 코드 예제에서는-just-in-time 데이터 로드 데모로 제공 됩니다. 효율성을 극대화 하기 위해 고유한 요구 사항에 대 한 코드를 수정 해야 합니다. 최소한 캐시에 데이터의 페이지당 행 수에 대 한 적절 한 값을 선택 해야 합니다. 이 값에 전달 되는 `Cache` 생성자입니다. 페이지당 행 수를 동시에 표시 될 수 있는 행 개수 보다 더 작은 프로그램 <xref:System.Windows.Forms.DataGridView> 제어 합니다.  
  
 최상의 결과 위해 성능 테스트 및 유용성 시스템 및 사용자의 요구 사항을 결정 하는 테스트를 수행 해야 합니다. 고려해 야 할 여러 가지 요소는 응용 프로그램, 네트워크 연결을 사용 하는 사용 가능한 대역폭 및 사용 되는 서버의 대기 시간을 실행 하는 클라이언트 컴퓨터에 메모리의 양을 포함 합니다. 대역폭 및 대기 시간의 최대 사용량 시간에 확인 해야 합니다.  
  
 응용 프로그램의 스크롤 성능을 향상 시키기 위해 로컬로 저장 된 데이터의 크기를 늘릴 수 있습니다. 그러나 시작 시간을 향상 시키려면 하지 않도록 해야 처음에 너무 많은 데이터를 로드 합니다. 수정 하려는 경우는 `Cache` 저장할 수 있는 데이터 페이지 수를 늘리려면 클래스입니다. 더 많은 데이터 페이지를 사용 하 여 스크롤의 효율성을 향상 시킬 수 있지만 사용 가능한 대역폭 및 서버 대기 시간에 따라 데이터 페이지에 있는 행의 이상적인 수를 결정 해야 합니다. 적은 수의 페이지, 서버를 보다 자주 액세스할 수 있지만 요청한 데이터를 반환할 더 적은 시간이 걸립니다. 대기 시간은 대역폭 보다 문제, 경우에 더 큰 데이터 페이지를 사용 하는 것이 좋습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 [Windows Forms DataGridView 컨트롤의 성능 조정](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 [Windows Forms DataGridView 컨트롤의 크기를 조정하는 최선의 방법](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 [Windows Forms DataGridView 컨트롤의 가상 모드](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)  
 [연습: Windows Forms DataGridView 컨트롤에서 가상 모드 구현](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)  
 [방법: Windows Forms DataGridView 컨트롤에서 Just-In-Time 데이터 로드를 사용하여 가상 모드 구현](../../../../docs/framework/winforms/controls/virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)
