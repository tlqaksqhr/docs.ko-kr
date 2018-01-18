---
title: "ADO.NET 데이터 집합"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 82b641bb-6001-4512-bf1a-2830acdd92ab
caps.latest.revision: "6"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: b9d566f99802ea80ae73132579bb3068b1ff3b28
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="adonet-datasets"></a>ADO.NET 데이터 집합
<xref:System.Data.DataSet> 개체는 연결되지 않은 분산 데이터 시나리오를 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]을 사용하여 지원하는 데 핵심적인 역할을 수행합니다. **DataSet** 데이터 소스에 관계 없이 일관성 있는 관계형 프로그래밍 모델을 제공 하는 데이터의 메모리 상주 표현입니다. 이 개체는 다양한 여러 데이터 소스에 사용하거나 XML 데이터에 사용할 수 있을 뿐 아니라 이 개체를 사용하여 응용 프로그램의 로컬 데이터를 관리할 수도 있습니다. **DataSet** 관련된 테이블, 제약 조건 및 테이블 간의 관계를 포함 하 여 데이터의 전체 집합을 나타냅니다. 다음 그림에서는 **DataSet** 개체 모델입니다.  
  
 ![ADO.Net graphic](../../../../docs/framework/data/adonet/media/ado-1-bpuedev11.png "ado_1_bpuedev11")  
DataSet 개체 모델  
  
 메서드 및 개체에는 **DataSet** 관계형 데이터베이스 모델에서와 일치 합니다.  
  
 **DataSet** 유지 될 수 있으며 해당 내용을 XML로 및 XML 스키마 정의 언어 (XSD) 스키마로 스키마를 다시 로드 합니다. 자세한 내용은 [데이터 집합에서 XML 사용](../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)을 참조하세요.  
  
## <a name="the-datatablecollection"></a>DataTableCollection  
 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] **DataSet** 의해 표현 되는 0 개 이상의 테이블의 컬렉션을 포함 <xref:System.Data.DataTable> 개체입니다. <xref:System.Data.DataTableCollection> 모든 포함 된 **DataTable** 개체에 **데이터 집합**합니다.  
  
 A **DataTable** 에 정의 된는 <xref:System.Data> 네임 스페이스 및 메모리 상주 데이터의 단일 테이블을 나타냅니다. 여기에는 <xref:System.Data.DataColumnCollection>에 의해 표현되는 열의 컬렉션과 <xref:System.Data.ConstraintCollection>에 의해 표현되는 제약 조건의 컬렉션이 포함됩니다. 이 두 컬렉션은 테이블의 스키마를 정의합니다. A **DataTable** 으로 표현 되는 행의 컬렉션도 포함는 <xref:System.Data.DataRowCollection>, 테이블의 데이터가 들어 있습니다. 이와 함께 <xref:System.Data.DataRow>는 현재 버전과 원래 버전을 모두 보유하므로 행에 저장된 값에 대한 변경 사항을 식별할 수 있습니다.  
  
## <a name="the-dataview-class"></a>DataView 클래스  
 <xref:System.Data.DataView>는 데이터 바인딩 응용 프로그램에서 자주 사용되는 기능으로, 이 기능을 사용하면 <xref:System.Data.DataTable>에 저장되어 있는 데이터에 대해 서로 다른 뷰를 만들 수 있습니다. <xref:System.Data.DataView>를 사용하면 테이블의 데이터를 여러 정렬 순서로 노출시킬 수 있으며 행 상태에 따라 또는 필터 식을 기준으로 데이터를 필터링할 수 있습니다. 자세한 내용은 참조 [데이터 보기](../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)합니다.  
  
## <a name="the-datarelationcollection"></a>DataRelationCollection  
 A **DataSet** 의 관계가 포함 해당 <xref:System.Data.DataRelationCollection> 개체입니다. 가 나타내는 관계는 <xref:System.Data.DataRelation> associates 행에 대 한 개체 **DataTable** 다른 행과 함께 **DataTable**합니다. 이 관계는 관계형 데이터베이스의 기본 키 열과 외래 키 열 간에 존재하는 조인 경로와 유사합니다. A **DataRelation** 의 두 테이블에 일치 하는 열을 식별 하는 **DataSet**합니다.  
  
 관계를 사용 하면 한 테이블에서 다른 탐색은 **DataSet**합니다. 필수 요소는 **DataRelation** 관계의 이름, 관련 되는 테이블의 이름 및 각 테이블의 관련된 열입니다. <xref:System.Data.DataColumn> 개체의 배열을 키 열로 지정하면 테이블당 두 개 이상의 열에 대한 관계를 빌드할 수 있습니다. 에 대 한 관계를 추가 하는 경우는 <xref:System.Data.DataRelationCollection>, 선택적으로 추가할 수는 **UniqueKeyConstraint** 및 **ForeignKeyConstraint** 관련된 열이 변경 될 때 무결성 제약 조건을 적용 하려면 값입니다.  
  
 자세한 내용은 참조 [Datarelation 추가](../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md)합니다.  
  
## <a name="xml"></a>XML  
 채울 수 있습니다는 **DataSet** XML 스트림이나 문서에서 합니다. 에 제공 하 여 XML 스트림 또는 문서를 사용할 수 있습니다는 **DataSet** 데이터, 스키마 정보 또는 둘 다 합니다. 기존 데이터 나 스키마 정보에 이미 있는 XML 스트림이나 문서에서 제공 되는 정보를 함께 사용할 수는 **DataSet**합니다. 자세한 내용은 [데이터 집합에서 XML 사용](../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)을 참조하세요.  
  
## <a name="extendedproperties"></a>ExtendedProperties  
 **DataSet**, **DataTable**, 및 **DataColumn** 모두는 **ExtendedProperties** 속성입니다. **ExtendedProperties** 는 **PropertyCollection** 결과 집합을 생성 하는 데 사용한 SELECT 문이나 데이터가 생성 된 시간 같은 사용자 지정 정보를 배치할 수 있습니다. **ExtendedProperties** 컬렉션에 대 한 스키마 정보로 유지 되는 **DataSet**합니다.  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]에서는 데이터 집합에 저장되어 있는 연결되지 않은 데이터에 대한 통합 언어 쿼리 기능을 제공합니다. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]표준 사용 하 여 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] 구문을 사용 하는 경우 컴파일 타임 구문 검사, 정적 입력 및 IntelliSense 지원을 제공 하 고는 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] IDE.  
  
 자세한 내용은 [LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [ADO.NET 개요](../../../../docs/framework/data/adonet/ado-net-overview.md)  
 [DataSet, DataTable 및 DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET에서 데이터 검색 및 수정](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
