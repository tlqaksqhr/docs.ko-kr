---
title: "데이터 바인딩 및 LINQ to DataSet"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 310bff4a-32dd-4f20-a271-6dbd82912631
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: b3b097f9bca790d1f19da9d75f834c6277507d8d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="data-binding-and-linq-to-dataset"></a>데이터 바인딩 및 LINQ to DataSet
*데이터 바인딩* 응용 프로그램 UI와 비즈니스 논리 사이의 연결을 설정 하는 프로세스입니다. 바인딩 설정이 올바르고 데이터가 적절한 알림을 제공하는 경우 데이터 값이 변경될 때 데이터에 바인딩된 요소에 변경 사항이 자동으로 반영됩니다. <xref:System.Data.DataSet>은 포함된 데이터 소스에 관계없이 일관성 있는 관계형 프로그래밍 모델을 제공하는 데이터의 메모리 내 표현입니다. ADO.NET 2.0 <xref:System.Data.DataView>는 <xref:System.Data.DataTable>에 저장된 데이터를 정렬하고 필터링하는 데 사용됩니다. 이 기능은 데이터 바인딩 응용 프로그램에서 자주 사용됩니다. <xref:System.Data.DataView>를 사용하여 테이블의 데이터를 여러 정렬 순서로 노출시킬 수 있으며, 행 상태에 따라 또는 필터 식을 기준으로 데이터를 필터링할 수 있습니다. 에 대 한 자세한 내용은 <xref:System.Data.DataView> 개체, 참조 [데이터 보기](../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)합니다.  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]개발자가 복잡 하 고 강력한 쿼리를 통해 만들 수 있습니다는 <xref:System.Data.DataSet> 를 사용 하 여 [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)]합니다. 그러나 한 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 의 열거형을 반환 하는 쿼리 <xref:System.Data.DataRow> 쉽게 바인딩 시나리오에서 사용 되지 않는 개체입니다. 바인딩 보다 쉽게 만들 수 있습니다는 <xref:System.Data.DataView> 에서 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 쿼리 합니다. 이 <xref:System.Data.DataView> 필터링과 정렬을 쿼리에 지정 된 사용 하지만 데이터 바인딩에 더 적합 한 합니다. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]기능을 확장 된 <xref:System.Data.DataView> 제공 하 여 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] 식 기반 필터링 및 정렬을 허용 하는 훨씬 더 복잡 하 고 강력한 필터링 및 정렬 문자열 기반 필터링 및 정렬 작업에 대 한 합니다.  
  
 <xref:System.Data.DataView>는 쿼리의 상위에 있는 뷰가 아니라 쿼리 자체를 나타냅니다. <xref:System.Data.DataView>는 간단한 데이터 바인딩 모델을 제공하는 <xref:System.Windows.Forms.DataGrid> 또는 <xref:System.Windows.Forms.DataGridView>와 같은 UI 컨트롤에 바인딩됩니다. <xref:System.Data.DataView>는 해당 테이블의 기본 뷰를 제공하는 <xref:System.Data.DataTable>에서도 만들 수 있습니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [DataView 개체 만들기](../../../../docs/framework/data/adonet/creating-a-dataview-object-linq-to-dataset.md)  
 <xref:System.Data.DataView> 만들기에 대한 정보를 제공합니다.  
  
 [DataView로 필터링](../../../../docs/framework/data/adonet/filtering-with-dataview-linq-to-dataset.md)  
 <xref:System.Data.DataView>로 필터링하는 방법을 설명합니다.  
  
 [DataView로 정렬](../../../../docs/framework/data/adonet/sorting-with-dataview-linq-to-dataset.md)  
 <xref:System.Data.DataView>로 정렬하는 방법을 설명합니다.  
  
 [DataView에서 DataRowView 컬렉션 쿼리](../../../../docs/framework/data/adonet/querying-the-datarowview-collection-in-a-dataview.md)  
 <xref:System.Data.DataRowView>로 노출된 <xref:System.Data.DataView> 컬렉션을 쿼리하는 방법에 대한 정보를 제공합니다.  
  
 [DataView 성능](../../../../docs/framework/data/adonet/dataview-performance.md)  
 <xref:System.Data.DataView>와 성능에 대한 정보를 제공합니다.  
  
 [방법: Windows Forms DataGridView 컨트롤에 DataView 개체 바인딩](../../../../docs/framework/data/adonet/how-to-bind-a-dataview-object-to-a-winforms-datagridview-control.md)  
 <xref:System.Data.DataView> 개체를 <xref:System.Windows.Forms.DataGridView>에 바인딩하는 방법을 설명합니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로그래밍 가이드](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)
