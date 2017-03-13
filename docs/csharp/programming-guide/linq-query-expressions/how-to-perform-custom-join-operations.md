---
redirect_url: /dotnet/articles/csharp/linq/perform-custom-join-operations
caps.handback.revision: 13
---
# 방법: 사용자 지정 조인 작업 수행(C# 프로그래밍 가이드)
이 예제에서는 `join` 절에서 사용할 수 없는 조인 작업을 수행하는 방법을 보여 줍니다.  쿼리 식에서 `join` 절은 가장 일반적인 조인 작업 형식인 동등 조인으로 제한되며 이에 맞게 최적화되어 있습니다.  동등 조인을 수행하는 경우 항상 `join` 절을 사용하여 최상의 성능을 얻을 수 있습니다.  
  
 하지만 다음과 같은 경우에는 `join` 절을 사용할 수 없습니다.  
  
-   다름\(비동등\) 식에서 조인을 서술하는 경우  
  
-   둘 이상의 동등 또는 비동등 식에서 조인을 서술하는 경우  
  
-   조인 작업 전에 오른쪽\(내부\) 시퀀스에 대해 임시 범위 변수를 적용해야 하는 경우  
  
 동등 조인이 아닌 조인을 수행하려면 여러 개의 `from` 절을 사용하여 각 데이터 소스를 개별적으로 적용합니다.  그런 다음 `where` 절의 조건자 식을 각 소스의 범위 변수에 적용합니다.  식이 메서드 호출 형태를 사용할 수도 있습니다.  
  
> [!NOTE]
>  이 종류의 사용자 지정 조인 작업을 여러 개의 `from` 절을 사용한 내부 컬렉션 액세스와 혼동하지 마십시오.  자세한 내용은 [join 절](../../../csharp/language-reference/keywords/join-clause.md)을 참조하십시오.  
  
## 예제  
 다음 예제의 첫 번째 메서드는 단순한 교차 조인을 보여 줍니다.  교차 조인은 매우 큰 결과 집합을 생성할 수 있으므로 주의해서 사용해야 합니다.  그러나 추가 쿼리가 실행되는 소스 시퀀스를 생성하기 위한 일부 시나리오에서 유용할 수 있습니다.  
  
 두 번째 메서드는 범주 ID가 왼쪽의 범주 목록에 나열된 모든 제품의 시퀀스를 생성합니다.  임시 배열을 만들기 위한 `let` 절과 `Contains` 메서드의 사용을 확인합니다.  또한 쿼리 전에 배열을 만들고 첫 번째 `from` 절을 제거할 수도 있습니다.  
  
 [!code-cs[csProgGuideLINQ#64](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-perform-custom-join-operations_1.cs)]  
  
## 예제  
 다음 예제에서는 쿼리가 내부\(오른쪽\) 시퀀스의 경우 조인 절 자체 전에 가져올 수 없는 일치하는 키를 기반으로 두 개의 시퀀스를 조인해야 합니다.  `join` 절을 사용하여 이 조인을 수행하면 각 요소에 대해 `Split` 메서드가 호출되어야 합니다.  여러 개의 `from` 절을 사용하면 쿼리가 반복 메서드 호출의 오버헤드를 방지할 수 있습니다.  그러나 `join`이 최적화되므로 이 특별한 경우에서는 여러 개의 `from` 절을 사용하는 것보다 속도가 더 빠를 수 있습니다.  결과는 주로 메서드 호출의 비용에 따라 달라집니다.  
  
 [!code-cs[csProgGuideLINQ#13](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-perform-custom-join-operations_2.cs)]  
  
## 코드 컴파일  
  
-   [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] 3.5 이상을 대상으로 하는 [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs-current-short-md.md)] 콘솔 응용 프로그램 프로젝트를 만듭니다.  기본적으로 프로젝트에는 System.Core.dll에 대한 참조 및 System.Linq 네임스페이스에 대한 `using` 지시문이 있습니다.  
  
-   `Program` 클래스를 이전 예제의 코드로 바꿉니다.  
  
-   [How to: Join Content from Dissimilar Files \(LINQ\)](../Topic/How%20to:%20Join%20Content%20from%20Dissimilar%20Files%20\(LINQ\).md)의 지침에 따라 scores.csv 및 names.csv 데이터 파일을 설정합니다.  
  
-   F5 키를 눌러 프로그램을 컴파일하고 실행합니다.  
  
-   아무 키나 눌러 콘솔 창을 닫습니다.  
  
## 참고 항목  
 [LINQ 쿼리 식](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [join 절](../../../csharp/language-reference/keywords/join-clause.md)   
 [Join Operations](../../../visual-basic/programming-guide/concepts/linq/join-operations.md)   
 [방법: Join 절 결과의 순서 정렬](../../../csharp/programming-guide/linq-query-expressions/how-to-order-the-results-of-a-join-clause.md)