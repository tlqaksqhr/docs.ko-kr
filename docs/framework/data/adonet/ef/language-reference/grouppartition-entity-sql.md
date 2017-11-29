---
title: GROUPPARTITION(Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d0482e9b-086c-451c-9dfa-ccb024a9efb6
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: ceadd193784a2c1936b0dcc2d634ae87b513e57e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="grouppartition-entity-sql"></a>GROUPPARTITION(Entity SQL)
집계가 관련된 현재 그룹 파티션에서 예측된 인수 값의 컬렉션을 반환합니다. `GroupPartition` 집계는 그룹 기반 집계이며 컬렉션 기반 형식을 포함하지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```  
GROUPPARTITION( [ALL|DISTINCT] expression )  
```  
  
## <a name="arguments"></a>인수  
 `expression`  
 임의의 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 식입니다.  
  
## <a name="remarks"></a>설명  
 다음 쿼리는 제품 목록 및 각 제품당 주문 라인 수량 컬렉션을 만듭니다.  
  
```  
select p, GroupPartition(ol.Quantity) from LOB.OrderLines as ol  
  group by ol.Product as p  
```  
  
 다음 두 쿼리는 구문적으로 서로 동일합니다.  
  
```  
select p, Sum(GroupPartition(ol.Quantity)) from LOB.OrderLines as ol  
  group by ol.Product as p  
select p, Sum(ol.Quantity) from LOB.OrderLines as ol  
  group by ol.Product as p  
```  
  
 `GROUPPARTITION` 연산자는 사용자 정의 집계 연산자와 함께 사용할 수 있습니다.  
  
 `GROUPPARTITION` 은 그룹화된 입력 집합에 대한 참조를 포함하는 특수 집계 연산자입니다. 이러한 참조는 범위 내에 GROUP BY가 있는 쿼리의 아무 곳에서나 사용할 수 있습니다. 예를 들면 다음과 같습니다.  
  
```  
select p, GroupPartition(ol.Quantity) from LOB.OrderLines as ol group by ol.Product as p  
```  
  
 일반 GROUP BY를 사용하는 경우 그룹화 결과는 숨겨집니다. 결과는 집계 함수에서만 사용할 수 있습니다. 그룹화 결과를 보려면 하위 쿼리를 사용하여 그룹화 및 입력 집합 결과를 상호 연결해야 합니다. 다음 두 쿼리는 동일한 의미를 갖습니다.  
  
```  
select p, (select q from GroupPartition(ol.Quantity) as q) from LOB.OrderLines as ol group by ol.Product as p  
select p, (select ol.Quantity as q from LOB.OrderLines as ol2 where ol2.Product = p) from LOB.OrderLines as ol group by ol.Product as p  
```  
  
 예제와 나와 있듯이 GROUPPARTITION 집계 연산자를 사용하면 그룹화 이후 입력 집합에 대한 참조를 보다 쉽게 가져올 수 있습니다.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 매개 변수를 사용하는 경우 GROUPPARTITION 연산자는 연산자 입력에서 `expression` 식을 지정할 수 있습니다.  
  
 예를 들어, 그룹 파티션에 대한 다음의 모든 입력 식은 유효합니다.  
  
```  
select groupkey, GroupPartition(b) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition(1) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition(a + b) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition({a + b}) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition({42}) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition(b > a) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 GROUPPARTITION 절을 GROUP BY 절과 함께 사용하는 방법을 보여 줍니다. GROUP BY 절은 `SalesOrderHeader` 엔터티를 해당 `Contact`별로 그룹화합니다. 그리고 나서 GROUPPARTITION 절은 각 그룹에 대한 `TotalDue` 속성을 예상하여 10진수 컬렉션을 생성합니다.  
  
 [!code-csharp[DP EntityServices Concepts 2#Collection_GroupPartition](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#collection_grouppartition)]
