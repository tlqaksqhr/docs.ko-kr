---
title: "DataTables | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 52ff0e32-3e5a-41de-9a3b-7b04ea52b83e
caps.latest.revision: 6
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# DataTables
<xref:System.Data.DataSet>은 테이블 컬렉션, 관계 및 제약 조건으로 구성되어 있습니다.  ADO.NET에서 <xref:System.Data.DataTable> 개체는 **DataSet**의 테이블을 표시하는 데 사용됩니다.  **DataTable**은 메모리 내 관계형 데이터가 포함된 테이블입니다. 데이터는 .NET 기반 응용 프로그램에 로컬로 상주하지만 Microsoft SQL Server와 같은 데이터 소스에서 **DataAdapter**를 사용하여 이 테이블을 채울 수 있습니다. 자세한 내용은 [DataAdapter에서 데이터 집합 채우기](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)를 참조하세요.  
  
 .NET Framework 클래스 라이브러리 내에서 **DataTable** 클래스는 **System.Data** 네임스페이스의 멤버입니다.  사용자는 **DataTable**을 **DataSet**의 멤버로 또는 독립적으로 만들어 사용할 수 있으며, <xref:System.Data.DataView> 등의 다른 .NET Framework 개체와 함께 **DataTable** 개체를 사용할 수 있습니다.  **DataSet** 개체의 **Tables** 속성을 통해 **DataSet**의 테이블 컬렉션에 액세스합니다.  
  
 테이블의 스키마나 구조는 열이나 제약 조건에 의해 표시됩니다.  **DataTable**의 스키마는 <xref:System.Data.DataColumn> 개체를 비롯하여 <xref:System.Data.ForeignKeyConstraint> 및 <xref:System.Data.UniqueConstraint> 개체를 사용하여 정의합니다.  테이블 열은 데이터 소스 열에 매핑될 수 있습니다. 또한 이 열은 식에서 계산된 값을 포함하며 값을 자동으로 증가시키고 기본 키 값을 포함할 수 있습니다.  
  
 **DataTable**에는 스키마 이외에도 데이터를 포함하고 정렬하는 데 사용되는 행이 들어 있습니다.  <xref:System.Data.DataRow> 클래스는 테이블에 포함된 실제 데이터를 나타냅니다.  **DataRow**와 해당 속성 및 메서드를 사용하여 테이블의 데이터를 검색, 평가 및 조작할 수 있습니다.  특정 행에 포함되어 있는 데이터에 액세스하여 이 데이터를 변경하는 동안 **DataRow** 개체는 해당 행의 현재 상태와 원래 상태를 모두 유지합니다.  
  
 테이블에서 하나 이상의 관련 열을 사용하면 테이블 간에 부모\-자식 관계를 만들 수 있습니다.  <xref:System.Data.DataRelation>은 **DataTable** 개체 간의 관계를 만드는 데 사용됩니다.  그런 다음 **DataRelation** 개체를 사용하여 특정 행과 관련된 부모 또는 자식 행을 반환합니다.  자세한 내용은 [DataRelations 추가](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md)을 참조하세요.  
  
## 단원 내용  
 [DataTable 만들기](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datatable.md)  
 **DataTable**을 만들어 **DataSet**에 추가하는 방법에 대해 설명합니다.  
  
 [DataTable 스키마 정의](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 **DataColumn** 개체 및 제약 조건을 만들고 사용하는 방법에 대해 설명합니다.  
  
 [DataTable에서 데이터 조작](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 테이블에서 데이터를 추가, 수정 및 삭제하는 방법에 대해 설명합니다.  변경된 테이블 데이터를 검사하기 위해 **DataTable** 이벤트를 사용하는 방법에 대해 설명합니다.  
  
 [DataTable 이벤트 처리](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)  
 열 값을 수정하거나 행을 추가 또는 삭제하는 경우의 이벤트를 포함하여 **DataTable**과 함께 사용할 수 있는 이벤트와 관련된 정보를 제공합니다.  
  
## 관련 단원  
 [ADO.NET](../../../../../docs/framework/data/adonet/index.md)  
 ADO.NET 아키텍처 및 구성 요소에 대해 설명하고, 이를 사용하여 기존 데이터 소스에 액세스하고 응용 프로그램 데이터를 관리하는 방법을 설명합니다.  
  
 [DataSets, DataTables 및 DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 테이블 간의 관계를 만드는 방법을 포함하여 ADO.NET **DataSet**에 대한 정보를 제공합니다.  
  
 [Constraint Class](frlrfSystemDataConstraintClassTopic)  
 **Constraint** 개체와 관련된 참조 정보를 제공합니다.  
  
 [DataColumn 클래스](frlrfSystemDataDataColumnClassTopic)  
 **DataColumn** 개체와 관련된 참조 정보를 제공합니다.  
  
 [DataSet 클래스](frlrfSystemDataDataSetClassTopic)  
 **DataSet** 개체와 관련된 참조 정보를 제공합니다.  
  
 [DataTable 클래스](frlrfSystemDataDataTableClassTopic)  
 **DataTable** 개체와 관련된 참조 정보를 제공합니다.  
  
 [클래스 라이브러리 개요](../../../../../docs/standard/class-library-overview.md)  
 **System** 네임스페이스를 포함하는 .NET Framework 클래스 라이브러리뿐만 아니라 이 라이브러리의 2차 네임스페이스인 **System.Data**에 대해 간략하게 설명합니다.  
  
## 참고 항목  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)