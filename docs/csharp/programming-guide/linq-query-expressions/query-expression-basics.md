---
redirect_url: /dotnet/articles/csharp/linq/query-expression-basics
caps.handback.revision: 32
---
# 쿼리 식 기본 사항(C# 프로그래밍 가이드)
## 쿼리란 무엇이고 쿼리의 기능은 무엇입니까?  
 *쿼리*는 지정한 데이터 소스\(또는 소스\)에서 어떤 데이터를 검색할지와 반환되는 데이터가 어떤 모양과 구성을 가져야 하는지를 설명하는 명령 집합입니다.  쿼리는 쿼리에서 생성되는 결과와는 다릅니다.  
  
 일반적으로 소스 데이터는 같은 종류의 요소 시퀀스로 논리적으로 구성되어 있습니다.  SQL 데이터베이스 테이블에는 행 시퀀스가 포함됩니다.  마찬가지로 [!INCLUDE[vstecado](../../../csharp/programming-guide/concepts/linq/includes/vstecado-md.md)] <xref:System.Data.DataTable>에는 <xref:System.Data.DataRow> 개체의 시퀀스가 포함됩니다.  XML 파일에는 XML 요소의 "시퀀스"가 있습니다. 여기서는 이러한 요소가 트리 구조에 계층적으로 구성되어 있습니다.  메모리 내 컬렉션에는 개체의 시퀀스가 포함됩니다.  
  
 응용 프로그램의 관점에서 보면 원래 소스 데이터의 특정 형식과 구조는 중요하지 않습니다.  응용 프로그램에서는 항상 소스 데이터를 <xref:System.Collections.Generic.IEnumerable%601> 또는 <xref:System.Linq.IQueryable%601> 컬렉션으로 간주합니다.  [!INCLUDE[sqltecxlinq](../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)]에서 소스 데이터를 `IEnumerable`\<<xref:System.Xml.Linq.XElement>\>로 표시할 수 있습니다  [!INCLUDE[linq_dataset](../../../csharp/programming-guide/linq-query-expressions/includes/linq-dataset-md.md)]에서는 `IEnumerable`\<<xref:System.Data.DataRow>\>입니다.  [!INCLUDE[vbtecdlinq](../../../csharp/includes/vbtecdlinq-md.md)]에서는 SQL 테이블의 데이터를 나타내기 위해 정의한 사용자 지정 개체에 상관없이 `IEnumerable` 또는 `IQueryable`입니다.  
  
 이러한 소스 시퀀스가 지정되며 쿼리에서는 다음 세 가지 작업 중 하나를 수행할 수 있습니다.  
  
