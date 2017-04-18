---
title: "DataViews | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0fe5dfa2-c1cd-435f-90b6-b4dd2e3ef34b
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# DataViews
<xref:System.Data.DataView>는 데이터 바인딩 응용 프로그램에서 자주 사용되는 기능으로, 이 기능을 사용하면 <xref:System.Data.DataTable>에 저장되어 있는 데이터에 대해 서로 다른 뷰를 만들 수 있습니다.  **DataView**를 사용하여 테이블의 데이터를 다른 정렬 순서로 노출시킬 수 있으며, 행 상태에 따라 또는 필터 식을 기준으로 데이터를 필터링할 수 있습니다.  
  
 **DataView**에서는 원본 **DataTable**의 데이터에 대한 동적 뷰를 제공합니다. 따라서 변경이 발생할 경우 DataTable의 내용, 순서 및 멤버에 해당 변경 사항이 적용됩니다.  이 동작은 특정 필터 및\/또는 정렬 순서에 따라 테이블에서 <xref:System.Data.DataRow> 배열을 반환하는 **DataTable**의 **Select** 메서드와는 다릅니다. 이 내용은 원본으로 사용하는 테이블의 변경 사항을 적용하기는 하지만 해당 멤버 및 순서는 정적으로 유지됩니다.  **DataView**의 동적 기능은 데이터 바인딩 응용 프로그램에 사용하기에 아주 적합합니다.  
  
 **DataView**에서는 단일 데이터 집합에 대한 동적 뷰를 제공하는데 이 동적 뷰에는 데이터베이스 뷰와 매우 유사하게 여러 가지 정렬 및 필터링 기준을 적용할 수 있습니다.  그러나 데이터베이스 뷰와 달리 **DataView**는 테이블로 취급될 수 없고 조인된 테이블의 뷰도 제공할 수 없습니다.  또한 소스 테이블에 있는 열을 제외하거나 계산을 통해 만들어지는 열과 같이 소스 테이블에 없는 열을 추가할 수 없습니다.  
  
 <xref:System.Data.DataView.DataViewManager%2A>를 사용하여 **DataSet**의 모든 테이블에 대한 뷰 설정을 관리할 수 있습니다.  **DataViewManager**에서는 각 테이블에 대한 기본 뷰 설정을 관리할 수 있는 편리한 방법을 제공합니다.  컨트롤을 둘 이상의 **DataSet** 테이블에 바인딩할 때는 **DataViewManager**에 바인딩하는 것이 좋습니다.  
  
## 단원 내용  
 [DataView 만들기](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-dataview.md)  
 **DataTable**에 대한 **DataView**를 만드는 방법을 설명합니다.  
  
 [데이터 정렬 및 필터링](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)  
 특정 필터 조건에 맞는 데이터 행의 하위 집합을 반환하거나 특정 정렬 순서로 데이터를 반환하도록 **DataView**의 속성을 설정하는 방법을 설명합니다.  
  
 [DataRows 및 DataRowViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datarows-and-datarowviews.md)  
 **DataView**에 의해 노출된 데이터에 액세스하는 방법을 설명합니다.  
  
 [행 찾기](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md)  
 **DataView**에서 특정 행을 찾는 방법을 설명합니다.  
  
 [ChildViews 및 관계](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/childviews-and-relations.md)  
 **DataView**를 사용하여 부모\-자식 관계에서 데이터 뷰를 만드는 방법을 설명합니다.  
  
 [DataViews 수정](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/modifying-dataviews.md)  
 업데이트 활성화 또는 비활성화를 포함하여 **DataView**를 통해 원본 **DataTable**의 데이터를 수정하는 방법을 설명합니다.  
  
 [DataView 이벤트 처리](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-dataview-events.md)  
 **DataView**의 내용 또는 순서가 업데이트될 때 알림을 받도록 **ListChanged** 이벤트를 사용하는 방법을 설명합니다.  
  
 [DataViews 관리](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/managing-dataviews.md)  
 **DataViewManager**를 사용하여 **DataSet**의 각 테이블에 대한 **DataView** 설정을 관리하는 방법을 설명합니다.  
  
## 관련 단원  
 [ASP.NET Web Applications](http://msdn.microsoft.com/ko-kr/a812d7b7-049e-4234-a4c2-6acf690301f6)  
 ASP.NET 응용 프로그램, Web Forms 및 Web Services를 만들기 위한 개요 및 자세한 단계별 절차를 제공합니다.  
  
 [Windows Applications](http://msdn.microsoft.com/ko-kr/a6bb2180-09b1-4738-b9fd-7fb05fc92f23)  
 Windows Forms 및 콘솔 응용 프로그램 작업에 대한 자세한 내용을 제공합니다.  
  
 [DataSets, DataTables 및 DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 **DataSet** 개체에 대해 설명하고, 이 개체를 사용하여 응용 프로그램 데이터를 관리하는 방법을 설명합니다.  
  
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 **DataTable** 개체에 대해 설명하고, 이 개체를 사용하여 단독으로 또는 **DataSet**의 일부로 응용 프로그램 데이터를 관리하는 방법을 설명합니다.  
  
 [ADO.NET](../../../../../docs/framework/data/adonet/index.md)  
 ADO.NET 아키텍처 및 구성 요소에 대해 설명하고, ADO.NET을 사용하여 기존 데이터 소스에 액세스하고 응용 프로그램 데이터를 관리하는 방법을 설명합니다.  
  
## 참고 항목  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)