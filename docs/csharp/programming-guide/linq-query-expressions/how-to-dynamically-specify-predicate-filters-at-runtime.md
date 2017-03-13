---
redirect_url: /dotnet/articles/csharp/linq/dynamically-specify-predicate-filters-at-runtime
caps.handback.revision: 22
---
# 방법: 런타임에 동적으로 조건자 필터 지정(C# 프로그래밍 가이드)
때로는 런타임 전에 `where` 절에서 소스 요소에 적용해야 하는 조건자 수를 알 수 없습니다.  다음 예제에서 볼 수 있듯이 동적으로 여러 개의 조건자 필터를 지정하는 한 가지 방법은 <xref:System.Linq.Enumerable.Contains%2A> 메서드를 사용하는 것입니다.  이 예제는 두 가지 과정을 거쳐 구성됩니다.  먼저 프로젝트는 프로그램에서 제공하는 값을 기준으로 필터링하여 실행됩니다.  그런 다음 런타임에 제공된 입력을 사용하여 프로젝트가 다시 실행됩니다.  
  
### Contains 메서드를 사용하여 필터링하려면  
  
1.  Visual Studio에서 새 콘솔 응용 프로그램을 엽니다.  프로그램 이름을 `PredicateFilters`로 지정합니다.  
  
2.  [방법: 개체 컬렉션 쿼리](../../../csharp/programming-guide/linq-query-expressions/how-to-query-a-collection-of-objects.md)에서 `StudentClass` 클래스를 복사하여 `Program` 클래스 아래에 있는 `PredicateFilters` 네임스페이스에 붙여 넣습니다.  `StudentClass`에서는 `Student` 개체의 목록을 제공합니다.  
  
3.  `StudentClass`의 `Main` 메서드를 주석으로 처리합니다.  
  
4.  `Program` 클래스를 다음 코드로 바꿉니다.  
  
     [!code-cs[csProgGuideLINQ#26](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-dynamically-specify-predicate-filters-at-runtime_1.cs)]  
  
5.  `DynamicPredicates` 클래스의 `Main` 메서드에서 `ids` 선언 아래에 다음 줄을 추가합니다.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
6.  F5 키를 눌러 프로젝트를 실행합니다.  
  
7.  명령 프롬프트 창에 다음 출력이 표시됩니다.  
  
     Garcia: 114  
  
     O'Donnell: 112  
  
     Omelchenko: 111  
  
8.  다음 단계로 프로젝트를 다시 실행합니다. 이번에는 배열 `ids` 대신 런타임에 입력된 값이 사용됩니다.  **솔루션 탐색기**에서 **PredicateFilters**를 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다.  
  
9. **디버그** 탭을 클릭합니다.  
  
10. **명령줄 인수** 창에서 `122 117 120 115`와 같이 공백으로 구분하여 122, 117, 120 및 115를 입력합니다.  프로젝트가 실행되면 입력된 값은 `Main` 메서드의 매개 변수인 `args`의 요소가 됩니다.  
  
11. `Main` 메서드에서 `QueryByID(ids)`를 `QueryByID(args)`로 변경합니다.  
  
12. F5 키를 눌러 프로젝트를 실행합니다.  
  
13. 명령 프롬프트 창에 다음 출력이 표시됩니다.  
  
     Adams: 120  
  
     Feng: 117  
  
     Garcia: 115  
  
     Tucker: 122  
  
### switch 문을 사용하여 필터링하려면  
  
1.  `switch` 문을 사용하면 선택적이고 미리 지정되어 있는 여러 쿼리 중에서 원하는 쿼리를 선택할 수 있습니다.  다음 예제에서 `studentQuery`는 런타임에 등급이 지정되었는지 연도가 지정되는지에 따라 다른 `where` 절을 사용합니다.  
  
2.  다음 메서드를 복사하여 `DynamicPredicates` 클래스에 붙여 넣습니다.  
  
     [!code-cs[csProgGuideLINQ#27](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-dynamically-specify-predicate-filters-at-runtime_2.cs)]  
  
3.  **명령줄 인수** 창에서 이전 절차의 ID 번호를 1부터 4까지의 정수로 바꿉니다.  
  
4.  `Main` 메서드에서 `QueryByID`에 대한 호출을 `args` 배열의 첫 번째 요소를 인수로 전달하는 `QueryByYear(args[0])` 호출로 바꿉니다.  
  
5.  F5 키를 눌러 프로젝트를 실행합니다.  
  
### 사용자 고유 응용 프로그램에서 이 메서드를 사용하려면  
  
-   사용자 고유의 응용 프로그램에 이 메서드를 적용하는 경우 LINQ에서는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]의 버전 3.5 또는 4를 필요로 하며 프로젝트에는 System.Core.dll에 대한 참조와 `System.Linq`에 대한 `using` 지시문이 포함되어야 합니다.  LINQ to SQL, LINQ to XML 및 LINQ to DataSet 형식에는 `using` 지시문 및 참조가 추가로 필요합니다.  자세한 내용은 [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md)를 참조하십시오.  
  
## 참고 항목  
 [LINQ 쿼리 식](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [where 절](../../../csharp/language-reference/keywords/where-clause.md)