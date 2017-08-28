---
title: "orderby 절(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- orderby
- orderby_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- orderby clause [C#]
- orderby keyword [C#]
ms.assetid: 21f87f48-d69d-4e95-9a52-6fec47b37e1f
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ec9507e4c1d9691d90d47cdbb20fdb22fc281d24
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="orderby-clause-c-reference"></a>orderby 절(C# 참조)
쿼리 식에서 `orderby` 절은 반환된 시퀀스 또는 하위 시퀀스(그룹)가 오름차순이나 내림차순으로 정렬되도록 합니다. 하나 이상의 보조 정렬 작업을 수행하기 위해 여러 키를 지정할 수 있습니다. 정렬은 요소 형식에 대한 기본 비교자에 의해 수행됩니다. 기본 정렬 순서는 오름차순입니다. 사용자 지정 비교자를 지정할 수도 있습니다. 그러나 메서드 기반 구문을 통해서만 사용할 수 있습니다. 자세한 내용은 [데이터 정렬](http://msdn.microsoft.com/library/6d76e2d7-b418-49b5-ac78-2bcd61169c48)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 예제에서 첫 번째 쿼리는 A부터 시작하여 사전순으로 단어를 정렬하고, 두 번째 쿼리는 동일한 단어를 내림차순으로 정렬합니다. `ascending` 키워드는 기본 정렬 값이며 생략할 수 있습니다.  
  
 [!code-cs[cscsrefQueryKeywords#20](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_1.cs)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 학생의 성을 기준으로 1차 정렬을 수행한 다음 이름을 기준으로 2차 정렬을 수행합니다.  
  
 [!code-cs[cscsrefQueryKeywords#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_2.cs)]  
  
## <a name="remarks"></a>설명  
 컴파일 시간에 `orderby` 절은 <xref:System.Linq.Enumerable.OrderBy%2A> 메서드 호출로 변환됩니다. `orderby` 절의 여러 키는 <xref:System.Linq.Enumerable.ThenBy%2A> 메서드 호출로 변환됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)   
 [쿼리 키워드(LINQ)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [LINQ 쿼리 식](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [group 절](../../../csharp/language-reference/keywords/group-clause.md)   
 [C#에서 LINQ 시작](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)

