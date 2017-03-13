---
redirect_url: /dotnet/articles/csharp/linq/perform-inner-joins
caps.handback.revision: 25
---
# 방법: 내부 조인 수행(C# 프로그래밍 가이드)
관계형 데이터베이스에서 말하는 *내부 조인*이란 첫 번째 컬렉션의 각 요소가 두 번째 컬렉션에서 일치하는 모든 요소에 대해 한 번만 표시되는 결과 집합을 생성하는 것입니다.  첫 번째 컬렉션의 요소와 일치하는 요소가 없는 경우 해당 요소가 결과 집합에 표시되지 않습니다.  C\#에서 `join` 절로 호출되는 <xref:System.Linq.Enumerable.Join%2A> 메서드는 내부 조인을 구현합니다.  
  
 이 항목에서는 다음과 같은 내부 조인의 네 가지 변형을 수행하는 방법을 보여 줍니다.  
  
-   간단한 키를 기준으로 두 데이터 소스의 요소를 연관시키는 간단한 내부 조인  
  
-   *복합* 키를 기준으로 두 데이터 소스의 요소를 연관시키는 내부 조인.  둘 이상의 값으로 구성된 복합 키를 사용하면 둘 이상의 속성을 기준으로 요소를 연관시킬 수 있습니다.  
  
-   연속된 조인 작업이 서로에게 추가되는 *여러 조인*  
  
-   그룹 조인을 사용하여 구현된 내부 조인  
  
## 예제  
  
