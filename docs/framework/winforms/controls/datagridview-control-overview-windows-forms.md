---
title: "DataGridView 컨트롤 개요(Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DataGridView"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "바인딩 컨트롤, DataGridView 컨트롤"
  - "열[Windows Forms], DataGridView 컨트롤"
  - "데이터[Windows Forms], 탐색"
  - "데이터[Windows Forms], 다시 정렬"
  - "데이터 바인딩(data binding), DataGridView 컨트롤"
  - "데이터 표, 데이터 표 정보"
  - "데이터 소스, DataGridView 컨트롤에 바인딩"
  - "DataGridView 컨트롤[Windows Forms], DataGridView 컨트롤 정보"
  - "DataGridView 컨트롤[Windows Forms], 데이터 바인딩(data binding)"
  - "데이터 집합[Windows Forms], DataGridView 컨트롤에 바인딩"
  - "표 컨트롤[Windows Forms]"
  - "[Windows Forms]"
  - "테이블[Windows Forms], DataGridView 컨트롤에 바인딩"
  - "테이블[Windows Forms], DataGridView 컨트롤에 표시"
ms.assetid: 0a45c661-89dc-4390-9cc6-c47eee501488
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 23
---
# DataGridView 컨트롤 개요(Windows Forms)
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다.  자세한 내용은 [Windows Forms DataGridView 컨트롤과 DataGrid 컨트롤의 차이점](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.  
  
 <xref:System.Windows.Forms.DataGridView> 컨트롤을 사용하면 여러 종류의 데이터 소스에서 가져온 표 형식의 데이터를 표시하고 편집할 수 있습니다.  
  
 데이터를 <xref:System.Windows.Forms.DataGridView> 컨트롤에 바인딩하는 작업은 많은 경우에 <xref:System.Windows.Forms.DataGridView.DataSource%2A> 속성을 설정하는 작업과 마찬가지로 단순합니다.  여러 목록이나 표가 포함된 데이터 소스에 바인딩하는 경우에는 <xref:System.Windows.Forms.DataGridView.DataMember%2A> 속성을 바인딩할 목록이나 표를 지정하는 문자열로 설정합니다.  
  
 <xref:System.Windows.Forms.DataGridView> 컨트롤은 표준 Windows Forms 데이터 바인딩 모델을 지원하므로 다음 목록에 설명된 클래스의 인스턴스에 바인딩됩니다.  
  
-   1차원 배열을 비롯한 <xref:System.Collections.IList> 인터페이스를 구현하는 모든 클래스  
  
-   <xref:System.Data.DataTable> 및 <xref:System.Data.DataSet> 클래스와 같은 <xref:System.ComponentModel.IListSource> 인터페이스를 구현하는 모든 클래스  
  
-   <xref:System.ComponentModel.BindingList%601> 클래스와 같은 <xref:System.ComponentModel.IBindingList> 인터페이스를 구현하는 모든 클래스  
  
-   <xref:System.Windows.Forms.BindingSource> 클래스와 같은 <xref:System.ComponentModel.IBindingListView> 인터페이스를 구현하는 모든 클래스  
  
 <xref:System.Windows.Forms.DataGridView> 컨트롤을 사용하면 반환된 개체에 구현된 경우 이러한 인터페이스에서 반환된 개체의 공용 속성이나 <xref:System.ComponentModel.ICustomTypeDescriptor> 인터페이스에서 반환된 속성 컬렉션에 데이터를 바인딩할 수 있습니다.  
  
 일반적으로 <xref:System.Windows.Forms.BindingSource> 구성 요소에 바인딩한 다음 <xref:System.Windows.Forms.BindingSource> 구성 요소를 다른 데이터 소스에 바인딩하거나 비즈니스 개체로 구성 요소를 채웁니다.  <xref:System.Windows.Forms.BindingSource> 구성 요소는 다양한 데이터 소스에 바인딩할 수 있고 많은 데이터 바인딩 문제를 자동으로 해결할 수 있기 때문에 데이터 소스로 많이 사용됩니다.  자세한 내용은 [BindingSource 구성 요소](../../../../docs/framework/winforms/controls/bindingsource-component.md)를 참조하십시오.  
  
 <xref:System.Windows.Forms.DataGridView> 컨트롤은 내부 데이터 저장소 없이 *바인딩되지 않은* 모드에서도 사용할 수 있습니다.  바인딩되지 않은 <xref:System.Windows.Forms.DataGridView> 컨트롤을 사용하는 코드 예제는 [연습: 바인딩되지 않은 Windows Forms DataGridView 컨트롤 만들기](../../../../docs/framework/winforms/controls/walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)를 참조하십시오.  
  
 <xref:System.Windows.Forms.DataGridView> 컨트롤은 매우 다양하게 구성하고 확장할 수 있으며, 모양과 동작을 사용자 지정할 수 있는 여러 가지 속성, 메서드 및 이벤트를 제공합니다.  Windows Forms 응용 프로그램에서 표 형식의 데이터를 표시하려면 <xref:System.Windows.Forms.DataGrid> 등의 다른 컨트롤을 사용하기 전에 <xref:System.Windows.Forms.DataGridView> 컨트롤을 먼저 사용하는 것이 좋습니다.  읽기 전용 값으로 채워진 작은 표를 표시하거나 수 백만 개의 레코드가 들어 있는 테이블을 사용자가 편집할 수 있도록 하려는 경우에 <xref:System.Windows.Forms.DataGridView> 컨트롤을 프로그래밍하기 쉽고 메모리 효율적인 솔루션으로 사용할 수 있습니다.  
  
## 단원 내용  
 [DataGridView 컨트롤 기술 요약](../../../../docs/framework/winforms/controls/datagridview-control-technology-summary-windows-forms.md)  
 <xref:System.Windows.Forms.DataGridView> 컨트롤 개념과 관련 클래스의 사용 방법을 요약합니다.  
  
 [DataGridView 컨트롤 아키텍처](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)  
 <xref:System.Windows.Forms.DataGridView> 컨트롤의 아키텍처, 형식 계층 구조 및 상속 구조를 설명합니다.  
  
 [DataGridView 컨트롤 시나리오](../../../../docs/framework/winforms/controls/datagridview-control-scenarios-windows-forms.md)  
 <xref:System.Windows.Forms.DataGridView> 컨트롤이 가장 일반적으로 사용되는 시나리오를 설명합니다.  
  
 [DataGridView 컨트롤 코드 디렉터리](../../../../docs/framework/winforms/controls/datagridview-control-code-directory-windows-forms.md)  
 다양한 <xref:System.Windows.Forms.DataGridView> 작업에 대한 설명서에 포함된 코드 예제를 볼 수 있는 링크를 제공합니다.  이러한 예제는 작업 형식별로 분류됩니다.  
  
## 관련 단원  
 [Windows Forms DataGridView 컨트롤의 열 형식](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)  
 정보를 표시하고 사용자가 정보를 수정하거나 추가할 수 있도록 하는 데 사용되는 Windows Forms <xref:System.Windows.Forms.DataGridView> 컨트롤의 열 형식을 설명합니다.  
  
 [Windows Forms DataGridView 컨트롤에서 데이터 표시](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 컨트롤에 수동으로 데이터를 채우거나 외부 데이터 소스에서 데이터를 가져와서 컨트롤을 채우는 방법을 설명하는 항목을 제공합니다.  
  
 [Windows Forms DataGridView 컨트롤 사용자 지정](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 <xref:System.Windows.Forms.DataGridView> 셀과 행을 사용자 지정 방식으로 그리는 방법과 파생 셀, 열 및 행 형식을 만드는 방법을 설명하는 항목을 제공합니다.  
  
 [Windows Forms DataGridView 컨트롤의 성능 조정](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 많은 양의 데이터 작업을 수행할 때 컨트롤을 효율적으로 사용하여 성능 문제를 해결하는 방법을 설명하는 항목을 제공합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.BindingSource>   
 [DataGridView 컨트롤](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)   
 [Windows Forms DataGridView 컨트롤의 기본 기능](../../../../docs/framework/winforms/controls/default-functionality-in-the-windows-forms-datagridview-control.md)   
 [Windows Forms DataGridView 컨트롤에서의 기본 키보드 및 마우스 처리](../../../../docs/framework/winforms/controls/default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)