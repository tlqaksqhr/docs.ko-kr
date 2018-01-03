---
title: "제네릭 목록으로 시퀀스 변환"
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
ms.assetid: 7ab76d93-6898-4e75-b76f-290a66ecead8
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 4b1fa6895e015ab7123bf454aac435812e4a23da
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="convert-a-sequence-to-a-generic-list"></a>제네릭 목록으로 시퀀스 변환
<xref:System.Linq.Enumerable.ToList%2A>를 사용하여 시퀀스에서 제네릭 목록을 만듭니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 <xref:System.Linq.Enumerable.ToList%2A>를 사용하여 제네릭 <xref:System.Collections.Generic.List%601>에 대한 쿼리를 즉시 평가합니다.  
  
 [!code-csharp[DLinqQueryExamples#45](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#45)]
 [!code-vb[DLinqQueryExamples#45](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#45)]  
  
## <a name="see-also"></a>참고 항목  
 [쿼리 예제](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
