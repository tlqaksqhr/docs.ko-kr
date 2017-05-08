---
title: "DataGrid 컨트롤 개요(Windows Forms) | Microsoft Docs"
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
  - "DataGrid"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "데이터 집합 [Windows Forms] DataGrid 컨트롤에 바인딩"
  - "데이터 바인딩, DataGrid 컨트롤"
  - "DataGrid 컨트롤 열 [Windows Forms]"
  - "데이터 소스, DataGrid 컨트롤에 바인딩"
  - "DataGrid 컨트롤에 바인딩 테이블 [Windows Forms]"
  - "데이터 바인딩 DataGrid 컨트롤 [Windows Forms]"
  - "DataGrid 컨트롤에 대 한 DataGrid 컨트롤 [Windows Forms]"
  - "DataGrid 컨트롤의 부모 표"
  - "DataGrid 컨트롤에 표시 되는 테이블 [Windows Forms]"
  - "데이터 표 정보 데이터 표"
  - "DataGrid 컨트롤의 다중 표"
  - "사용 데이터 [Windows Forms]"
  - "탐색 데이터 [Windows Forms]"
  - "DataGrid 컨트롤, 바인딩된 컨트롤"
  - "데이터 바인딩된 컨트롤을 DataGrid"
  - "DataGrid에서 부모 표 탐색"
  - "자식 테이블, DataGrid 컨트롤"
ms.assetid: 85604bce-bc03-49d9-9030-dda8896c44b1
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# DataGrid 컨트롤 개요(Windows Forms)
> [!NOTE]
>  그러나 <xref:System.Windows.Forms.DataGridView> 대체 하 고 기능을 추가 <xref:System.Windows.Forms.DataGrid> 컨트롤는 <xref:System.Windows.Forms.DataGrid> 컨트롤을 선택 하는 경우 이전 버전과 호환성 및 나중에 사용할 수 있도록 유지 합니다. 자세한 내용은 참조 [차이 Windows Forms DataGridView 컨트롤과 DataGrid 컨트롤의](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)합니다.  
  
 Windows Forms <xref:System.Windows.Forms.DataGrid> 컨트롤에서 일련의 행과 열 데이터를 표시 합니다. 가장 간단한 경우는 관계를 포함하지 않는 단일 테이블이 있는 데이터 소스에 표 형태 창이 바인딩된 경우입니다. 이 경우 스프레드시트와 같이 간단한 행과 열에 데이터가 나타납니다. 바인딩 데이터를 다른 컨트롤에 대 한 자세한 내용은 참조 [데이터 바인딩 및 Windows Forms](../../../../docs/framework/winforms/data-binding-and-windows-forms.md)합니다.  
  
 하는 경우는 <xref:System.Windows.Forms.DataGrid> 배수를 사용 하 여 데이터에 바인딩된 관련 테이블 및 표의 각 행에 확장 기가 표시 됩니다 모눈에 탐색을 사용 합니다. 사용자는 확장기를 통해 부모 테이블에서 자식 테이블로 이동할 수 있습니다. 노드를 클릭하면 자식 테이블이 표시되고 뒤로 단추를 클릭하면 원래 부모 테이블이 표시됩니다. 이런 방식으로 표 형태 창에 테이블 간의 계층 관계가 표시됩니다.  
  
 다음 스크린샷은 여러 테이블을 가진 데이터에 바인딩된 DataGrid를 보여 줍니다.  
  
 ![여러 테이블을 사용 하 여 데이터에 바인딩된 DataGrid](../../../../docs/framework/winforms/controls/media/vbcontrol1.gif "vbControl1")  
여러 테이블을 가진 데이터에 바인딩된 DataGrid  
  
 <xref:System.Windows.Forms.DataGrid> 데이터 집합, 관련된 테이블 및 서식 지정 및 편집 기능 간의 탐색을 위한 사용자 인터페이스를 제공할 수 있습니다.  
  
 데이터의 표시 및 조작은 별개 기능입니다. 컨트롤이 사용자 인터페이스를 처리하는 반면, 데이터 업데이트는 Windows Forms 데이터 바인딩 아키텍처 및 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 데이터 공급자에 의해 처리됩니다. 따라서 동일한 데이터 소스에 바인딩된 여러 컨트롤이 동기화 상태로 유지됩니다.  
  
