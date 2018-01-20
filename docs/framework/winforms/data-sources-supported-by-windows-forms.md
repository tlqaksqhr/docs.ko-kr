---
title: "Windows Forms에서 지원하는 데이터 소스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- collections [Windows Forms], binding to
- OLE DB providers [Windows Forms], Windows Forms
- DataTable class [Windows Forms], binding and Windows Forms
- Windows Forms, data binding
- DataView class [Windows Forms], binding and Windows Forms
- DataViewManager class [Windows Forms], binding and Windows Forms
- Windows Forms, source data
- arrays [Windows Forms]
- data sources [Windows Forms]
- data providers [Windows Forms]
- DataSet class [Windows Forms], binding and Windows Forms
- data [Windows Forms], data providers
ms.assetid: 3d2c43f6-462b-4d35-9c86-13e9afe012e1
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5a0a4c2bca136377b9c6812008189dae009e195f
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="data-sources-supported-by-windows-forms"></a>Windows Forms에서 지원하는 데이터 소스
일반적으로 데이터 바인딩을 사용 되었습니다 응용 프로그램 내에서 데이터베이스에 저장 된 데이터를 활용 하려면. Windows Forms 데이터 바인딩, 최소한의 특정 요구를 충족으로 배열 및 컬렉션 등의 다른 구조에 있는 데이터와 데이터베이스에서 데이터를 액세스할 수 있습니다.  
  
