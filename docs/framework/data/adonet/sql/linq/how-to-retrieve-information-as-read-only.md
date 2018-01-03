---
title: "방법: 읽기 전용으로 정보 검색"
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
ms.assetid: fb09e298-0b53-47e5-97fb-ab318bcd4fad
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 04a20a06cd8ed8785b37bdc604a817b475f93873
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-retrieve-information-as-read-only"></a>방법: 읽기 전용으로 정보 검색
데이터를 변경하지 않으려면 읽기 전용 결과를 검색하여 쿼리의 성능을 향상시킬 수 있습니다.  
  
 <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A>를 `false`로 설정하여 읽기 전용 처리를 구현합니다.  
  
> [!NOTE]
>  <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A>를 `false`로 설정한 경우 <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A>는 암시적으로 `false`로 설정됩니다.  
  
## <a name="example"></a>예  
 다음 코드에서는 직원 고용 날짜의 읽기 전용 컬렉션을 검색합니다.  
  
 [!code-csharp[DLinqQuerying#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#2)]
 [!code-vb[DLinqQuerying#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#2)]  
  
## <a name="see-also"></a>참고 항목  
 [쿼리 개념](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 [데이터베이스 쿼리](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)  
 [지연된 로드 및 즉시 로드 비교](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md)
