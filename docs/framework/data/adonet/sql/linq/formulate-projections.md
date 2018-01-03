---
title: "프로젝션 작성"
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
ms.assetid: 745742df-0eda-479b-83f8-29bd8a80db96
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: bb22ddd4882d9885c55301a6fdc6a0eb336b49af
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="formulate-projections"></a>프로젝션 작성
다음 예제에서는 C#의 `select` 문과 `Select`의 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 문을 다른 기능과 함께 사용하여 쿼리 투영을 만드는 방법을 보여 줍니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 `Select`의 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 절(C#의 `select` 절)을 사용하여 `Customers`에 대한 연락처 이름의 시퀀스를 반환합니다.  
  
 [!code-csharp[DLinqQueryExamples#57](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#57)]
 [!code-vb[DLinqQueryExamples#57](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#57)]  
  
## <a name="example"></a>예  
 다음 예제에서는 `Select` 절에 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` 절에 C#) 및 *익명 형식* 및 전화 번호에 대 한 연락처 이름의 시퀀스를 반환 하려면 `Customers`합니다.  
  
 [!code-csharp[DLinqQueryExamples#58](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#58)]
 [!code-vb[DLinqQueryExamples#58](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#58)]  
  
## <a name="example"></a>예  
 다음 예제에서는 `Select` 절 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` 절에 C#) 및 *익명 형식* 이름의 시퀀스를 반환 하 고 직원에 대 한 전화 번호를 합니다. 결과 시퀀스에서 `FirstName`과 `LastName` 필드는 단일 필드(`Name`)로 결합되고 `HomePhone` 필드는 `Phone`으로 이름이 변경됩니다.  
  
 [!code-csharp[DLinqQueryExamples#59](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#59)]
 [!code-vb[DLinqQueryExamples#59](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#59)]  
  
## <a name="example"></a>예  
 다음 예제에서는 `Select` 절 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` 절에 C#) 및 *익명 형식* 모든 시퀀스를 반환 `ProductID`s 및 라는 계산 된 값을 `HalfPrice`합니다. 이 값은 2로 나누어진 `UnitPrice`로 설정됩니다.  
  
 [!code-csharp[DLinqQueryExamples#60](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#60)]
 [!code-vb[DLinqQueryExamples#60](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#60)]  
  
## <a name="example"></a>예  
 다음 예제에서는 `Select` 절 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` 절에 C#)와 *조건문* 제품 이름과 제품 사용 가능성의 시퀀스를 반환 합니다.  
  
 [!code-csharp[DLinqQueryExamples#61](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#61)]
 [!code-vb[DLinqQueryExamples#61](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#61)]  
  
## <a name="example"></a>예  
 다음 예제에서는 한 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] `Select` 절 (`select` 절에 C#) 및 *알려진 형식의* (이름)의 직원 이름의 시퀀스를 반환 합니다.  
  
 [!code-csharp[DLinqQueryExamples#62](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#62)]
 [!code-vb[DLinqQueryExamples#62](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#62)]  
  
## <a name="example"></a>예  
 다음 예제에서는 `Select` 및 `Where` 에 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` 및 `where` C#) 반환 하는 *필터링 된 시퀀스* 런던에 살고 있는 고객에 대 한 연락처 이름의 합니다.  
  
 [!code-csharp[DLinqQueryExamples#63](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#63)]
 [!code-vb[DLinqQueryExamples#63](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#63)]  
  
## <a name="example"></a>예  
 다음 예제에서는 `Select` 절에 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` 절에 C#) 및 *익명 형식* 반환 하는 *생성 된 하위 집합* 고객에 대 한 데이터입니다.  
  
 [!code-csharp[DLinqQueryExamples#64](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#64)]
 [!code-vb[DLinqQueryExamples#64](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#64)]  
  
## <a name="example"></a>예  
 다음 예제에서는 중첩된 쿼리를 사용하여 다음 결과를 반환합니다.  
  
-   모든 주문의 시퀀스와 해당 `OrderID`입니다.  
  
-   할인이 있는 주문 항목에 대한 시퀀스입니다.  
  
-   운송 비용이 포함되지 않은 총 금액입니다.  
  
 [!code-csharp[DLinqQueryExamples#65](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#65)]
 [!code-vb[DLinqQueryExamples#65](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#65)]  
  
## <a name="see-also"></a>참고 항목  
 [쿼리 예제](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
