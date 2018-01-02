---
title: "DataReader 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 49d4422a-7464-4ab8-8ec7-90185fde3ecf
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 169f290ba41e7efe1ceb7c57f0821fdc0a886c5e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="creating-a-datareader"></a>DataReader 만들기
<xref:System.Data.DataTable> 및 <xref:System.Data.DataSet> 클래스에는 <xref:System.Data.DataTable.CreateDataReader%2A>의 내용이나 <xref:System.Data.DataTable> 개체의 <xref:System.Data.DataSet> 컬렉션 내용을 하나 이상의 정방향 읽기 전용 커서로 반환하는 <xref:System.Data.DataSet.Tables%2A> 메서드가 있습니다.  
  
## <a name="example"></a>예제  
 다음 콘솔 응용 프로그램에서는 <xref:System.Data.DataTable> 인스턴스를 만듭니다. 이 예제에서는 다음 채워진 전달 <xref:System.Data.DataTable> 를 호출 하는 프로시저는 <xref:System.Data.DataTable.CreateDataReader%2A> 메서드 내에 포함 된 결과를 반복 하는 <xref:System.Data.DataTableReader>합니다.  
  
 [!code-csharp[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/VB/source.vb#1)]  
  
 이 예제에서는 콘솔 창에 다음 출력을 표시합니다.  
  
```  
1 Mary  
2 Andy  
3 Peter  
4 Russ  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Data.DataTable.CreateDataReader%2A>  
 <xref:System.Data.DataSet.CreateDataReader%2A>  
 [DataTableReader](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
