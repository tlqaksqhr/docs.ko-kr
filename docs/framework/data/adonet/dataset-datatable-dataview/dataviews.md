---
title: "데이터 보기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0fe5dfa2-c1cd-435f-90b6-b4dd2e3ef34b
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 5b79461a6fc3314ca4178e0f9b1cff1c468cc3e6
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="dataviews"></a>데이터 보기
<xref:System.Data.DataView>는 데이터 바인딩 응용 프로그램에서 자주 사용되는 기능으로, 이 기능을 사용하면 <xref:System.Data.DataTable>에 저장되어 있는 데이터에 대해 서로 다른 뷰를 만들 수 있습니다. 사용 하는 **DataView**를 여러 정렬 순서로 테이블의 데이터를 노출할 수 있습니다 및 행 상태 또는 필터 식을 기준으로 데이터를 필터링 할 수 있습니다.  
  
 A **DataView** 제공 데이터 원본에 대 한 동적 뷰 **DataTable**: 콘텐츠, 정렬 및 구성원 나타나는 순서 대로 변경 내용을 반영 합니다. 이 동작은에서 **선택** 의 메서드는 **DataTable**, 반환 하는 <xref:System.Data.DataRow> 배열 테이블에서 특정 필터 및/또는 정렬 순서에 따라: thiscontent 변경 내용이 반영 되는 기본 테이블을 하지만 해당 멤버 및 순서 지정 정적인 상태로 유지 합니다. 동적 기능은 **DataView** 데이터 바인딩 응용 프로그램에 적합 합니다.  
  
 A **DataView** 단일 집합이 있는 여러 가지 정렬 및 필터링 기준을 적용할 수 있습니다는 데이터베이스 뷰와 매우 유사 하 게 데이터에 대 한 동적 뷰를 제공 합니다. 그러나 데이터베이스 뷰와 달리는 **DataView** 테이블로 취급 될 수 없고 및 조인 된 테이블의 뷰를 제공할 수 없습니다. 또한 소스 테이블에 있는 열을 제외하거나 계산을 통해 만들어지는 열과 같이 소스 테이블에 없는 열을 추가할 수 없습니다.  
  
 사용할 수 있습니다는 <xref:System.Data.DataView.DataViewManager%2A> 에 있는 모든 테이블에 대 한 뷰 설정을 관리할 수는 **DataSet**합니다. **DataViewManager** 각 테이블에 대 한 기본 뷰 설정을 관리할 수 있는 편리한 방법을 제공 합니다. 컨트롤의 둘 이상의 테이블을 바인딩하는 경우는 **DataSet**바인딩할는 **DataViewManager** 것이 좋습니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [DataView 만들기](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-dataview.md)  
 만드는 방법에 설명 된 **DataView** 에 대 한는 **DataTable**합니다.  
  
 [데이터 정렬 및 필터링](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)  
 속성을 설정 하는 방법에 설명 된 **DataView** 특정 정렬 순서로 데이터를 반환 하거나 특정 필터 조건에 맞는 데이터 행의 하위 집합을 반환 하도록 합니다.  
  
 [DataRow 및 DataRowView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datarows-and-datarowviews.md)  
 에 의해 노출 된 데이터에 액세스 하는 방법에 설명 된 **DataView**합니다.  
  
 [행 찾기](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md)  
 특정 행을 확인 하는 방법에 설명 된 **DataView**합니다.  
  
 [ChildView 및 관계](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/childviews-and-relations.md)  
 사용 하 여 부모-자식 관계에서 데이터의 뷰를 만드는 방법에 설명 된 **DataView**합니다.  
  
 [데이터 보기 수정](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/modifying-dataviews.md)  
 내부에서 데이터를 수정 하는 방법을 설명 **DataTable** 통해는 **DataView**, 업데이트 활성화 또는 비활성화를 포함 합니다.  
  
 [DataView 이벤트 처리](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-dataview-events.md)  
 사용 하는 방법에 설명는 **ListChanged** 이벤트 알림을 받을 때 내용 또는 순서가 **DataView** 업데이트 되 고 합니다.  
  
 [데이터 보기 관리](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/managing-dataviews.md)  
 사용 하는 방법에 설명는 **DataViewManager** 관리할 **DataView** 의 각 테이블에 대 한 설정을 **데이터 집합**합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [ASP.NET 웹 응용 프로그램](http://msdn.microsoft.com/library/a812d7b7-049e-4234-a4c2-6acf690301f6)  
 ASP.NET 응용 프로그램, Web Forms 및 Web Services를 만들기 위한 개요 및 자세한 단계별 절차를 제공합니다.  
  
 [Windows 응용 프로그램](http://msdn.microsoft.com/library/a6bb2180-09b1-4738-b9fd-7fb05fc92f23)  
 Windows Forms 및 콘솔 응용 프로그램 작업에 대한 자세한 내용을 제공합니다.  
  
 [DataSet, DataTable 및 DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 설명의 **DataSet** 개체와 사용 하 여 응용 프로그램 데이터를 관리 하는 방법을 합니다.  
  
 [DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 설명의 **DataTable** 개체와 사용 하 여 단독으로 또는의 일부로 응용 프로그램 데이터를 관리 하는 방법을 **DataSet**합니다.  
  
 [ADO.NET](../../../../../docs/framework/data/adonet/index.md)  
 ADO.NET 아키텍처 및 구성 요소에 대해 설명하고, ADO.NET을 사용하여 기존 데이터 소스에 액세스하고 응용 프로그램 데이터를 관리하는 방법을 설명합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
