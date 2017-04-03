---
title: "쿼리 식의 Null 값 처리"
description: "쿼리 식의 Null 값을 처리하는 방법입니다."
keywords: .NET, .NET Core, C#
author: stevehoag
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: ac63ae8b-724d-4251-9334-528f4e884ae7
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 14b64bf8d3590f4f7dc3d1b00cb50d0bc421d9bc
ms.lasthandoff: 03/13/2017

---
# <a name="handle-null-values-in-query-expressions"></a>쿼리 식의 Null 값 처리

이 예제에서는 소스 컬렉션에서 가능한 null 값을 처리하는 방법을 보여 줍니다. <xref:System.Collections.Generic.IEnumerable%601> 등의 개체 컬렉션에는 값이 [null](../language-reference/keywords/null.md)인 요소가 포함될 수 있습니다. 소스 컬렉션이 null이거나 값이 null인 요소를 포함하고 사용 중인 쿼리가 null 값을 처리하지 않는 경우 쿼리를 실행하면 <xref:System.NullReferenceException>이 throw됩니다.  
  
## <a name="example"></a>예제

 다음 예제와 같이 null 참조 예외를 피하도록 방어적으로 코딩할 수 있습니다.  
  
 [!code-cs[csProgGuideLINQ#82](../../../samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_1.cs)]  
  
 이전 예제에서 `where` 절은 범주 시퀀스에서 모든 null 요소를 필터링합니다. 이 방법은 join 절의 null 확인과 관계가 없습니다. `Products.CategoryID`가 `Nullable<int>`의 축약형인 `int?` 형식이므로 이 예제에서는 null이 있는 조건식이 적용됩니다.  
  
## <a name="example"></a>예제

 join 절에서 비교 키 중 하나만 nullable 값 형식인 경우에는 쿼리 식에서 다른 키를 nullable 형식으로 캐스트할 수 있습니다. 다음 예제에서는 `EmployeeID`가 `int?` 형식의 값이 포함된 열이라고 가정합니다.  
  
 [!code-cs[csProgGuideLINQ#83](../../../samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_2.cs)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Nullable%601>   
 [LINQ 쿼리 식](index.md)   
 [Nullable 형식](../programming-guide/nullable-types/index.md)
