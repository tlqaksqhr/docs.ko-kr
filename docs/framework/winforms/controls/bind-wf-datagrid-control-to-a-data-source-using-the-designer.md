---
title: "방법: 디자이너를 사용하여 데이터 소스에 Windows Forms DataGrid 컨트롤 바인딩 | Microsoft Docs"
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
  - "바인딩 컨트롤"
  - "바인딩 컨트롤, DataGrid 컨트롤"
  - "데이터 바인딩, DataGrid 컨트롤"
  - "데이터 바인딩 컨트롤, DataGrid"
  - "DataGrid 컨트롤[Windows Forms], 데이터 바인딩"
  - "데이터 집합[Windows Forms], DataGrid 컨트롤에 바인딩"
  - "Windows Forms 컨트롤, 데이터 바인딩"
ms.assetid: 4e96e3d0-b1cc-4de1-8774-bc9970ec4554
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: 디자이너를 사용하여 데이터 소스에 Windows Forms DataGrid 컨트롤 바인딩
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다.  자세한 내용은 [Windows Forms DataGridView 컨트롤과 DataGrid 컨트롤의 차이점](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.  
  
 Windows Forms <xref:System.Windows.Forms.DataGrid> 컨트롤은 데이터 소스의 정보를 표시하도록 특별히 디자인된 컨트롤입니다.  <xref:System.Windows.Forms.DataGrid.DataSource%2A> 및 <xref:System.Windows.Forms.DataGrid.DataMember%2A> 속성을 설정하여 디자인 타임에 이 컨트롤을 바인딩하거나 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 메서드를 호출하여 런타임에 바인딩합니다.  다양한 데이터 소스의 데이터를 표시할 수 있지만 가장 일반적인 소스는 데이터 집합과 데이터 뷰입니다.  
  
 폼에 데이터 집합이나 데이터 뷰의 인스턴스가 포함된 경우와 같이 디자인 타임에 데이터 소스를 사용할 수 있는 경우에는 디자인 타임에 데이터 표를 데이터 소스에 바인딩할 수 있습니다.  그런 다음 데이터가 데이터 표에 어떻게 나타나는지 미리 볼 수 있습니다.  
  
 또한 런타임에 프로그래밍 방식으로 데이터 표를 바인딩할 수도 있습니다.  이 방법은 런타임에 얻은 정보를 기반으로 데이터 소스를 설정하려는 경우에 유용합니다.  예를 들어, 응용 프로그램에서 사용자에게 보려는 테이블의 이름을 지정하도록 할 수 있습니다.  이 방법은 디자인 타임에 데이터 소스가 없는 경우에도 필요합니다.  여기에는 배열, 컬렉션, 형식화되지 않은 데이터 집합 및 데이터 판독기와 같은 데이터 소스가 포함됩니다.  
  
 다음 절차를 수행하려면 <xref:System.Windows.Forms.DataGrid> 컨트롤이 포함된 폼이 있는 **Windows 응용 프로그램** 프로젝트가 필요합니다.  이러한 프로젝트를 설정하는 데 대한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)를 참조하십시오.  [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)]에서는 기본적으로 <xref:System.Windows.Forms.DataGrid> 컨트롤이 **도구 상자**에 없습니다.  이 컨트롤을 추가하는 방법에 대한 자세한 내용은 [How to: Add Items to the Toolbox](http://msdn.microsoft.com/ko-kr/458e119e-17fe-450b-b889-e31c128bd7e0)를 참조하십시오.  또한 [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)]에서는 **데이터 소스** 창을 사용하여 디자인 타임 데이터 바인딩을 수행할 수 있습니다.  자세한 내용은 [Visual Studio에서 데이터에 컨트롤 바인딩](../Topic/Bind%20controls%20to%20data%20in%20Visual%20Studio.md)를 참조하십시오.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 디자이너에서 DataGrid 컨트롤을 단일 테이블에 데이터 바인딩하려면  
  
1.  컨트롤의 <xref:System.Windows.Forms.DataGrid.DataSource%2A> 속성을 바인딩할 데이터 항목을 포함하는 개체로 설정합니다.  
  
2.  데이터 소스가 데이터 집합이면 <xref:System.Windows.Forms.DataGrid.DataMember%2A> 속성을 바인딩할 테이블의 이름으로 설정합니다.  
  
3.  데이터 소스가 데이터 집합이거나 데이터 집합 테이블에 기반하는 데이터 뷰인 경우에는 데이터 집합을 채우는 코드를 폼에 추가합니다.  
  
     이때 사용할 올바른 코드는 데이터 집합이 데이터를 가져오는 위치에 따라 다릅니다.  데이터베이스에서 직접 데이터 집합을 채우는 경우에는 아래 코드 예제에서 볼 수 있는 것과 같이 일반적으로 `DsCategories1`이라는 데이터 집합을 채우는 데이터 어댑터의 `Fill` 메서드를 호출합니다.  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
4.  선택적으로, 데이터 표에 적절한 테이블 스타일과 열 스타일을 추가합니다.  
  
     테이블 스타일이 없는 상태에서 테이블을 보면 최소한의 형식이 지정된 상태로 모든 열이 표시되는 것을 볼 수 있습니다.  
  
### 디자이너에서 DataGrid 컨트롤을 데이터 집합의 여러 테이블에 데이터 바인딩하려면  
  
1.  컨트롤의 <xref:System.Windows.Forms.DataGrid.DataSource%2A> 속성을 바인딩할 데이터 항목을 포함하는 개체로 설정합니다.  
  
2.  데이터 집합에 관련 테이블\(관계 개체\)이 포함된 경우에는 <xref:System.Windows.Forms.DataGrid.DataMember%2A> 속성을 부모 테이블의 이름으로 설정합니다.  
  
3.  데이터 집합을 채우는 코드를 작성합니다.  
  
## 참고 항목  
 [DataGrid 컨트롤 개요](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)   
 [방법: Windows Forms DataGrid 컨트롤에 테이블과 열 추가](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)   
 [DataGrid 컨트롤](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)   
 [Windows Forms 데이터 바인딩](../../../../docs/framework/winforms/windows-forms-data-binding.md)   
 [Visual Studio에서 데이터 액세스](../Topic/Accessing%20data%20in%20Visual%20Studio.md)