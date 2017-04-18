---
title: "방법: Windows Forms DataGrid 컨트롤에 테이블과 열 추가 | Microsoft Docs"
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
  - "열[Windows Forms], DataGrid 컨트롤에 추가"
  - "DataGrid 컨트롤[Windows Forms], 테이블 및 열 추가"
  - "테이블[Windows Forms], DataGrid 컨트롤에 추가"
ms.assetid: 2fe661b9-aa06-49b9-a314-a0d3cbfdcb4d
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: Windows Forms DataGrid 컨트롤에 테이블과 열 추가
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다.  자세한 내용은 [Windows Forms DataGridView 컨트롤과 DataGrid 컨트롤의 차이점](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.  
  
 **DataGridTableStyle** 개체를 만든 다음 <xref:System.Windows.Forms.DataGrid> 컨트롤의 **TableStyles** 속성을 통해 액세스할 수 있는 **GridTableStylesCollection** 개체에 추가하여 테이블과 열에 Windows Form <xref:System.Windows.Forms.DataGrid> 컨트롤의 데이터를 표시할 수 있습니다.  각 테이블 스타일은 **DataGridTableStyle** 개체의 **MappingName** 속성에 지정된 데이터 테이블의 내용을 표시합니다.  기본적으로 열 스타일이 지정되지 않은 테이블 스타일은 해당 데이터 테이블 안에 있는 모든 열을 표시합니다.  각 **DataGridTableStyle** 개체의 **GridColumnStyles** 속성을 통해 액세스할 수 있는 **GridColumnStylesCollection** 개체에 **DataGridColumnStyle** 개체를 추가하여 테이블의 어떤 열을 표시할 것인지 제한할 수 있습니다.  
  
### 프로그래밍 방식으로 테이블 및 열을 DataGrid에 추가하려면  
  
1.  테이블의 데이터를 표시하려면 먼저 <xref:System.Windows.Forms.DataGrid> 컨트롤을 데이터 집합에 바인딩해야 합니다.  자세한 내용은 [방법: 데이터 소스에 Windows Forms DataGrid 컨트롤 바인딩](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)을 참조하십시오.  
  
    > [!CAUTION]
    >  열 스타일을 프로그래밍 방식으로 지정할 때는 항상 **DataGridTableStyle** 개체를 **GridTableStylesCollection** 개체에 추가하기 전에 **DataGridColumnStyle** 개체를 만들어 **GridColumnStylesCollection** 개체에 추가하십시오.  빈 **DataGridTableStyle** 개체를 컬렉션에 추가하면 **DataGridColumnStyle** 개체가 자동으로 생성됩니다.  그 결과 중복된 **MappingName** 값을 가진 새 **DataGridColumnStyle** 개체를 **GridColumnStylesCollection** 개체에 추가하려고 하면 예외가 throw됩니다.  
  
2.  새 테이블 스타일을 선언하고 해당 매핑 이름을 설정합니다.  
  
    ```vb  
    Dim ts1 As New DataGridTableStyle()  
    ts1.MappingName = "Customers"  
  
    ```  
  
    ```csharp  
    DataGridTableStyle ts1 = new DataGridTableStyle();  
    ts1.MappingName = "Customers";  
  
    ```  
  
    ```cpp  
    DataGridTableStyle* ts1 = new DataGridTableStyle();  
    ts1->MappingName = S"Customers";  
    ```  
  
3.  새 열 스타일을 선언하고 해당 매핑 이름과 기타 속성을 설정합니다.  
  
    ```vb  
    Dim myDataCol As New DataGridBoolColumn()  
    myDataCol.HeaderText = "My New Column"  
    myDataCol.MappingName = "Current"  
  
    ```  
  
    ```csharp  
    DataGridBoolColumn myDataCol = new DataGridBoolColumn();  
    myDataCol.HeaderText = "My New Column";  
    myDataCol.MappingName = "Current";  
  
    ```  
  
    ```cpp  
    DataGridBoolColumn^ myDataCol = gcnew DataGridBoolColumn();  
    myDataCol->HeaderText = "My New Column";  
    myDataCol->MappingName = "Current";  
    ```  
  
4.  **GridColumnStylesCollection** 개체의 **Add** 메서드를 호출하여 열을 테이블 스타일에 추가합니다.  
  
    ```vb  
    ts1.GridColumnStyles.Add(myDataCol)  
  
    ```  
  
    ```csharp  
    ts1.GridColumnStyles.Add(myDataCol);  
  
    ```  
  
    ```cpp  
    ts1->GridColumnStyles->Add(myDataCol);  
    ```  
  
5.  **GridTableStylesCollection** 개체의 **Add** 메서드를 호출하여 테이블 스타일을 데이터 표에 추가합니다.  
  
    ```vb  
    DataGrid1.TableStyles.Add(ts1)  
  
    ```  
  
    ```csharp  
    dataGrid1.TableStyles.Add(ts1);  
  
    ```  
  
    ```cpp  
    dataGrid1->TableStyles->Add(ts1);  
    ```  
  
## 참고 항목  
 [DataGrid 컨트롤](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)   
 [방법: Windows Forms DataGrid 컨트롤에서 열 삭제 또는 숨기기](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)