## <a name="structures-to-bind-to"></a>바인딩할 구조  
 Windows Forms에서 바인딩할 수 있습니다 구조체의 광범위 한 단순한 ADO.NET 데이터 테이블 (복잡 한 바인딩) 같은 복잡 한 목록에 있는 개체 (단순 바인딩) 합니다. 단순 바인딩에 대 한 Windows Forms는 단순 개체에 공용 속성에 바인딩을 지원합니다. Windows Forms 목록 기반 바인딩에 일반적으로 지 원하는 개체 필요는 <xref:System.Collections.IList> 인터페이스 또는 <xref:System.ComponentModel.IListSource> 인터페이스입니다. 또한를 통해 바인딩하는 경우는 <xref:System.Windows.Forms.BindingSource> 구성 요소를 지 원하는 개체를 바인딩할 수 있습니다는 <xref:System.Collections.IEnumerable> 인터페이스입니다. 데이터 바인딩과 관련 된 인터페이스에 대 한 자세한 내용은 참조 [인터페이스와 관련 된 데이터 바인딩](../../../docs/framework/winforms/interfaces-related-to-data-binding.md)합니다.  
  
 다음 목록에는 Windows Forms에서 바인딩할 수 있습니다는 구조를 보여 줍니다.  
  
 <xref:System.Windows.Forms.BindingSource>  
 A <xref:System.Windows.Forms.BindingSource> 는 가장 일반적인 Windows Forms 데이터 원본 및 데이터 원본 서버와 Windows Forms 컨트롤 간의 프록시 역할을 합니다. 일반 <xref:System.Windows.Forms.BindingSource> 사용 패턴은 컨트롤을 바인딩하는 <xref:System.Windows.Forms.BindingSource> 바인딩하고 <xref:System.Windows.Forms.BindingSource> 데이터 원본 (예를 들어 ADO.NET 데이터 테이블 또는 비즈니스 개체)에 합니다. <xref:System.Windows.Forms.BindingSource> 및 데이터 바인딩 지원의 수준을 향상 시킬 수 있는 서비스를 제공 합니다. 그러나 예를 들어, Windows Forms 기반 하 여 목록 컨트롤 같은 <xref:System.Windows.Forms.DataGridView> 및 <xref:System.Windows.Forms.ComboBox> 바인딩을 직접 지원 하지 않습니다 <xref:System.Collections.IEnumerable> 데이터 원본이 시나리오를 통해 바인딩에서 사용할 수 있습니다는 <xref:System.Windows.Forms.BindingSource>합니다. 이 경우에 <xref:System.Windows.Forms.BindingSource> 데이터 원본에는 변환는 <xref:System.Collections.IList>합니다.  
  
 단순 개체  
 Windows Forms 공용 속성에 데이터 바인딩 컨트롤 속성을 사용 하 여 개체의 인스턴스에 대해 지원 된 <xref:System.Windows.Forms.Binding> 유형입니다. 또한 Windows Forms에서는 바인딩 목록 기반 컨트롤을와 같은 한 <xref:System.Windows.Forms.ListControl> 인스턴스에 개체에는 <xref:System.Windows.Forms.BindingSource> 사용 됩니다.  
  
 배열 또는 컬렉션  
 을 데이터 원본으로 작동 하려면 목록을 구현 해야는 <xref:System.Collections.IList> 하나, 인터페이스 예의 인스턴스가 있는 배열을 것은 <xref:System.Array> 클래스입니다. 배열에 대 한 자세한 내용은 참조 하십시오. [하는 방법: 한 배열의 개체 만들기 (Visual Basic)](http://msdn.microsoft.com/library/6b64e069-0387-400c-9081-3bdc581020c3)합니다.  
  
 일반적으로 사용 해야 <xref:System.ComponentModel.BindingList%601> 데이터 바인딩에 대 한 개체의 목록을 만들 때. <xref:System.ComponentModel.BindingList%601>제네릭 버전의는 <xref:System.ComponentModel.IBindingList> 인터페이스입니다. <xref:System.ComponentModel.IBindingList> 확장 인터페이스는 <xref:System.Collections.IList> 속성, 메서드 및 양방향 데이터 바인딩을에 필요한 이벤트를 추가 하 여 인터페이스입니다.  
  
 <xref:System.Collections.IEnumerable>  
 Windows Forms 컨트롤을 지 원하는 데이터 원본에 바인딩될 수는 <xref:System.Collections.IEnumerable> 통해 바인딩된 경우 인터페이스는 <xref:System.Windows.Forms.BindingSource> 구성 요소입니다.  
  
 [!INCLUDE[vstecado](../../../includes/vstecado-md.md)]데이터 개체  
 [!INCLUDE[vstecado](../../../includes/vstecado-md.md)]다양 한 데이터 구조에 대 한 바인딩에 적합 한를 제공 합니다. 각 구조 복잡성에 따라 다릅니다.  
  
-   <xref:System.Data.DataColumn>. A <xref:System.Data.DataColumn> 은의 필수 구성 요소는 <xref:System.Data.DataTable>을 열 수를 하나의 테이블을 구성 합니다. 각 <xref:System.Data.DataColumn> 에 <xref:System.Data.DataColumn.DataType%2A> 데이터 열에 저장 (예를 들어, 자동차를 설명 하는 테이블에 있는 자동차의 제조업체)의 종류를 결정 하는 속성입니다. 바인딩할 수 있습니다 단순 컨트롤 (같은 <xref:System.Windows.Forms.TextBox> 컨트롤의 <xref:System.Windows.Forms.Control.Text%2A> 속성) 데이터 테이블 내의 열입니다.  
  
-   <xref:System.Data.DataTable>. A <xref:System.Data.DataTable> 에 행과 열이 있는 테이블의 표현인 [!INCLUDE[vstecado](../../../includes/vstecado-md.md)]합니다. 두 컬렉션을 포함 하는 데이터 테이블: <xref:System.Data.DataColumn>, (최종적으로 결정 하는 해당 테이블에 입력할 수 있는 데이터)는 지정된 된 테이블에 데이터의 열을 나타내는 및 <xref:System.Data.DataRow>, 지정된 된 테이블에 데이터 행을 나타내는입니다. 바인딩할 수 있습니다 복합 컨트롤을 데이터 테이블에 포함 된 정보 (바인딩 등의 <xref:System.Windows.Forms.DataGridView> 컨트롤을 데이터 테이블에). 그러나에 바인딩하는 경우는 <xref:System.Data.DataTable>, 테이블의 기본 보기에 실제로 바인딩 됩니다.  
  
-   <xref:System.Data.DataView>. A <xref:System.Data.DataView> 필터링 하거나 정렬할 수 있는 단일 데이터 테이블의 사용자 지정 된 뷰입니다. 데이터 뷰는 "스냅숏" 복합 바인딩된 컨트롤에서 사용 하는 데이터입니다. 있습니다 수 단순 바인딩 또는 복합 바인딩할 데이터 뷰의 데이터 있지만 잘 정리 되 고 업데이트 하는 데이터 원본 대신 데이터의 고정된 된 "화면"에 바인딩하는 점에 유의 합니다.  
  
-   <xref:System.Data.DataSet>. A <xref:System.Data.DataSet> 는 테이블, 관계 및 제약 조건 데이터베이스의 데이터의 컬렉션입니다. 있습니다 수 단순 바인딩할 또는 복잡 한 바인딩은 데이터 집합 내의 데이터에 있지만 기본값을 바인딩하는 점에 유의 <xref:System.Data.DataViewManager> 에 대 한는 <xref:System.Data.DataSet> (다음 글머리 참조).  
  
-   <xref:System.Data.DataViewManager>. A <xref:System.Data.DataViewManager> 전체의 사용자 지정된 보기는 <xref:System.Data.DataSet>뷰이며는 <xref:System.Data.DataView>, 비슷하지만 관계가 포함 됩니다. 와 <xref:System.Data.DataViewManager.DataViewSettings%2A> 컬렉션을 설정할 수 있습니다 기본 필터 및 정렬 옵션에 대 한 모든 뷰는는 <xref:System.Data.DataViewManager> 에 지정된 된 테이블에 대 한 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Windows Forms 데이터 바인딩의 변경 알림](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 [데이터 바인딩 및 Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 [Windows Forms 데이터 바인딩](../../../docs/framework/winforms/windows-forms-data-binding.md)