## 간단한 키 조인 예제  
 다음 예제에서는 두 사용자 정의 형식\(`Person` 및 `Pet`\)의 개체를 포함하는 두 컬렉션을 만듭니다.  이 쿼리에서는 C\#의 `join` 절을 사용하여 `Owner`가 해당 `Person`인 `Pet` 개체와 `Person` 개체가 일치하는지 확인합니다.  C\#의 `select` 절은 결과 개체의 표시 모양을 정의합니다.  이 예제에서 결과 개체는 소유자의 이름과 애완 동물의 이름으로 구성된 익명 형식입니다.  
  
 [!code-cs[CsLINQProgJoining#1](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/how-to-perform-inner-joins_1.cs)]  
  
 `Person`에 일치하는 `Pet.Owner`를 갖는 `Pet` 개체가 없으므로 `LastName`이 "Huff"인 `Person` 개체는 결과 집합에 나타나지 않습니다.  
  
## 예제  
  
## 복합 키 조인 예제  
 하나의 속성을 기준으로 요소를 연관시키는 대신에 복합 키를 사용하여 여러 가지 속성을 기준으로 요소를 비교할 수 있습니다.  이를 위해 각 컬렉션에서 사용자가 비교할 속성으로 구성된 익명 형식을 반환하도록 키 선택기 함수를 지정합니다.  속성에 레이블을 지정하는 경우 각 키의 익명 형식에 동일한 레이블을 가져야 합니다.  또한 속성은 동일한 순서로 나타나야 합니다.  
  
 다음 예제에서는 `Employee` 개체의 목록과 `Student` 개체의 목록을 사용하여 학생이기도 한 직원을 확인할 수 있습니다.  이러한 형식에는 모두 <xref:System.String> 형식의 `FirstName`과 `LastName` 속성이 있습니다.  각 목록의 요소로부터 조인 키를 만드는 함수는 각 요소의 `FirstName` 및 `LastName` 속성으로 구성된 익명 형식을 반환합니다.  조인 작업은 이러한 복합 키가 같은지 비교하여 각 목록에서 이름과 성이 모두 일치하는 개체의 쌍을 반환합니다.  
  
 [!code-cs[CsLINQProgJoining#2](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/how-to-perform-inner-joins_2.cs)]  
  
## 예제  
  
## 여러 조인 예제  
 여러 조인을 수행하기 위해 서로에게 추가될 수 있는 조인 작업의 수에는 제한이 없습니다.  C\#의 각 `join` 절은 지정된 데이터 소스와 이전 조인의 결과를 연관시킵니다.  
  
 다음 예제에서는 세 개의 컬렉션인 `Person` 개체 목록, `Cat` 개체 목록 및 `Dog` 개체 목록을 만듭니다.  
  
 C\#의 첫 번째 `join` 절은 `Cat.Owner`와 일치하는 `Person`을 기준으로 일치하는 사람과 고양이를 찾습니다.  `Person` 개체와 `Cat.Name`을 포함하는 익명 형식의 시퀀스를 반환합니다.  
  
 C\#의 두 번째 `join` 절은 `Person` 형식의 `Owner` 속성 및 해당 동물의 이름 첫글자로 구성된 복합 키를 기준으로 첫 번째 조인으로 반환된 익명 형식을 제공된 개 목록의 `Dog` 개체와 연관시킵니다.  일치하는 각 쌍에서 `Cat.Name` 및 `Dog.Name` 속성을 포함하는 익명 형식의 시퀀스를 반환합니다.  이 조인은 내부 조인이므로 두 번째 데이터 소스에 일치하는 항목이 있는 첫 번째 데이터 소스의 해당 개체만 반환됩니다.  
  
 [!code-cs[CsLINQProgJoining#3](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/how-to-perform-inner-joins_3.cs)]  
  
## 예제  
  
## 그룹화 조인을 사용한 내부 조인 예제  
 다음 예제에서는 그룹 조인을 사용하여 내부 조인을 구현하는 방법을 보여 줍니다.  
  
 `query1`에서 `Person` 개체 목록은 `Pet.Owner` 속성에 일치하는 `Person`을 기준으로 `Pet` 개체 목록에 그룹 조인됩니다.  그룹 조인은 각 그룹이 `Person` 개체 및 일치하는 `Pet` 개체의 시퀀스로 구성된 중간 그룹의 컬렉션을 만듭니다.  
  
 쿼리에 두 번째 `from` 절을 추가하면 시퀀스의 해당 시퀀스가 보다 긴 시퀀스에 결합됩니다.  최종 시퀀스의 요소 형식은 `select` 절에서 지정됩니다.  이 예제에서 형식은 `Person.FirstName` 및 일치하는 각 쌍에 대한 `Pet.Name` 속성으로 구성된 익명 형식입니다.  
  
 `query1`의 결과는 내부 조인을 수행하기 위해 C\#의 `into` 절을 사용하지 않고 `join` 절을 사용하여 얻은 결과 집합과 동일합니다.  `query2` 변수에서는 이와 동일한 쿼리를 보여 줍니다.  
  
 [!code-cs[CsLINQProgJoining#4](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/how-to-perform-inner-joins_4.cs)]  
  
## 코드 컴파일  
  
-   [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs-current-short-md.md)]에서 콘솔 응용 프로그램 프로젝트를 새로 만듭니다.  
  
-   이미 참조되지 않았다면 System.Core.dll에 대한 참조를 추가합니다.  
  
-   <xref:System.Linq> 네임스페이스를 포함합니다.  
  
-   예제에서 코드를 복사하여 `Main` 메서드 아래의 program.cs 파일에 붙여넣습니다.  `Main` 메서드에 코드 줄을 추가하여 붙여넣은 메서드를 호출합니다.  
  
-   프로그램을 실행합니다.  
  
## 참고 항목  
 <xref:System.Linq.Enumerable.Join%2A>   
 <xref:System.Linq.Enumerable.GroupJoin%2A>   
 [Join Operations](../../../visual-basic/programming-guide/concepts/linq/join-operations.md)   
 [방법: 그룹화 조인 수행](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-grouped-joins.md)   
 [방법: 왼쪽 우선 외부 조인 수행](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-left-outer-joins.md)   
 [방법: 두 컬렉션 조인](../Topic/How%20to:%20Join%20Two%20Collections%20\(C%23\)%20\(LINQ%20to%20XML\).md)   
 [익명 형식](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)