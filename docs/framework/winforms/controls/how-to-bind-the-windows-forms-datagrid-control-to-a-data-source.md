---
title: "방법: 데이터 소스에 Windows Forms DataGrid 컨트롤 바인딩"
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
- cpp
helpviewer_keywords:
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], data binding
- bound controls [Windows Forms], DataGrid control
- Windows Forms controls, data binding
- bound controls [Windows Forms]
- data-bound controls [Windows Forms], DataGrid
ms.assetid: 128cdb07-dfd3-4d60-9d6a-902847667c36
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 185c094b32f0de7a1a26da144601961d92a625b9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source"></a>방법: 데이터 소스에 Windows Forms DataGrid 컨트롤 바인딩
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다. 자세한 내용은 [Windows Forms DataGridView 및 DataGrid 컨트롤의 차이점](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.  
  
 Windows Forms <xref:System.Windows.Forms.DataGrid> 컨트롤 특별히 설계 된 데이터 원본에서 정보를 표시 합니다. 호출 하 여 런타임에 컨트롤을 바인딩하는 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 메서드. 다양 한 데이터 원본에서에서 데이터를 표시할 수 있지만 가장 일반적인 소스는 데이터 집합 및 데이터 보기.  
  
### <a name="to-data-bind-the-datagrid-control-programmatically"></a>데이터 바인딩 DataGrid 컨트롤 프로그래밍 방식으로 하려면  
  
1.  데이터 집합을 채우는 코드를 작성 합니다.  
  
     이면 데이터 원본이 데이터 집합 또는 데이터 집합 테이블을 기반으로 데이터 뷰를 폼에 데이터 집합을 채우는 코드를 추가 합니다.  
  
     사용할 올바른 코드는 데이터 집합 데이터를 가져오는 위치에 따라 달라 집니다. 일반적으로 호출 하는 데이터베이스에서 직접 데이터 집합을 채우는 경우는 `Fill` 메서드 라는 데이터 집합을 채우는 다음 예제와 같이 데이터 어댑터의 `DsCategories1`:  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
     데이터 집합, XML 웹 서비스에서 채워진 경우 일반적으로 코드에는 서비스의 인스턴스를 만들 하 고 데이터 집합을 반환 하는 방법 중 하나를 호출 합니다. 그런 다음 로컬 데이터 집합에 XML 웹 서비스에서 데이터 집합을 병합합니다. 다음 예제에서는 호출 하는 XML 웹 서비스의 인스턴스를 만드는 방법을 보여 줍니다. `CategoriesService`, 호출의 `GetCategories` 메서드를 호출 하는 로컬 데이터 집합으로 결과 데이터 집합 병합 `DsCategories1`:  
  
    ```vb  
    Dim ws As New MyProject.localhost.CategoriesService()  
    ws.Credentials = System.Net.CredentialCache.DefaultCredentials  
    DsCategories1.Merge(ws.GetCategories())  
    ```  
  
    ```csharp  
    MyProject.localhost.CategoriesService ws = new MyProject.localhost.CategoriesService();  
    ws.Credentials = System.Net.CredentialCache.DefaultCredentials;  
    DsCategories1.Merge(ws.GetCategories());  
    ```  
  
    ```cpp  
    MyProject::localhost::CategoriesService^ ws =   
       new MyProject::localhost::CategoriesService();  
    ws->Credentials = System::Net::CredentialCache::DefaultCredentials;  
    dsCategories1->Merge(ws->GetCategories());  
    ```  
  
2.  호출 된 <xref:System.Windows.Forms.DataGrid> 컨트롤의 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 메서드를 데이터 원본 및 데이터 멤버에 전달 합니다. 데이터 멤버를 명시적으로 전달 하도록 필요 하지 않은 경우 빈 문자열을 전달 합니다.  
  
    > [!NOTE]
    >  컨트롤의 눈금에 처음으로 바인딩하는 경우 설정할 수 있습니다 <xref:System.Windows.Forms.DataGrid.DataSource%2A> 및 <xref:System.Windows.Forms.DataGrid.DataMember%2A> 속성입니다. 그러나 설정 된 후 이러한 속성을 재설정할 수 없습니다. 따라서 것이 좋습니다 항상 사용 하 여 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 메서드.  
  
     다음 예제에서는 프로그래밍 방식으로 바인딩하는 방법을 라는 데이터 집합의 Customers 테이블에 `DsCustomers1`:  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "Customers");  
    ```  
  
     데이터 집합에 Customers 테이블을 사용 하는 경우 바인딩할 수도 있습니다. 표에서 이러한 방식으로:  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "");  
    ```  
  
3.  (선택 사항) 해당 테이블 스타일과 열 스타일을 표에 추가 합니다. 테이블, 테이블 스타일이 없는 경우 나타납니다 하지만 최소한의 서식으로 및 표시 하는 모든 열을 갖는 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [DataGrid 컨트롤 개요](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 [방법: Windows Forms DataGrid 컨트롤에 테이블 및 열 추가](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)  
 [DataGrid 컨트롤](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [Windows Forms 데이터 바인딩](../../../../docs/framework/winforms/windows-forms-data-binding.md)
