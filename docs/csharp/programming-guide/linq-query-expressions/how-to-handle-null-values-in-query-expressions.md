---
redirect_url: /dotnet/articles/csharp/linq/handle-null-values-in-query-expressions
caps.handback.revision: 6
---
# 방법: 쿼리 식의 Null 값 처리(C# 프로그래밍 가이드)
이 예제에서는 소스 컬렉션에 포함될 수 있는 null 값의 처리 방법을 보여 줍니다.  <xref:System.Collections.Generic.IEnumerable%601>과 같은 개체 컬렉션에는 값이 [null](../../../csharp/language-reference/keywords/null.md)인 요소가 포함될 수 있습니다.  소스 컬렉션이 null이거나 값이 null인 요소가 소스 컬렉션에 들어 있고 쿼리에서 null 값을 처리하지 않는 경우, 쿼리를 실행하면 <xref:System.NullReferenceException>이 throw됩니다.  
  
## 예제  
 다음 예제와 같이 null 참조 예외가 발생하지 않도록 코드를 작성할 수 있습니다.  
  
 [!code-cs[csProgGuideLINQ#82](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-handle-null-values-in-query-expressions_1.cs)]  
  
 위의 예제에서 `where` 절은 범주 시퀀스에서 null 요소를 모두 필터링하여 제외합니다.  이 기술은 조인 절의 null 검사 기능과는 관계없습니다.  이 예제에서 null을 사용하는 조건 식은 `Products.CategoryID`가 `int?` 형식\(`Nullable<int>`의 축약형\)이기 때문에 제대로 작동합니다.  
  
## 예제  
 조인 절에서 비교 키 중 하나만 nullable 값 형식인 경우에는 쿼리 식에서 다른 키를 nullable 형식으로 캐스팅할 수 있습니다.  다음 예제에서는 `EmployeeID` 열에 `int?` 형식의 값이 들어 있다고 가정합니다.  
  
 [!code-cs[csProgGuideLINQ#83](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-handle-null-values-in-query-expressions_2.cs)]  
  
## 참고 항목  
 <xref:System.Nullable%601>   
 [LINQ 쿼리 식](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [nullable 형식](../../../csharp/programming-guide/nullable-types/index.md)