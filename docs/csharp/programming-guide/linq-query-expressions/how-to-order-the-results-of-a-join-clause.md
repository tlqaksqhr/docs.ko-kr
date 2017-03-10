---
redirect_url: /dotnet/articles/csharp/linq/order-the-results-of-a-join-clause
caps.handback.revision: 6
---
# 방법: Join 절 결과의 순서 정렬(C# 프로그래밍 가이드)
이 예제에서는 조인 연산 결과의 순서를 정렬하는 방법을 보여 줍니다.  순서 정렬 작업은 조인 이후에 수행됩니다.  조인하기 전에 하나 이상의 소스 시퀀스에 대해 `orderby` 절을 사용할 수도 있지만 이 방법은 사용하지 않는 것이 좋습니다.  일부 [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)] 공급자에서는 조인 이후에 이 정렬 순서를 유지하지 않기 때문입니다.  
  
## 예제  
 이 쿼리는 그룹 조인을 만든 후 범위 내에 있는 category 요소를 기준으로 그룹을 정렬합니다.  익명 형식 이니셜라이저 안에서는 하위 쿼리가 제품 시퀀스에서 일치하는 모든 요소의 순서를 정렬합니다.  
  
 [!code-cs[csProgGuideLINQ#81](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csRef30LangFeatures_2.cs#81)]  
  
## 코드 컴파일  
  
-   .NET Framework 버전 3.5를 대상으로 하는 [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs-current-short-md.md)] 프로젝트를 만듭니다.  기본적으로 프로젝트에는 System.Core.dll에 대한 참조 및 System.Linq 네임스페이스에 대한 `using` 지시문이 있습니다.  
  
-   프로젝트에 코드를 복사합니다.  
  
-   F5 키를 눌러 프로그램을 컴파일하고 실행합니다.  
  
-   아무 키나 눌러 콘솔 창을 닫습니다.  
  
## 참고 항목  
 [LINQ 쿼리 식](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [orderby 절](../../../csharp/language-reference/keywords/orderby-clause.md)   
 [join 절](../../../csharp/language-reference/keywords/join-clause.md)   
 [Join Operations](../../../visual-basic/programming-guide/concepts/linq/join-operations.md)