> [!NOTE]
>  Windows Forms에서 중요 한 차이점이 있습니다. Visual Basic 6.0의 DataGrid 컨트롤에 익숙한 경우 <xref:System.Windows.Forms.DataGrid> 제어 합니다.  
  
 눈금에 바인딩된 경우는 <xref:System.Data.DataSet>, 열과 행이 자동으로, 형식이 지정 만들어지고 채워집니다. 자세한 내용은 [Data Binding and Windows Forms](../../../../docs/framework/winforms/data-binding-and-windows-forms.md)을 참조하세요. 생성 된 <xref:System.Windows.Forms.DataGrid> 컨트롤을 추가, 삭제, 다시 정렬 하 고 필요에 따라 열과 행 형식을 지정 합니다.  
  
## <a name="binding-data-to-the-control"></a>컨트롤에 데이터 바인딩  
 에 대 한는 <xref:System.Windows.Forms.DataGrid> 컨트롤이 작동 하려면, 사용 하 여 데이터 소스에 바인딩되어야는 <xref:System.Windows.Forms.DataGrid.DataSource%2A> 및 <xref:System.Windows.Forms.DataGrid.DataMember%2A> 디자인 타임에 속성 또는 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 런타임에 메서드. 이 바인딩은 가리키는 <xref:System.Windows.Forms.DataGrid> 인스턴스화된 데이터 소스 개체와 같은 <xref:System.Data.DataSet> 또는 <xref:System.Data.DataTable>). <xref:System.Windows.Forms.DataGrid> 컨트롤 데이터에 대해 수행 하는 작업의 결과 표시 합니다. 대부분의 데이터 관련 작업을 통해 수행 되지 않습니다는 <xref:System.Windows.Forms.DataGrid> , 않고 대신 데이터 소스를 통해.  
  
 바인딩된 데이터 집합의 데이터가 임의 메커니즘을 통해 업데이트 되는 경우는 <xref:System.Windows.Forms.DataGrid> 컨트롤이 변경 내용을 반영 합니다. 데이터 표에 테이블 스타일과 열 스타일의 `ReadOnly` 속성으로 설정 `false`, 데이터 집합의 데이터를 통해 업데이트할 수 있습니다는 <xref:System.Windows.Forms.DataGrid> 제어 합니다.  
  
 하나의 테이블에 표시 될 수는 <xref:System.Windows.Forms.DataGrid> 한 번에 있습니다. 에 표시할 테이블을 선택 하려면 관련된 테이블 간에 이동할 수 테이블 간에 부모-자식 관계는 정의 하는 경우는 <xref:System.Windows.Forms.DataGrid> 제어 합니다. 바인딩에 대 한 내용은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 한 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 디자인 타임 또는 런타임 시 데이터 원본 참조 [하는 방법: 데이터 소스에 Windows Forms DataGrid 컨트롤 바인딩](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)합니다.  
  
 에 대 한 유효한 데이터 소스는 <xref:System.Windows.Forms.DataGrid> 포함 합니다.  
  
-   <xref:System.Data.DataTable> 클래스  
  
-   <xref:System.Data.DataView> 클래스  
  
-   <xref:System.Data.DataSet> 클래스  
  
