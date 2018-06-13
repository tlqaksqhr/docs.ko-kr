---
title: 단독으로 저장 프로시저를 사용하여 작업 사용자 지정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 441e8ef3-998c-4d12-8825-ce66a178f90f
ms.openlocfilehash: 3c60a9e430b4228117fd03a43a30f27342154b1b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33357516"
---
# <a name="customizing-operations-by-using-stored-procedures-exclusively"></a>단독으로 저장 프로시저를 사용하여 작업 사용자 지정
저장 프로시저만을 사용한 데이터 액세스는 일반적인 시나리오입니다.  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 제공 되는 예제를 수정할 수 있습니다 [사용자 지정 작업에서 사용 하 여 저장 프로시저](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md) (함 동적 SQL에서 실행) 첫 번째 쿼리도 저장된 프로시저를 래핑하는 메서드 호출으로 대체 하 여 합니다.  
  
 다음 예제와 같이 `CustomersByCity`는 메서드로 가정합니다.  
  
### <a name="code"></a>코드  
 [!code-csharp[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#4)]
 [!code-vb[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#4)]  
  
 다음 코드는 동적 SQL 없이 실행됩니다.  
  
 [!code-csharp[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/Program.cs#5)]
 [!code-vb[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>참고 항목  
 [기본 동작 재정의에서 개발자의 책임](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)
