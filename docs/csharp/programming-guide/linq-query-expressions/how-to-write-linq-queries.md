---
redirect_url: /dotnet/articles/csharp/linq/write-linq-queries
caps.handback.revision: 25
---
# 방법: C#에서 LINQ 쿼리 작성
이 항목에서는 C\#에서 [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)] 쿼리를 작성할 수 있는 세 가지 방법을 보여 줍니다.  
  
1.  쿼리 구문 사용  
  
2.  메서드 구문 사용  
  
3.  쿼리 구문과 메서드 구문의 조합 사용  
  
 다음 예제에서는 앞에서 설명한 각 방법을 사용하여 몇 가지 간단한 [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)] 쿼리를 보여 줍니다.  일반적으로 규칙은 가능하면 \(1\)을 사용하고 필요에 따라 \(2\)와 \(3\)을 사용하는 것입니다.  
  
> [!NOTE]
>  이러한 쿼리는 간단한 메모리 내 컬렉션을 수행합니다. 그러나 기본 구문은 [!INCLUDE[vbtecdlinq](../../../csharp/includes/vbtecdlinq-md.md)] 및 [!INCLUDE[sqltecxlinq](../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)]에서 사용된 구문과 동일합니다.  
  
## 예제  
  
## 쿼리 구문  
 대부분의 쿼리를 작성하는 데 권장되는 방법은 *쿼리 구문*을 사용하여 *쿼리 식*을 만드는 것입니다.  다음 예제에서는 세 개의 쿼리 식을 보여 줍니다.  첫 번째 쿼리 식에서는 `where` 절이 있는 조건을 적용하여 결과를 필터링하거나 제한하는 방법을 보여 줍니다.  소스 시퀀스에서 값이 7보다 크거나 3보다 작은 요소를 모두 반환합니다.  두 번째 식에서는 반환된 결과의 순서를 지정하는 방법을 보여 줍니다.  세 번째 식에서는 키에 따라 결과를 그룹화하는 방법을 보여 줍니다.  이 쿼리는 단어의 첫 번째 문자를 기준으로 두 개의 그룹을 반환합니다.  
  
 [!code-cs[csProgGuideLINQ#5](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csrefLINQHowTos.cs#5)]  
  
 쿼리 형식은 <xref:System.Collections.Generic.IEnumerable%601>입니다.  이러한 쿼리는 모두 다음 예제와 같이 `var`를 사용하여 작성할 수 있습니다.  
  
 `var query = from num in numbers...`  
  
 이전 예제에서는 `foreach` 문에서 쿼리 상수를 반복할 때까지 쿼리가 실제로 실행되지 않습니다.  자세한 내용은 [Introduction to LINQ Queries \(C\#\)](../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)를 참조하십시오.  
  
## 예제  
  
## 메서드 구문  
 일부 쿼리 작업은 메서드 호출로 표시되어야 합니다.  가장 일반적인 이러한 메서드는 <xref:System.Linq.Enumerable.Sum%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, <xref:System.Linq.Enumerable.Average%2A> 등과 같은 singleton 숫자 값을 반환하는 메서드입니다.  이러한 메서드는 단일 값만 나타내며 추가 쿼리 작업에 대해 소스로 사용할 수 없으므로 항상 모든 쿼리에서 마지막으로 호출되어야 합니다.  다음 예제에서는 쿼리 식에서 메서드를 호출하는 방법을 보여 줍니다.  
  
 [!code-cs[csProgGuideLINQ#6](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csrefLINQHowTos.cs#6)]  
  
## 예제  
 메서드에 매개 변수가 있으면 매개 변수가 다음 예제와 같이 [람다](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) 식 형식으로 제공됩니다.  
  
 [!code-cs[csProgGuideLINQ#7](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csrefLINQHowTos.cs#7)]  
  
 앞의 쿼리에서 쿼리 \#4만 즉시 실행됩니다.  이는 쿼리가 단일 값을 반환하고 제네릭 <xref:System.Collections.Generic.IEnumerable%601> 컬렉션이 아니기 때문입니다.  이 메서드 자체는 값을 계산하기 위해 `foreach`를 사용해야 합니다.  
  
 앞의 각 쿼리는 다음 예제와 같이 [var](../../../csharp/language-reference/keywords/var.md)를 통한 암시적 형식 지정을 사용하여 작성할 수 있습니다.  
  
 [!code-cs[csProgGuideLINQ#8](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csrefLINQHowTos.cs#8)]  
  
## 예제  
  
## 혼합 쿼리와 메서드 구문  
 이 예제에서는 쿼리 절의 결과로 메서드 구문을 사용하는 방법을 보여 줍니다.  쿼리 식을 괄호로 묶은 다음 도트 연산자를 적용하고 메서드를 호출합니다.  다음 예제에서는 쿼리 \#7에서 값이 3과 7 사이인 숫자의 수를 반환합니다.  그러나 일반적으로 두 번째 변수를 사용하여 메서드 호출의 결과를 저장하는 것이 좋습니다.  이 경우 쿼리가 쿼리 결과와 혼동될 가능성은 낮습니다.  
  
 [!code-cs[csProgGuideLINQ#9](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csrefLINQHowTos.cs#9)]  
  
 쿼리 \#7에서는 컬렉션이 아닌 단일 값을 반환하기 때문에 쿼리가 즉시 실행됩니다.  
  
 앞의 쿼리를 다음과 같이 `var`를 통한 암시적 형식 지정을 사용하여 작성할 수 있습니다.  
  
```  
var numCount = (from num in numbers...  
```  
  
 해당 쿼리는 다음과 같이 메서드 구문으로 작성될 수 있습니다.  
  
```  
var numCount = numbers.Where(n => n < 3 || n > 7).Count();  
```  
  
 해당 쿼리는 다음과 같이 명시적 형식 지정을 사용하여 작성할 수 있습니다.  
  
```  
int numCount = numbers.Where(n => n < 3 || n > 7).Count();  
```  
  
## 참고 항목  
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [Walkthrough: Writing Queries in C\#](../../../csharp/programming-guide/concepts/linq/walkthrough-writing-queries-linq.md)   
 [LINQ 쿼리 식](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [where 절](../../../csharp/language-reference/keywords/where-clause.md)