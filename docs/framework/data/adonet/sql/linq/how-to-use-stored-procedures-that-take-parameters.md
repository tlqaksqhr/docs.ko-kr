---
title: "방법: 매개 변수를 사용하는 저장 프로시저 사용"
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
ms.assetid: b935fd84-cb9c-4205-8c48-658d5db2ec93
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 28f389d7128283501291bc3220cfde3815cc0713
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-stored-procedures-that-take-parameters"></a>방법: 매개 변수를 사용하는 저장 프로시저 사용
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 출력 매개 변수를 참조 매개 변수에 매핑하고 값 형식에 대해 매개 변수를 nullable로 선언합니다.  
  
 행 집합을 반환 하는 쿼리에 입력된 매개 변수를 사용 하는 방법의 예제를 보려면 [하는 방법: 행 집합 반환](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md)합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 단일 입력 매개 변수(고객 ID)를 사용하여 출력 매개 변수(해당 고객의 총 판매액)를 반환합니다.  
  
```  
CREATE PROCEDURE [dbo].[CustOrderTotal]   
@CustomerID nchar(5),  
@TotalSales money OUTPUT  
AS  
SELECT @TotalSales = SUM(OD.UNITPRICE*(1-OD.DISCOUNT) * OD.QUANTITY)  
FROM ORDERS O, "ORDER DETAILS" OD  
where O.CUSTOMERID = @CustomerID AND O.ORDERID = OD.ORDERID  
```  
  
 [!code-csharp[DLinqSprox#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#2)]
 [!code-vb[DLinqSprox#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#2)]  
  
## <a name="example"></a>예  
 이 저장 프로시저는 다음과 같이 호출할 수 있습니다.  
  
 [!code-csharp[DLinqSprox#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#3)]
 [!code-vb[DLinqSprox#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>참고 항목  
 [저장 프로시저](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)  
 [샘플 데이터베이스 다운로드](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [Nullable 형식 사용](~/docs/csharp/programming-guide/nullable-types/using-nullable-types.md)  
 [Nullable 값 형식](~/docs/visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
