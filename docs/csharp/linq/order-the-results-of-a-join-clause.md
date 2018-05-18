---
title: join 절 결과를 순서대로 정렬
description: join 절 결과를 순서대로 정렬하는 방법
ms.date: 12/1/2016
ms.assetid: a7458901-1201-4c25-b8d9-c04ca52e0eb9
ms.openlocfilehash: f426152e614ed9a9c4aa41d7ba7cb8ddf1cd3063
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="order-the-results-of-a-join-clause"></a>join 절 결과를 순서대로 정렬
이 예제에서는 조인 작업 결과를 순서대로 정렬하는 방법을 보여 줍니다. 조인 후 순서대로 정렬합니다. 조인 전에 하나 이상의 소스 시퀀스와 함께 `orderby` 절을 사용할 수도 있지만 일반적으로 권장되지는 않습니다. 일부 LINQ 공급자는 조인 후에 정렬 순서를 유지하지 않을 수도 있습니다.  
  
## <a name="example"></a>예  
 이 쿼리는 그룹 조인을 만든 후 범위 내에 있는 범주 요소에 따라 그룹을 정렬합니다. 무명 형식 이니셜라이저 내의 하위 쿼리는 제품 시퀀스에서 일치하는 모든 요소를 순서대로 정렬합니다.  
  
 [!code-csharp[csProgGuideLINQ#81](../../../samples/snippets/csharp/concepts/linq/how-to-order-the-results-of-a-join-clause_1.cs)]  
 
## <a name="see-also"></a>참고 항목  
 [LINQ 쿼리 식](index.md)  
 [orderby 절](../language-reference/keywords/orderby-clause.md)  
 [join 절](../language-reference/keywords/join-clause.md) 