-   요소의 하위 집합을 검색하여 개별 요소를 수정하지 않고 새 시퀀스를 생성합니다.  그런 다음 쿼리에서는 다음 예제와 같이 반환된 시퀀스를 다양한 방법을 정렬하거나 그룹화합니다. 이 예제에서는 `scores`가 `int[]`인 것으로 가정합니다.  
  
     [!code-cs[csrefQueryExpBasics#45](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_1.cs)]  
  
-   앞의 예제와 같이 요소의 시퀀스를 검색하지만 이를 새 개체 형식으로 변환합니다.  예를 들어 쿼리에서 데이터 소스의 특정 고객 레코드 중 성만 검색할 수 있습니다.  또는 전체 레코드를 검색한 다음 최종 결과 시퀀스를 생성하기 전에 해당 레코드를 사용하여 다른 메모리 내 개체 형식이나 XML 데이터를 구성할 수도 있습니다.  다음 예제에서는 `int`에서 `string`으로 변환합니다.  새 형식은 `highScoresQuery`가 됩니다.  
  
     [!code-cs[csrefQueryExpBasics#46](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_2.cs)]  
  
-   소스 데이터에 대한 다음과 같은 singleton 값을 검색합니다.  
  
    -   특정 조건과 일치하는 요소 수  
  
    -   가장 큰 값 또는 가장 작은 값을 갖는 요소  
  
    -   조건과 일치하는 첫 번째 항목 또는 지정한 요소 집합에서 특정 값의 합.  예를 들어 다음 쿼리는 `scores` 정수 배열에서 80점보다 높은 점수의 수를 반환합니다.  
  
     [!code-cs[csrefQueryExpBasics#47](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_3.cs)]  
  
     앞의 예제에서는 `Count` 메서드에 대한 호출 앞에 있는 쿼리 식을 괄호로 묶었습니다.  또한 구체적인 결과를 저장할 새 변수를 사용하여 이 식을 표현할 수도 있습니다.  이 기술을 사용하면 쿼리를 저장하는 변수와 결과를 저장하는 쿼리가 별도로 유지되기 때문에 읽기가 더 쉬워집니다.  
  
     [!code-cs[csrefQueryExpBasics#48](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_4.cs)]  
  
 앞의 예제에서는 `highScoresQuery`에서 반환되는 요소 수를 확인하기 위해 `Count`에서 결과를 반복해야 하므로 쿼리가 `Count`에 대한 호출에서 실행됩니다.  
  
## 쿼리 식이란?  
 *쿼리 식*은 쿼리 구문으로 표현되는 쿼리입니다.  쿼리 식은 고급 언어 구문입니다.  다른 식과 똑같으며 C\# 식을 사용할 수 있는 모든 컨텍스트에서 사용할 수 있습니다.  쿼리 식은 SQL 또는 XQuery와 유사한 선언적 구문으로 작성된 절의 집합으로 구성됩니다.  각 절은 하나 이상의 C\# 식을 포함하고 이러한 식 자체도 쿼리 식이거나 쿼리 식을 포함할 수 있습니다.  
  
 쿼리 식은 [from](../../../csharp/language-reference/keywords/from-clause.md) 절로 시작하여 [select](../../../csharp/language-reference/keywords/select-clause.md) 또는 [group](../../../csharp/language-reference/keywords/group-clause.md) 절로 끝나야 합니다.  첫 번째 `from` 절과 마지막 `select` 또는 `group` 절 사이에는  [where](../../../csharp/language-reference/keywords/where-clause.md), [orderby](../../../csharp/language-reference/keywords/orderby-clause.md), [join](../../../csharp/language-reference/keywords/join-clause.md), [let](../../../csharp/language-reference/keywords/let-clause.md) 및 추가 [from](../../../csharp/language-reference/keywords/from-clause.md) 절과 같은 선택적 절 중 하나 이상이 포함될 수 있습니다.  또한 [into](../../../csharp/language-reference/keywords/into.md) 키워드를 사용하여 `join` 또는 `group` 절의 결과를 같은 쿼리 식에 있는 다른 쿼리 절의 소스로 사용할 수 있습니다.  
  
### 쿼리 변수  
 [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)]에서 쿼리 변수는 쿼리의 *결과*가 아닌 *쿼리*를 저장하는 변수입니다. 좀 더 구체적으로 말하면 쿼리 변수는 항상 열거 가능한 형식이며 `foreach` 문이나 해당 `IEnumerator.MoveNext` 메서드에 대한 직접 호출에서 반복되는 경우 요소의 시퀀스를 생성합니다.  
  
 다음 코드 예제에서는 하나의 데이터 소스, 하나의 필터링 절 및 순서 지정 절이 있고 소스 요소의 변환은 없는 간단한 쿼리 식을 보여 줍니다.  `select` 절은 쿼리를 끝냅니다.  
  
 [!code-cs[csrefQueryExpBasics#49](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_5.cs)]  
  
 앞의 예제에서 `scoreQuery`는 *쿼리 변수*이며 그냥 *쿼리*라고 하기도 합니다.  쿼리 변수에는 `foreach` 루프에서 생성되는 실제 결과 데이터가 저장되지 않습니다.  그리고 `foreach` 문을 실행할 때 쿼리 결과가 쿼리 변수 `scoreQuery`를 통해 반환되지 않습니다.  대신 반복 변수 `testScore`를 통해 반환됩니다.  `scoreQuery` 변수는 두 번째 `foreach` 루프에서 반복될 수 있습니다.  이 변수는 해당 변수와 데이터 소스가 수정되지 않은 경우 동일한 결과를 생성합니다.  
  
 쿼리 변수는 쿼리 구문이나 메서드 구문 또는 이 둘의 조합으로 표현한 쿼리를 저장할 수 있습니다.  다음 예제에서 `queryMajorCities`와 `queryMajorCities2`는 모두 쿼리 변수입니다:  
  
 [!code-cs[csrefQueryExpBasics#50](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_6.cs)]  
  
 반면 다음 두 예제에서는 각각 쿼리로 초기화되어 있지만 쿼리 변수는 아닌 변수를 보여 줍니다.  이들은 결과를 저장하므로 쿼리 변수가 아닙니다:  
  
 [!code-cs[csrefQueryExpBasics#51](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_7.cs)]  
  
> [!NOTE]
>  [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)] 문서에서 쿼리를 저장하는 변수는 이름에 "query"라는 단어가 포함됩니다.  실제 결과를 저장하는 변수는 이름에 "query"를 포함하지 않습니다.  
  
 쿼리를 표현하는 다양한 방법에 대한 자세한 내용은 [Query Syntax and Method Syntax in LINQ](../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md)를 참조하십시오.  
  
#### 쿼리 변수에 대한 명시적 및 암시적 형식화  
 일반적으로 이 문서에서는 쿼리 변수와 [select 절](../../../csharp/language-reference/keywords/select-clause.md) 사이의 형식 관계를 보여 주기 위해 쿼리 변수의 명시적 형식을 제공합니다.  그러나 [var](../../../csharp/language-reference/keywords/var.md) 키워드를 사용하여 컴파일러에서 컴파일할 때 쿼리 변수 또는 다른 지역 변수의 형식을 유추하도록 할 수도 있습니다.  예를 들어 이 항목의 앞부분에 있는 쿼리 예제를 다음과 같이 암시적 형식화를 사용하여 표현할 수도 있습니다:  
  
 [!code-cs[csrefQueryExpBasics#52](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_8.cs)]  
  
 자세한 내용은 [암시적으로 형식화한 지역 변수](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) 및 [Type Relationships in LINQ Query Operations](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)을 참조하십시오.  
  
### 쿼리 식 시작  
 쿼리 식은 `from` 절로 시작해야 합니다.  이 절은 범위 변수와 함께 데이터 소스를 지정합니다.  범위 변수는 소스 시퀀스가 이동될 때 소스 시퀀스의 각 연속 요소를 나타냅니다.  범위 변수는 데이터 소스에 있는 요소의 형식을 기반으로 하는 강력한 형식입니다.  다음 예제에서 `countries`는 `Country` 개체의 배열이므로 범위 변수도 `Country`로 형식화됩니다.  범위 변수는 강력한 형식이므로 도트 연산자를 사용하여 형식의 사용 가능한 멤버에 액세스할 수 있습니다.  
  
 [!code-cs[csrefQueryExpBasics#53](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_9.cs)]  
  
 범위 변수는 쿼리가 세미콜론이나 *continuation* 절로 종료될 때까지 범위 내에 있습니다.  
  
 쿼리 식에는 여러 `from` 절이 포함될 수 있습니다.  소스 시퀀스의 각 요소가 컬렉션이거나 컬렉션을 포함하는 경우 추가 `from` 절을 사용합니다.  예를 들어 `Country` 개체의 컬렉션이 있고 이들 각각에 `Cities`라는 `City` 개체의 컬렉션이 포함되어 있다고 가정합니다.  각 `Country`에서 `City` 개체를 쿼리하려면 다음과 같이 두 개의 `from` 절을 사용합니다.  
  
 [!code-cs[csrefQueryExpBasics#54](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_10.cs)]  
  
 자세한 내용은 [from 절](../../../csharp/language-reference/keywords/from-clause.md)를 참조하십시오.  
  
### 쿼리 식 종료  
 쿼리 식은 `select` 절 또는 `group` 절로 끝나야 합니다.  
  
#### group 절  
 `group` 을 사용하면 지정하는 키별로 구성된 그룹 시퀀스를 생성할 수 있습니다.  키는 모든 데이터 형식을 사용할 수 있습니다.  예를 들어 다음 쿼리에서는 하나 이상의 `Country` 개체를 포함하는 그룹 시퀀스를 생성하며 해당 키가 `char` 값입니다.  
  
 [!code-cs[csrefQueryExpBasics#55](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_11.cs)]  
  
 그룹화에 대한 자세한 내용은 [group 절](../../../csharp/language-reference/keywords/group-clause.md)을 참조하십시오.  
  
#### select 절  
 `select` 절을 사용하면 다른 모든 형식의 시퀀스를 생성할 수 있습니다.  간단한 `select` 문에서는 데이터 소스에 포함된 개체와 동일한 형식의 개체 시퀀스를 생성합니다.  이 예제에서 데이터 소스에는 `Country` 개체가 포함되어 있습니다.  `orderby` 절은 요소를 새로운 순서로 정렬하고 `select` 절은 다시 정렬된 `Country` 개체의 시퀀스를 생성합니다.  
  
 [!code-cs[csrefQueryExpBasics#56](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_12.cs)]  
  
 `select` 절을 사용하여 소스 데이터를 새로운 형식의 시퀀스로 변환할 수도 있습니다.  이러한 변환을 *프로젝션*이라고도 합니다.  다음 예제에서 `select` 절은 원래 요소에 있는 필드의 하위 집합만 포함하는 익명 형식의 시퀀스를 *프로젝션*합니다.  새 개체는 개체 이니셜라이저를 사용하여 초기화됩니다.  
  
 [!code-cs[csrefQueryExpBasics#57](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_13.cs)]  
  
 `select` 절을 사용하여 소스 데이터를 변환하는 모든 방법에 대한 자세한 내용은 [select 절](../../../csharp/language-reference/keywords/select-clause.md)을 참조하십시오.  
  
#### "into"로 연속  
 `select` 또는 `group` 절에서 `into` 키워드를 사용하여 쿼리를 저장하는 임시 식별자를 만들 수 있습니다.  그룹화 또는 선택 작업 후에 쿼리에서 추가 쿼리 작업을 수행해야 하는 경우에 이렇게 합니다.  다음 예제에서는 1천만 범위 내에서 인구에 따라 `countries`를 그룹화합니다.  이러한 그룹을 만든 후 추가 절에서 일부 그룹을 필터링한 다음 그룹을 오름차순으로 정렬합니다.  이러한 추가 작업을 수행하려면 `countryGroup`으로 나타내는 연속이 필요합니다.  
  
 [!code-cs[csrefQueryExpBasics#58](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_14.cs)]  
  
 자세한 내용은 [into](../../../csharp/language-reference/keywords/into.md)를 참조하십시오.  
  
### 필터링, 정렬 및 조인  
 시작하는 `from` 절과 끝내는 `select` 또는 `group` 절 사이에 있는 다른 모든 절\(`where`, `join`, `orderby`, `from`, `let`\)은 선택적입니다.  선택적 절은 쿼리 본문에서 사용하지 않거나 여러 번 사용할 수 있습니다.  
  
#### where 절  
 `where` 절을 사용하면 하나 이상의 ㅈ 조건자 식을 기반으로 소스 데이터의 요소를 필터링할 수 있습니다.  다음 예제의 `where` 절에는 두 개의 조건자가 있습니다.  
  
 [!code-cs[csrefQueryExpBasics#59](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_15.cs)]  
  
 자세한 내용은 [where 절](../../../csharp/language-reference/keywords/where-clause.md)을 참조하십시오.  
  
#### orderby 절  
 `orderby` 절을 사용하면 결과를 오름차순이나 내림차순으로 정렬할 수 있습니다.  또한 2차 정렬 순서를 지정할 수도 있습니다.  다음 예제에서는 `country` 개체에 대해 `Area` 속성을 사용하여 기본 정렬을 수행합니다.  그런 다음 `Population` 속성을 사용하여 2차 정렬을 수행합니다.  
  
 [!code-cs[csrefQueryExpBasics#60](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_16.cs)]  
  
 `ascending` 키워드는 선택적이며 순서를 지정하지 않는 경우 기본 정렬 순서로 사용됩니다.  자세한 내용은 [orderby 절](../../../csharp/language-reference/keywords/orderby-clause.md)을 참조하십시오.  
  
#### join 절  
 `join` 절을 사용하면 한 데이터 소스의 요소와 다른 데이터 소스의 열을 각 요소에서 지정한 키 사이의 같음 비교를 기반으로 연결 또는 결합할 수 있습니다.  [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)]에서 조인 작업은 해당 요소의 형식이 다른 개체의 시퀀스에 대해 수행합니다.  두 시퀀스를 조인한 후에는 `select` 또는 `group` 문을 사용하여 출력 시퀀스에 저장할 요소를 지정해야 합니다.  또한 익명 형식을 사용하여 연관된 각 요소 집합의 속성을 출력 시퀀스의 새 형식으로 결합할 수 있습니다.  다음 예제에서는 해당 `Category` 속성이 `categories` 문자열 변수의 범주 중 하나와 일치하는 `prod` 개체를 연결합니다.  `Category`가 `categories`의 어떤 문자열과도 일치하지 않는 제품은 필터링됩니다.  `select` 문에서는 해당 속성을 `cat` 및 `prod` 모두에서 가져오는 새 형식을 프로젝션합니다.  
  
 [!code-cs[csrefQueryExpBasics#61](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_17.cs)]  
  
 또한 [into](../../../csharp/language-reference/keywords/into.md) 키워드를 사용하여 `join` 작업의 결과를 임시 변수에 저장하는 방법을 통해 그룹 조인을 수행할 수도 있습니다.  자세한 내용은 [join 절](../../../csharp/language-reference/keywords/join-clause.md)을 참조하십시오.  
  
#### let 절  
 `let` 절을 사용하면 메서드와 같은 식의 결과를 새 범위 변수에 저장할 수 있습니다.  다음 예제에서 범위 변수 `firstName`는 `Split`에서 반환된 문자열 배열의 첫 번째 요소를 저장합니다.  
  
 [!code-cs[csrefQueryExpBasics#62](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_18.cs)]  
  
 자세한 내용은 [let 절](../../../csharp/language-reference/keywords/let-clause.md)을 참조하십시오.  
  
### 쿼리 식의 하위 쿼리  
 쿼리 절 자체에 쿼리 식이 포함될 수 있으며 이를 *하위 쿼리*라고도 합니다.  각 하위 쿼리는 자체의 `from` 절로 시작되며 이 절은 첫 번째 `from` 절의 동일한 데이터 소스를 가리키지 않아도 됩니다.  예를 들어 다음 쿼리에서는 select 문에서 그룹화 작업의 결과를 검색하기 위해 사용된 쿼리 식을 보여 줍니다.  
  
 [!code-cs[csrefQueryExpBasics#63](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_19.cs)]  
  
 자세한 내용은 [방법: 그룹화 작업에서 하위 쿼리 수행](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-a-subquery-on-a-grouping-operation.md)를 참조하십시오.  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [LINQ 쿼리 식](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [쿼리 키워드\(LINQ\)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [Standard Query Operators Overview](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)