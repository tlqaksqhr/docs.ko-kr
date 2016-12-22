---
title: "방법: 쿼리 결과 그룹화(C# 프로그래밍 가이드) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "group 절 예제[C#의 LINQ]"
  - "그룹[C#의 LINQ]"
  - "쿼리[C#의 LINQ], 그룹화"
  - "쿼리 식[C#의 LINQ], 그룹화"
ms.assetid: ee981053-3392-4245-a8c2-b3730211da0d
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 방법: 쿼리 결과 그룹화(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

그룹화는 [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)]의 가장 강력한 기능 중 하나입니다.  다음 예제에서는 다양한 방식으로 데이터를 그룹화하는 방법을 보여 줍니다.  
  
-   단일 속성 사용  
  
-   문자열 속성의 첫 글자 사용  
  
-   계산된 숫자 범위 사용  
  
-   부울 조건자 또는 기타 식 사용  
  
-   복합 키 사용  
  
 또한 마지막 두 개의 쿼리는 학생의 이름과 성만 포함한 새 익명 형식으로 해당 결과를 반환합니다.  자세한 내용은 [group 절](../../../csharp/language-reference/keywords/group-clause.md)을 참조하십시오.  
  
## 예제  
 이 항목의 모든 예제에서는 다음 도우미 클래스와 데이터 소스가 사용됩니다.  
  
 [!code-cs[csProgGuideLINQ#15](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-group-query-results_1.cs)]  
  
## 예제  
 다음 예제에서는 요소의 단일 속성을 그룹 키로 사용하여 소스 요소를 그룹화하는 방법을 보여 줍니다.  이 경우 키는 학생의 성 `string`입니다.  또한 부분 문자열을 키에 사용할 수도 있습니다.  그룹화 작업은 형식에 대해 기본 같음 비교자를 사용합니다.  
  
 다음 메서드를 `StudentClass` 클래스에 붙여 넣습니다.  `Main` 메서드의 호출 문을 `sc.GroupBySingleProperty()`로 변경합니다.  
  
 [!code-cs[csProgGuideLINQ#17](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-group-query-results_2.cs)]  
  
## 예제  
 다음 예제에서는 개체의 속성이 아닌 항목을 그룹 키에 사용하여 소스 요소를 그룹화하는 방법을 보여 줍니다.  이 예제에서 키는 학생의 성 중에서 첫 번째 문자입니다.  
  
 다음 메서드를 `StudentClass` 클래스에 붙여 넣습니다.  `Main` 메서드의 호출 문을 `sc.GroupBySubstring()`로 변경합니다.  
  
 [!code-cs[csProgGuideLINQ#18](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-group-query-results_3.cs)]  
  
## 예제  
 다음 예제에서는 숫자 범위를 그룹 키로 사용하여 소스 요소를 그룹화하는 방법을 보여 줍니다.  쿼리는 이름 및 성과 학생이 속한 백분위수 범위만 포함한 익명 형식으로 결과를 반환합니다.  결과를 표시하기 위해 완전한 `Student` 개체를 사용할 필요가 없으므로 익명 형식이 사용됩니다.  `GetPercentile`은 학생의 평균 점수에 기초하여 백분위수를 계산하는 도우미 함수입니다.  이 메서드는 0에서 10 사이의 정수를 반환합니다.  
  
 [!code-cs[csProgGuideLINQ#50](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-group-query-results_4.cs)]  
  
 다음 메서드를 `StudentClass` 클래스에 붙여 넣습니다.  `Main` 메서드의 호출 문을 `sc.GroupByRange()`로 변경합니다.  
  
 [!code-cs[csProgGuideLINQ#19](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-group-query-results_5.cs)]  
  
## 예제  
 다음 예제에서는 부울 비교 식을 사용하여 소스 요소를 그룹화하는 방법을 보여 줍니다.  이 예제에서 부울 식은 학생의 평균 시험 점수가 75점을 넘는지 확인합니다.  위의 예제와 같이 완전한 소스 요소가 필요하지 않으므로 결과는 익명 형식으로 반환됩니다.  익명 형식의 속성은 `Key` 멤버의 속성이 되고 쿼리 실행 시에 이름으로 액세스할 수 있습니다.  
  
 다음 메서드를 `StudentClass` 클래스에 붙여 넣습니다.  `Main` 메서드의 호출 문을 `sc.GroupByBoolean()`로 변경합니다.  
  
 [!code-cs[csProgGuideLINQ#20](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-group-query-results_6.cs)]  
  
## 예제  
 다음 예제에서는 익명 형식을 사용하여 여러 값이 포함된 키를 캡슐화하는 방법을 보여 줍니다.  이 예제에서 첫 번째 키 값은 학생의 성 중에서 첫 번째 문자입니다.  두 번째 키 값은 학생이 첫 번째 시험에서 85점이 넘는 점수를 받았는지 여부를 지정하는 부울입니다.  키의 임의 속성으로 그룹을 정렬할 수 있습니다.  
  
 다음 메서드를 `StudentClass` 클래스에 붙여 넣습니다.  `Main` 메서드의 호출 문을 `sc.GroupByCompositeKey()`로 변경합니다.  
  
 [!code-cs[csProgGuideLINQ#21](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-group-query-results_7.cs)]  
  
## 코드 컴파일  
 테스트하려는 각 메서드를 복사하여 `StudentClass` 클래스에 붙여 넣습니다.  메서드에 대한 호출 문을 `Main` 메서드에 추가하고 F5 키를 누릅니다.  
  
 사용자 고유의 응용 프로그램에 이러한 메서드를 적용하는 경우 LINQ에서는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 버전 3.5 또는 4를 필요로 하며 프로젝트에는 System.Core.dll에 대한 참조와 System.Linq에 대한 using 지시문이 포함되어야 합니다.  LINQ to SQL, LINQ to XML 및 LINQ to DataSet 형식에는 using 지시문 및 참조가 추가로 필요합니다.  자세한 내용은 [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Linq.Enumerable.GroupBy%2A>   
 <xref:System.Linq.IGrouping%602>   
 [LINQ 쿼리 식](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [group 절](../../../csharp/language-reference/keywords/group-clause.md)   
 [익명 형식](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [방법: 그룹화 작업에서 하위 쿼리 수행](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-a-subquery-on-a-grouping-operation.md)   
 [방법: 중첩 그룹 만들기](../Topic/How%20to:%20Create%20a%20Nested%20Group%20\(C%23%20Programming%20Guide\).md)   
 [Grouping Data](../../../visual-basic/programming-guide/concepts/linq/grouping-data.md)