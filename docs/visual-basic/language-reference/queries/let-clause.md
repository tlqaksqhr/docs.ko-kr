---
title: "Let 절(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.QueryLet
helpviewer_keywords:
- queries [Visual Basic], Let
- Let clause [Visual Basic]
- Let statement [Visual Basic]
ms.assetid: 981aa516-16eb-4c53-b1f1-5aa3e82f316e
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 70e47517a62f58dcababd31c26277417b62eab66
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="let-clause-visual-basic"></a>Let 절(Visual Basic)
값을 계산 하 고 쿼리 내에서 새 변수를 할당 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Let variable = expression [, ...]  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`variable`|필수 요소. 지정된 된 식의 결과를 사용할 수 있는 별칭입니다.|  
|`expression`|필수 요소. 평가 되 고 지정 된 변수에 할당 되는 식입니다.|  
  
## <a name="remarks"></a>설명  
 `Let` 절을 사용 하면 계산 값 각각에 대 한 쿼리 결과 및 별칭을 사용 하 여 엔터티를 참조할 수 있습니다. 다른 절에서와 같은 별칭을 사용할 수는 `Where` 절. `Let` 절을 사용 하면 더 쉽게 읽을 쿼리에 포함 된 식 절에 별칭을 지정 하는 별칭 식 절을 사용할 때마다 대체할 수 있기 때문에 쿼리 문을 만들 수 있습니다.  
  
 개수에 관계 없이 포함할 수 있습니다 `variable` 및 `expression` 에 할당 된 `Let` 절. 쉼표 (,)로 각 할당을 구분 합니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 `Let` 절 10% 할인 제품을 계산 합니다.  
  
 [!code-vb[VbSimpleQuerySamples#16](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/let-clause_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic의 LINQ 소개](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [쿼리](../../../visual-basic/language-reference/queries/queries.md)  
 [Select 절](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From 절](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Where 절](../../../visual-basic/language-reference/queries/where-clause.md)
