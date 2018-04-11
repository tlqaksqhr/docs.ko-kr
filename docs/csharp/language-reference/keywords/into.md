---
title: into(C# 참조)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- into_CSharpKeyword
- into
helpviewer_keywords:
- into keyword [C#]
ms.assetid: 81ec62c1-f0b1-4755-8a31-959876e77f65
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7f2400143e66c68942cdec3ebfa04cfdd8cfe983
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="into-c-reference"></a>into(C# 참조)
`into` 상황별 키워드를 사용하여 [group](../../../csharp/language-reference/keywords/group-clause.md), [join](../../../csharp/language-reference/keywords/join-clause.md), [select](../../../csharp/language-reference/keywords/select-clause.md) 절의 결과를 새 식별자에 저장하기 위한 임시 식별자를 만들 수 있습니다. 이 식별자 자체는 추가 쿼리 명령의 생성기일 수 있습니다. `group` 또는 `select` 절에 사용할 경우 새 식별자의 사용을 *연속*이라고도 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `into` 키워드를 사용하여 임시 식별자 `fruitGroup`을 활성화하는 방법을 보여 줍니다. 이 식별자는 `IGrouping`의 유추된 형식을 갖습니다. 식별자를 사용하여 각 그룹에서 <xref:System.Linq.Enumerable.Count%2A> 메서드를 호출하고 둘 이상의 단어를 포함하는 그룹만 선택할 수 있습니다.  
  
 [!code-csharp[cscsrefQueryKeywords#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/into_1.cs)]  
  
 각 그룹에서 추가 쿼리 작업을 수행하려는 경우에만 `group` 절에 `into`를 사용하면 됩니다. 자세한 내용은 [group 절](../../../csharp/language-reference/keywords/group-clause.md)을 참조하세요.  
  
 `join` 절에 `into`를 사용하는 방법의 예는 [join 절](../../../csharp/language-reference/keywords/join-clause.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [쿼리 키워드(LINQ)](../../../csharp/language-reference/keywords/query-keywords.md)  
 [LINQ 쿼리 식](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [group 절](../../../csharp/language-reference/keywords/group-clause.md)