-   <xref:System.Data.DataViewManager> 클래스  
  
 소스가 데이터 집합인 경우 데이터 집합은 폼의 개체이거나 XML Web services에 의해 폼에 전달된 개체일 수 있습니다. 형식화된 데이터 집합이나 형식화되지 않은 데이터 집합에 바인딩할 수 있습니다.  
  
 바인딩할 수도 있습니다는 <xref:System.Windows.Forms.DataGrid> 개체, 배열에 요소와 같은 구조에 공용 속성을 노출 하는 경우 컨트롤을 추가 구조체입니다. 구조체에 있는 요소의 모든 public 속성이 표 형태 창에 표시됩니다. 예를 들어, 바인딩하는 경우는 <xref:System.Windows.Forms.DataGrid> 고객의 배열에는 컨트롤 개체의 형태는 해당 고객 개체의 모든 공용 속성이 표시 됩니다. 이는 일부 인스턴스에서 구조체에 바인딩할 수는 있지만 결과로 바인딩된 구조체가 실용적이지 않을 수 있음을 의미합니다. 예를 들어 정수 배열에 바인딩할 수는 있지만 `Integer` 데이터 형식이 public 속성을 지원하지 않으므로 표 형태 창에서 데이터를 표시할 수 없습니다.  
  
 해당 요소가 public 속성을 노출하는 경우 다음 구조체에 바인딩할 수 있습니다.  
  
-   구현 하는 모든 구성 요소는 <xref:System.Collections.IList> 인터페이스입니다. 여기에는&1;차원 배열이 포함됩니다.  
  
-   구현 하는 모든 구성 요소는 <xref:System.ComponentModel.IListSource> 인터페이스입니다.  
  
-   구현 하는 모든 구성 요소는 <xref:System.ComponentModel.IBindingList> 인터페이스입니다.  
  
 가능한 데이터 원본에 대 한 자세한 내용은 참조 [Windows Forms에서 지 원하는 데이터 소스](../../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md)합니다.  
  
## <a name="grid-display"></a>표 형태 창 표시  
 일반적인 용도 <xref:System.Windows.Forms.DataGrid> 컨트롤의 데이터 집합의 단일 테이블을 표시 하는 것입니다. 그러나 컨트롤을 사용하여 관련 테이블을 비롯한 여러 테이블을 표시할 수도 있습니다. 표 형태 창의 표시는 데이터 소스에 따라 자동으로 조정됩니다. 다음 표에서는 다양한 구성에 대해 표시되는 내용을 보여 줍니다.  
  
|데이터 집합의 내용|표시되는 내용|  
|--------------------------|-----------------------|  
|단일 테이블.|테이블이 표 형태 창에 표시됩니다.|  
|여러 테이블.|사용자가 표시할 테이블을 찾기 위해 탐색할 수 있는 트리 뷰가 표 형태 창에 표시될 수 있습니다.|  
|관련된 여러 테이블.|테이블을 선택하는 데 사용할 트리 뷰가 표 형태 창에 표시되거나, 부모 테이블이 표 형태 창에 표시되도록 지정할 수 있습니다. 사용자는 부모 테이블의 레코드를 통해 관련된 자식 행을 탐색할 수 있습니다.|  
  
