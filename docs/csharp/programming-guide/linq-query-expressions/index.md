---
redirect_url: /dotnet/articles/csharp/linq/index
caps.handback.revision: 21
---
# LINQ 쿼리 식(C# 프로그래밍 가이드)
[!INCLUDE[vbteclinqext](../../../csharp/getting-started/includes/vbteclinqext-md.md)]는 C\# 언어\(또한 Visual Basic 및 잠재적으로 다른 모든 .NET 언어\)에 대한 쿼리 기능의 직접 통합을 기반으로 하는 기술 집합의 이름입니다.  [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)]를 사용하면 쿼리가 클래스, 메서드, 이벤트와 같은 고급 언어 구문이 됩니다.  
  
 쿼리를 작성하는 개발자에게 가장 많이 표시되는 [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)]의 "통합 언어" 부분은 쿼리 식입니다.  쿼리 식은 C\# 3.0에서 소개된 선언적 *쿼리 구문*으로 작성됩니다.  쿼리 구문을 사용하면 최소한의 코드로 데이터 소스에 대해 복잡한 필터링, 정렬 및 그룹화 작업을 수행할 수 있습니다.  동일한 기본 쿼리 식 패턴을 사용하여 SQL 데이터베이스, [!INCLUDE[vstecado](../../../csharp/programming-guide/concepts/linq/includes/vstecado-md.md)] 데이터 집합, .XML 문서 및 스트림, .NET 컬렉션의 데이터를 쿼리하고 변환합니다.  
  
 다음 예제에서는 전체 쿼리 작업을 보여 줍니다.  전체 작업에는 데이터 소스 만들기, 쿼리 식 정의 및 `foreach` 문으로 쿼리 실행이 포함됩니다.  
  
 [!code-cs[csProgGuideLINQ#11](../../../csharp/programming-guide/arrays/codesnippet/CSharp/index_1.cs)]  
  
 C\#의 [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)] 기본 사항에 대한 자세한 내용은 [Getting Started with LINQ in C\#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)을 참조하십시오.  
  
## 쿼리 식 개요  
  
-   쿼리 식은 [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)] 사용 데이터 소스의 데이터를 쿼리 및 변환하는 데 사용할 수 있습니다.  예를 들어 단일 쿼리는 SQL 데이터베이스에서 데이터를 검색하고 XML 스트림을 출력으로 생성할 수 있습니다.  
  
-   쿼리 식은 많은 익숙한 C\# 언어 구문을 사용하므로 쉽게 익힐 수 있습니다.  자세한 내용은 [Getting Started with LINQ in C\#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)을 참조하십시오.  
  
-   컴파일러가 형식을 유추할 수 있으므로 대부분 명시적으로 형식을 제공할 필요는 없지만 쿼리 식의 변수는 모두 강력한 형식입니다.  자세한 내용은 [Type Relationships in LINQ Query Operations](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)를 참조하십시오.  
  
-   쿼리는 `foreach` 문에서 쿼리 변수를 반복할 때까지 실행되지 않습니다.  자세한 내용은 [Introduction to LINQ Queries \(C\#\)](../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)를 참조하십시오.  
  
-   컴파일 타임에 쿼리 식은 C\# 사양에 설정된 규칙에 따라 표준 쿼리 연산자 메서드로 변환됩니다.  쿼리 구문을 사용하여 표현할 수 있는 모든 쿼리는 메서드 구문으로도 표현할 수 있습니다.  그러나 대체로 쿼리 구문이 더 읽기 쉽고 간결합니다.  자세한 내용은 [C\# 언어 사양](../../../csharp/language-reference/language-specification.md) 및 [Standard Query Operators Overview](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)를 참조하십시오.  
  
-   일반적으로 [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)] 쿼리를 작성할 때는 가능한 한 쿼리 구문을 사용하고 필요한 경우에만 메서드 구문을 사용하는 것이 좋습니다.  두 형태 간에 의미 체계 또는 성능상의 차이는 없습니다.  쿼리 식이 메서드 식으로 작성된 동등한 식보다 읽기 쉽습니다.  
  
-   <xref:System.Linq.Enumerable.Count%2A> 또는 <xref:System.Linq.Enumerable.Max%2A> 같은 일부 쿼리 작업에는 동등한 쿼리 식 절이 없으므로 메서드 호출로 표현해야 합니다.  다양한 방법으로 메서드 구문과 쿼리 구문을 결합할 수 있습니다.  자세한 내용은 [Query Syntax and Method Syntax in LINQ](../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md)를 참조하십시오.  
  
-   쿼리가 적용되는 형식에 따라 쿼리 식을 식 트리나 대리자로 컴파일할 수 있습니다.  <xref:System.Collections.Generic.IEnumerable%601> 쿼리는 대리자로 컴파일되고  <xref:System.Linq.IQueryable> 및 <xref:System.Linq.IQueryable%601> 쿼리는 식 트리로 컴파일됩니다.  자세한 내용은 [식 트리](../Topic/Expression%20Trees%20\(C%23%20and%20Visual%20Basic\).md)를 참조하십시오.  
  
 다음 표에서는 일반적인 작업을 위한 쿼리 및 코드 예제에 대한 추가 정보를 제공하는 항목을 보여 줍니다.  
  
|항목|설명|  
|--------|--------|  
|[쿼리 식 기본 사항](../../../csharp/programming-guide/linq-query-expressions/query-expression-basics.md)|기본적인 쿼리 개념을 소개하고 C\# 쿼리 구문의 예제를 제공합니다.|  
|[방법: C\#에서 LINQ 쿼리 작성](../../../csharp/programming-guide/linq-query-expressions/how-to-write-linq-queries.md)|몇 가지 기본적인 쿼리 식 형식의 예제를 제공합니다.|  
|[방법: 쿼리 식의 예외 처리](../../../csharp/programming-guide/linq-query-expressions/how-to-handle-exceptions-in-query-expressions.md)|잠재적 예외 throw 코드를 쿼리 식 외부로 이동하는 방법 및 시기를 보여 줍니다.|  
|[How to: Populate Object Collections from Multiple Sources \(LINQ\)](../Topic/How%20to:%20Populate%20Object%20Collections%20from%20Multiple%20Sources%20\(LINQ\).md)|`select` 문을 사용하여 여러 소스의 데이터를 새 형식으로 병합하는 방법을 보여 줍니다.|  
|[방법: 쿼리 결과 그룹화](../../../csharp/programming-guide/linq-query-expressions/how-to-group-query-results.md)|`group` 절을 사용하는 다양한 방법을 보여 줍니다.|  
|[방법: 중첩 그룹 만들기](../../../csharp/programming-guide/linq-query-expressions/how-to-create-a-nested-group.md)|중첩 그룹을 만드는 방법을 보여 줍니다.|  
|[방법: 그룹화 작업에서 하위 쿼리 수행](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-a-subquery-on-a-grouping-operation.md)|쿼리의 하위 식을 새 쿼리의 데이터 소스로 사용하는 방법을 보여 줍니다.|  
|[방법: 연속 키를 기준으로 결과 그룹화](../../../csharp/programming-guide/linq-query-expressions/how-to-group-results-by-contiguous-keys.md)|스트리밍 데이터 소스에 대한 그룹화 작업을 수행할 수 있는 스레드로부터 안전한 표준 쿼리 연산자를 구현하는 방법을 보여 줍니다.|  
|[방법: 런타임에 동적으로 조건자 필터 지정](../../../csharp/programming-guide/linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md)|동등 비교에 사용할 임의 개수의 값을 `where` 절에 제공하는 방법을 보여 줍니다.|  
|[방법: 쿼리 결과를 메모리에 저장](../../../csharp/programming-guide/linq-query-expressions/how-to-store-the-results-of-a-query-in-memory.md)|`foreach` 루프를 사용하지 않고도 쿼리 결과를 구체화하고 저장하는 방법을 보여 줍니다.|  
|[방법: 메서드에서 쿼리 반환](../../../csharp/programming-guide/linq-query-expressions/how-to-return-a-query-from-a-method.md)|메서드에서 쿼리 변수를 반환하는 방법 및 이러한 변수를 입력 매개 변수로 메서드에 전달하는 방법을 보여 줍니다.|  
|[방법: 사용자 지정 조인 작업 수행](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-custom-join-operations.md)|조건자 함수 종류를 기반으로 조인 작업을 수행하는 방법을 보여 줍니다.|  
|[방법: 복합 키를 사용하여 조인](../../../csharp/programming-guide/linq-query-expressions/how-to-join-by-using-composite-keys.md)|둘 이상의 일치하는 키를 기반으로 두 개의 소스를 조인하는 방법을 보여 줍니다.|  
|[방법: Join 절 결과의 순서 정렬](../../../csharp/programming-guide/linq-query-expressions/how-to-order-the-results-of-a-join-clause.md)|조인 작업으로 생성된 시퀀스를 정렬하는 방법을 보여 줍니다.|  
|[방법: 내부 조인 수행](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-inner-joins.md)|[!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)]에서 내부 조인을 수행하는 방법을 보여 줍니다.|  
|[방법: 그룹화 조인 수행](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-grouped-joins.md)|[!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)]에서 그룹화된 조인을 생성하는 방법을 보여 줍니다.|  
|[방법: 왼쪽 우선 외부 조인 수행](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-left-outer-joins.md)|[!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)]에서 왼쪽 우선 외부 조인을 생성하는 방법을 보여 줍니다.|  
|[방법: 쿼리 식의 Null 값 처리](../../../csharp/programming-guide/linq-query-expressions/how-to-handle-null-values-in-query-expressions.md)|[!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)] 쿼리에서 null 값을 처리하는 방법을 보여 줍니다.|  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [Walkthrough: Writing Queries in C\#](../../../csharp/programming-guide/concepts/linq/walkthrough-writing-queries-linq.md)   
 [Basic LINQ Query Operations](../../../csharp/programming-guide/concepts/linq/basic-linq-query-operations.md)   
 [Query Syntax and Method Syntax in LINQ](../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md)   
 [Standard Query Operators Overview](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [쿼리 키워드\(LINQ\)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [How Linq to Objects Queries Work](http://go.microsoft.com/fwlink/?LinkId=112389)   
 [Reading and Writing Queries](http://go.microsoft.com/fwlink/?LinkId=112391)   
 [What is a collection?](http://go.microsoft.com/fwlink/?LinkId=112394)   
 [Link to Everything: A List of LINQ Providers](http://go.microsoft.com/fwlink/?LinkId=112411)