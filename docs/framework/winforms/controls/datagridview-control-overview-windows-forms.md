---
title: "DataGridView 컨트롤 개요(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: DataGridView
helpviewer_keywords:
- DataGridView control [Windows Forms], about DataGridView control
- grid controls [Windows Forms]
- tables [Windows Forms], displaying in DataGridView control
- tables [Windows Forms], binding to DataGridView control
- columns [Windows Forms], DataGridView control
- bound controls [Windows Forms], dataGridView control
- datasets [Windows Forms], binding to DataGridView control
- data grids [Windows Forms], about data grids
- data [Windows Forms], resorting
- data [Windows Forms], navigating
- grids [Windows Forms]
- data binding [Windows Forms], DataGridView control
- data sources [Windows Forms], binding to DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 0a45c661-89dc-4390-9cc6-c47eee501488
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6d9cc6568813af866acaf20696b870bedc3099be
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="datagridview-control-overview-windows-forms"></a>DataGridView 컨트롤 개요(Windows Forms)
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다. 자세한 내용은 [Windows Forms DataGridView 및 DataGrid 컨트롤의 차이점](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.  
  
 와 <xref:System.Windows.Forms.DataGridView> 컨트롤을 표시 하 고 다양 한 종류의 데이터 원본에서 테이블 형식 데이터를 편집할 수 있습니다.  
  
 에 데이터 바인딩는 <xref:System.Windows.Forms.DataGridView> 컨트롤 쉽고 직관적으로 지정 되며 대부분의 경우에서로 설정 하기만 하면는 <xref:System.Windows.Forms.DataGridView.DataSource%2A> 속성입니다. 여러 목록 또는 테이블을 포함 하는 데이터 소스에 바인딩하는 경우 설정의 <xref:System.Windows.Forms.DataGridView.DataMember%2A> 속성을 목록 또는 바인딩할 테이블을 지정 하는 문자열입니다.  
  
 <xref:System.Windows.Forms.DataGridView> 컨트롤은 표준 Windows Forms 데이터 바인딩 모델을 지원 하므로 다음 목록에 설명 된 클래스의 인스턴스에 바인딩합니다.  
  
-   클래스를 구현 하는 모든 클래스는 <xref:System.Collections.IList> 인터페이스를 1 차원 배열을 포함 합니다.  
  
-   클래스를 구현 하는 모든 클래스는 <xref:System.ComponentModel.IListSource> 인터페이스와 같은 <xref:System.Data.DataTable> 및 <xref:System.Data.DataSet> 클래스입니다.  
  
-   클래스를 구현 하는 모든 클래스는 <xref:System.ComponentModel.IBindingList> 인터페이스와 같은 <xref:System.ComponentModel.BindingList%601> 클래스입니다.  
  
-   클래스를 구현 하는 모든 클래스는 <xref:System.ComponentModel.IBindingListView> 인터페이스와 같은 <xref:System.Windows.Forms.BindingSource> 클래스입니다.  
  
 <xref:System.Windows.Forms.DataGridView> 컨트롤은 이러한 인터페이스에서 반환 된 개체의 공용 속성 또는 속성 컬렉션에서 반환 된 데이터 바인딩을 지원는 <xref:System.ComponentModel.ICustomTypeDescriptor> 인터페이스, 반환 된 개체에 구현 된 경우.  
  
 일반적으로 바인딩할는 <xref:System.Windows.Forms.BindingSource> 구성 요소 및 바인딩은 <xref:System.Windows.Forms.BindingSource> 구성 요소를 다른 데이터 원본 또는 비즈니스 개체를 채웁니다. <xref:System.Windows.Forms.BindingSource> 다양 한 데이터 소스에 바인딩할 수 하 고 자동으로 많은 데이터 바인딩 문제를 해결할 수 있기 때문에 구성 요소는 기본 데이터 원본. 자세한 내용은 참조 [BindingSource 구성 요소](../../../../docs/framework/winforms/controls/bindingsource-component.md)합니다.  
  
 <xref:System.Windows.Forms.DataGridView> 컨트롤에 사용할 수도 있습니다 *언바운드* 없는 기본 데이터 저장소 모드입니다. 바인딩되지 않은 사용 하는 코드 예제에 대 한 <xref:System.Windows.Forms.DataGridView> 제어, 참조 [연습: 바인딩되지 않은 Windows Forms DataGridView 컨트롤 만들기](../../../../docs/framework/winforms/controls/walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)합니다.  
  
 <xref:System.Windows.Forms.DataGridView> 컨트롤은 고도로 구성 가능 하며 확장 가능 하 고 여러 속성, 메서드 및 해당 모양 및 동작을 사용자 지정 하는 이벤트를 제공 합니다. 테이블 형식 데이터를 표시 하는 Windows Forms 응용 프로그램을 사용할 때는 <xref:System.Windows.Forms.DataGridView> 다른 대체 이전 컨트롤 (예를 들어 <xref:System.Windows.Forms.DataGrid>). 읽기 전용 값의 작은 눈금을 표시 하는 경우 또는 수백만 개의 레코드를 테이블을 편집 하는 사용자를 설정 하는 경우는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 쉽게 프로그래밍할, 메모리 효율적인 솔루션으로 제공 합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [DataGridView 컨트롤 기술 요약](../../../../docs/framework/winforms/controls/datagridview-control-technology-summary-windows-forms.md)  
 요약 <xref:System.Windows.Forms.DataGridView> 개념 및 관련된 클래스의 사용을 제어 합니다.  
  
 [DataGridView 컨트롤 아키텍처](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)  
 아키텍처를 설명는 <xref:System.Windows.Forms.DataGridView> 해당 형식 계층 구조 및 상속 구조를 설명 하는 컨트롤입니다.  
  
 [DataGridView 컨트롤 시나리오](../../../../docs/framework/winforms/controls/datagridview-control-scenarios-windows-forms.md)  
 가장 일반적인 시나리오에 설명 <xref:System.Windows.Forms.DataGridView> 컨트롤을 사용 합니다.  
  
 [DataGridView 컨트롤 코드 디렉터리](../../../../docs/framework/winforms/controls/datagridview-control-code-directory-windows-forms.md)  
 다양 한 설명서의 코드 예제에 대 한 링크를 제공 <xref:System.Windows.Forms.DataGridView> 작업 합니다. 이러한 예제는 작업 형식별로 분류되어 제공됩니다.  
  
## <a name="related-sections"></a>관련 단원  
 [Windows Forms DataGridView 컨트롤의 열 형식](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)  
 Windows Forms에서의 열 형식을 설명 <xref:System.Windows.Forms.DataGridView> 컨트롤 정보를 표시 하며 정보를 수정 하거나 추가할 수 있도록 하는 데 사용 합니다.  
  
 [Windows Forms DataGridView 컨트롤에서 데이터 표시](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 수동으로 또는 외부 데이터 소스에서 컨트롤을 데이터로 채우는 방법을 설명하는 항목을 제공합니다.  
  
 [Windows Forms DataGridView 컨트롤 사용자 지정](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 <xref:System.Windows.Forms.DataGridView> 셀 및 행의 사용자 지정 그리기를 수행하고 파생된 셀, 열 및 행 형식을 설명하는 항목을 제공합니다.  
  
 [Windows Forms DataGridView 컨트롤의 성능 조정](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 컨트롤을 효율적으로 사용하여 대용량 데이터를 사용할 때 성능 문제를 방지하는 방법을 설명하는 항목을 제공합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [DataGridView 컨트롤](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [Windows Forms DataGridView 컨트롤의 기본 기능](../../../../docs/framework/winforms/controls/default-functionality-in-the-windows-forms-datagridview-control.md)  
 [Windows Forms DataGridView 컨트롤에서의 기본 키보드 및 마우스 처리](../../../../docs/framework/winforms/controls/default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)
