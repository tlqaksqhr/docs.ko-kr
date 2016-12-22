---
title: "Group By 절(Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.QueryGroupByInto"
  - "vb.QueryGroupBy"
  - "vb.QueryGroupRef"
  - "vb.QueryGroupInto"
  - "vb.QueryGroup"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "쿼리[Visual Basic], Group By"
  - "Group By 문"
  - "Group By 절"
ms.assetid: b1b5dcea-6654-473b-a2db-01f7e4c265d7
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Group By 절(Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

쿼리 결과의 요소를 그룹화합니다. 각 그룹에 집계 함수를 적용하는 데 사용할 수도 있습니다. 그룹화 작업은 하나 이상의 키를 기반으로 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Group [ listField1 [, listField2 [...] ] By keyExp1 [, keyExp2 [...] ]  
  Into aggregateList  
```  
  
## <a name="parts"></a>요소  
  
-   `listField1`, `listField2`  
  
     선택 사항입니다. 그룹화된 결과에 포함할 필드를 명시적으로 식별하는 쿼리 변수의 하나 이상 필드입니다. 필드를 지정하지 않으면 쿼리 변수의 모든 필드가 그룹화된 결과에 포함됩니다.  
  
-   `keyExp1`  
  
     필수 요소. 요소 그룹을 결정하는 데 사용할 키를 식별하는 식입니다. 둘 이상의 키를 지정하여 복합 키를 지정할 수 있습니다.  
  
-   `keyExp2`  
  
     선택 사항입니다. 복합 키를 만들기 위해 `keyExp1` 와 결합되는 하나 이상의 추가 키입니다.  
  
-   `aggregateList`  
  
     필수 요소. 그룹의 집계 방법을 식별하는 하나 이상의 식입니다. 그룹화된 결과의 멤버 이름을 식별하려면 다음 형식 중 하나일 수 있는 `Group` 키워드를 사용합니다.  
  
    ```  
    Into Group  
    ```  
  
     또는  
  
    ```  
    Into <alias> = Group  
    ```  
  
     그룹에 적용할 집계 함수를 포함할 수도 있습니다.  
  
## <a name="remarks"></a>설명  
 `Group By` 절을 사용하여 쿼리 결과를 그룹으로 나눌 수 있습니다. 그룹화는 키 또는 여러 키로 구성된 복합 키를 기반으로 합니다. 일치하는 키 값과 연결된 요소는 동일한 그룹에 포함됩니다.  
  
 `aggregateList` 절의 `Into` 매개 변수와 `Group` 키워드를 사용하여 그룹을 참조하는 데 사용되는 멤버 이름을 식별합니다. `Into` 절에 집계 함수를 포함하여 그룹화된 요소의 값을 계산할 수도 있습니다. 표준 집계 함수 목록은 [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 해당 위치(국가)를 기준으로 고객 목록을 그룹화하고 각 그룹에 있는 고객 수를 제공합니다. 결과는 국가 이름별로 정렬됩니다. 그룹화된 결과는 도시 이름별로 정렬됩니다.  
  
 [!code-vb[VbSimpleQuerySamples#11](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/group-by-clause_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic의 LINQ 소개](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [쿼리](../../../visual-basic/language-reference/queries/queries.md)   
 [Select 절](../../../visual-basic/language-reference/queries/select-clause.md)   
 [From 절](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Order By 절](../../../visual-basic/language-reference/queries/order-by-clause.md)   
 [Aggregate 절](../../../visual-basic/language-reference/queries/aggregate-clause.md)   
 [Group Join 절](../../../visual-basic/language-reference/queries/group-join-clause.md)