> [!NOTE]
>  사용 하 여 데이터 집합의 테이블은 관련 된 <xref:System.Data.DataRelation>합니다.  또한 참조 [HYPERLINK "http://msdn.microsoft.com/library/dbwcse3d (v = vs.110)" 관계 집합의 데이터](http://msdn.microsoft.com/library/dbwcse3d\(v=vs.110\)) 또는 [데이터 집합의 관계](http://msdn.microsoft.com/library/dbwcse3d\(v=vs.120\))합니다.  
  
 때는 <xref:System.Windows.Forms.DataGrid> 컨트롤에서 테이블을 표시 및 <xref:System.Windows.Forms.DataGrid.AllowSorting%2A> 속성이 `true`, 열 머리글을 클릭 하 여 데이터를 다시 정렬할 수 있습니다. 사용자가 행을 추가하고 셀을 편집할 수도 있습니다.  
  
 테이블 집합 간의 관계는 탐색의 부모/자식 구조를 사용하여 사용자에게 표시됩니다. 부모 테이블은 가장 높은 데이터 수준이고, 자식 테이블은 부모 테이블의 개별 목록에서 파생된 데이터 테이블입니다. 자식 테이블을 포함하는 각 부모 행에 확장기가 표시됩니다. 확장기를 클릭하면 자식 테이블에 대한 웹 형식의 링크 목록이 생성됩니다. 사용자가 링크를 선택하면 자식 테이블이 표시됩니다. 부모 행 표시/숨기기 아이콘을 클릭 하면 (![부모 행 표시/숨기기 아이콘](../../../../docs/framework/winforms/controls/media/vbicon.png "vbIcon")) 부모 테이블에 대 한 정보를 숨기 거 나 경우 사용자가 이전에 숨긴 다시 표시 됩니다. 사용자는 뒤로 단추를 클릭하여 이전에 표시된 테이블로 다시 이동할 수 있습니다.  
  
## <a name="columns-and-rows"></a>열과 행  
 <xref:System.Windows.Forms.DataGrid> 의 컬렉션 <xref:System.Windows.Forms.DataGridTableStyle> 에 포함 된 개체는 <xref:System.Windows.Forms.DataGrid> 컨트롤의 <xref:System.Windows.Forms.DataGrid.TableStyles%2A> 속성입니다. 테이블 스타일의 컬렉션을 포함할 수 있습니다 <xref:System.Windows.Forms.DataGridColumnStyle> 에 포함 된 개체는 <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> 의 속성은 <xref:System.Windows.Forms.DataGridTableStyle>... 편집할 수는 <xref:System.Windows.Forms.DataGrid.TableStyles%2A> 및 <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> 속성을 통해 액세스 한 컬렉션 편집기를 사용 하 여는 **속성** 창입니다.  
  
 모든 <xref:System.Windows.Forms.DataGridTableStyle> 연관는 <xref:System.Windows.Forms.DataGrid> 컨트롤을 통해 액세스할 수는 <xref:System.Windows.Forms.GridTableStylesCollection>합니다. <xref:System.Windows.Forms.GridTableStylesCollection> 사용 하 여 디자이너에서 편집할 수는 <xref:System.Windows.Forms.DataGridTableStyle> 컬렉션 편집기를 통해 프로그래밍 방식으로 또는 <xref:System.Windows.Forms.DataGrid> 컨트롤의 <xref:System.Windows.Forms.DataGrid.TableStyles%2A> 속성입니다.  
  
 ![DataGrid 컨트롤에 포함 된 개체](../../../../docs/framework/winforms/controls/media/vbcolumns1.png "vbColumns1")  
다음 그림에서는 DataGrid 컨트롤에 포함된 개체를 보여 줍니다.  
  
 테이블 스타일과 열 스타일와 동기화 됩니다 <xref:System.Data.DataTable> 개체 및 <xref:System.Data.DataColumn> 설정 하 여 개체의 `MappingName` 속성을 적절 한 <xref:System.Data.DataTable.TableName%2A> 및 <xref:System.Data.DataColumn.ColumnName%2A> 속성입니다. 때는 <xref:System.Windows.Forms.DataGridTableStyle> 없는 열 스타일에 추가 되는 <xref:System.Windows.Forms.DataGrid> 유효한 데이터 소스에 바인딩된 컨트롤 및 <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> 테이블 스타일의 속성을 유효한 <xref:System.Data.DataTable.TableName%2A> 속성, 컬렉션을 <xref:System.Windows.Forms.DataGridColumnStyle> 해당 테이블 스타일에 대 한 개체 생성 됩니다. 각 <xref:System.Data.DataColumn> 에서 찾을 수는 <xref:System.Data.DataTable.Columns%2A> 의 컬렉션은 <xref:System.Data.DataTable>, 해당 <xref:System.Windows.Forms.DataGridColumnStyle> 에 추가 되는 <xref:System.Windows.Forms.GridColumnStylesCollection>합니다. <xref:System.Windows.Forms.GridColumnStylesCollection> 을 통해 액세스는 <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> 의 속성은 <xref:System.Windows.Forms.DataGridTableStyle>합니다. 열을 추가 하거나 사용 하 여 눈금에서 삭제 될 수는 <xref:System.Windows.Forms.GridColumnStylesCollection.Add%2A> 또는 <xref:System.Windows.Forms.GridColumnStylesCollection.Remove%2A> 메서드는 <xref:System.Windows.Forms.GridColumnStylesCollection>합니다. 자세한 내용은 참조 [하는 방법: Windows Forms DataGrid 컨트롤에 추가 하는 테이블 및 열](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md) 및 [하는 방법: Windows Forms DataGrid 컨트롤에서 열 숨기기 또는 삭제](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)합니다.  
  
 열 형식 컬렉션을 확장 하 고 <xref:System.Windows.Forms.DataGridColumnStyle> 서식 지정 및 편집 기능을 사용 하 여 클래스입니다. 모든 열 형식에서 상속 된 <xref:System.Windows.Forms.DataGridColumnStyle> 기본 클래스입니다. 만든 클래스에 따라 달라 집니다는 <xref:System.Data.DataColumn.DataType%2A> 속성은 <xref:System.Data.DataColumn> 입니다는 <xref:System.Web.UI.WebControls.DataGridColumn> 기반 합니다. 예를 들어는 <xref:System.Data.DataColumn> 있는 해당 <xref:System.Data.DataColumn.DataType%2A> 속성으로 설정 <xref:System.Boolean> 연관 될는 <xref:System.Windows.Forms.DataGridBoolColumn>합니다. 다음 표에서는 이러한 열 형식을 각각 설명합니다.  
  
|열 유형|설명|  
|-----------------|-----------------|  
|<xref:System.Windows.Forms.DataGridTextBoxColumn>|데이터를 받아서 형식이 지정된 문자열이나 형식이 지정되지 않은 문자열로 표시합니다. 편집 기능이 동일 간단한의 데이터 편집은 <xref:System.Windows.Forms.TextBox>합니다. 상속 <xref:System.Windows.Forms.DataGridColumnStyle>합니다.|  
|<xref:System.Windows.Forms.DataGridBoolColumn>|`true`, `false` 및 null 값을 받아서 표시합니다. 상속 <xref:System.Windows.Forms.DataGridColumnStyle>합니다.|  
  
 열 오른쪽 가장자리를 두 번 클릭하면 열 크기가 조정되어 전체 캡션과 가장 넓은 항목을 표시합니다.  
  
## <a name="table-styles-and-column-styles"></a>테이블 스타일과 열 스타일  
 기본 형식을 설정 하는 즉시는 <xref:System.Windows.Forms.DataGrid> 컨트롤을 사용자 지정할 수 있습니다 색을 특정 테이블이 데이터 표에 표시 될 때 사용 됩니다.  
  
 인스턴스를 만들어 이렇게는 <xref:System.Windows.Forms.DataGridTableStyle> 클래스입니다. 테이블 스타일의 기본 형식과 별도로 특정 테이블의 서식을 지정할는 <xref:System.Windows.Forms.DataGrid> 자체를 제어 합니다. 각 테이블에 대해 한 번에 하나의 테이블 스타일만 정의될 수 있습니다.  
  
 경우에 따라 특정 열을 특정 데이터 테이블의 나머지 열과 다르게 표시할 수 있습니다. 사용 하 여 열 스타일의 사용자 지정된 집합을 만들 수는 <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> 속성입니다.  
  
 테이블 스타일이 데이터 테이블과 관련이 있는 것처럼 열 스타일은 데이터 집합의 열과 관련이 있습니다. 각 테이블에 대해 한 번에 하나의 테이블 스타일만 정의될 수 있는 것처럼 특정 테이블 스타일에서 각 열에 대해 하나의 열 스타일만 정의될 수 있습니다. 이 관계는 열에 정의 된 <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> 속성입니다.  
  
 열 스타일을 추가하지 않고 테이블 스타일을 만든 경우 런타임에 폼과 표 형식 창이 생성될 때 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서 기본 열 스타일을 추가합니다. 그러나 테이블 스타일을 만들고 열 스타일을 추가한 경우에는 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서 열 스타일을 만들지 않습니다. 또한 열 스타일을 정의하고 표 형태 창에 표시할 열을 포함하는 매핑 이름으로 할당해야 합니다.  
  
 열 스타일을 할당하여 데이터 표에 포함할 열을 지정하며 열 스타일이 열에 할당되지 않았기 때문에 표 형태 창에 표시되지 않는 데이터 열을 데이터 집합에 포함할 수 있습니다. 그러나 데이터 열이 데이터 집합에 포함되었기 때문에 표시되지 않는 데이터를 프로그래밍 방식으로 편집할 수 있습니다.  
  
> [!NOTE]
>  일반적으로 테이블 스타일 컬렉션에 테이블 스타일을 추가하기 전에 열 스타일을 만들고 열 스타일 컬렉션에 추가합니다. 컬렉션에 빈 테이블 스타일을 추가하는 경우 열 스타일이 자동으로 생성됩니다. 중복 된 새 열 스타일을 추가 하려고 하면 예외가 throw 될 따라서 <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> 열 스타일 컬렉션에는 값입니다.  
>   
>  많은 열 중에서 하나의 열만 조정하려는 경우도 있습니다. 예를 들어 데이터 집합은 50개의 열을 포함하지만 이 중에서 49개만 조정하려고 합니다. 이 경우 50개 열을 모두 가져오고 프로그래밍 방식으로 하나를 제거하는 것이 원하는 49개의 개별 열을 프로그래밍 방식으로 각각 추가하는 것보다 더 쉽습니다.  
  
## <a name="formatting"></a>서식 지정  
 에 적용할 수 있는 형식 지정에 <xref:System.Windows.Forms.DataGrid> 컨트롤의 테두리 스타일, 모눈선 스타일, 글꼴, 캡션 속성, 데이터 맞춤 및 교대로 반복 되는 행의 배경색이 포함 됩니다. 자세한 내용은 참조 [하는 방법: Windows Forms DataGrid 컨트롤 서식 지정](../../../../docs/framework/winforms/controls/how-to-format-the-windows-forms-datagrid-control.md)합니다.  
  
## <a name="events"></a>이벤트  
 컨트롤 외에도 공용 이벤트와 같은 <xref:System.Windows.Forms.Control.MouseDown>, <xref:System.Windows.Forms.Control.Enter>, 및 <xref:System.Windows.Forms.DataGrid.Scroll>, <xref:System.Windows.Forms.DataGrid> 편집 및 탐색 모눈 내에서 관련 된 이벤트를 지원 합니다. <xref:System.Windows.Forms.DataGrid.CurrentCell%2A> 속성은 선택 된 셀을 결정 합니다. <xref:System.Windows.Forms.DataGrid.CurrentCellChanged> 이벤트는 사용자가 새로운 셀으로 이동 하면 발생 합니다. 사용자가 부모/자식 관계를 통해 새 테이블로 이동 하는 경우는 <xref:System.Windows.Forms.DataGrid.Navigate> 이벤트가 발생 합니다. <xref:System.Windows.Forms.DataGrid.BackButtonClick> 이벤트는 사용자가 자식 테이블을 볼 때 뒤로 단추를 클릭할 때 발생 하며 <xref:System.Windows.Forms.DataGrid.ShowParentDetailsButtonClick> 이벤트는 부모 행 표시/숨기기 아이콘을 클릭할 때 발생 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [DataGrid 컨트롤](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)   
 [방법: 데이터 소스에 Windows Forms DataGrid 컨트롤 바인딩](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)   
 [방법: 테이블 및 추가 열을 Windows Forms DataGrid 컨트롤](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)   
 [방법: 열 삭제 또는 숨기기 windows에서 Forms DataGrid 컨트롤](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)   
 [방법: Windows Forms DataGrid 컨트롤 서식 지정](../../../../docs/framework/winforms/controls/how-to-format-the-windows-forms-datagrid-control.md)