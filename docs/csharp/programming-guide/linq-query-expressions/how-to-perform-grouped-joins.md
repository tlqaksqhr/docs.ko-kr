---
redirect_url: /dotnet/articles/csharp/linq/perform-grouped-joins
caps.handback.revision: 23
---
# 방법: 그룹화 조인 수행(C# 프로그래밍 가이드)
그룹 조인은 계층적 데이터 구조를 생성하는 데 유용합니다.  그룹 조인은 첫 번째 컬렉션의 각 요소와 두 번째 컬렉션의 연관된 요소 집합을 쌍으로 만듭니다.  
  
 예를 들어, Student라는 클래스나 관계형 데이터베이스 테이블은 Id 및 Name이라는 두 개의 필드를 포함할 수 있습니다.  Course라는 두 번째 클래스나 관계형 데이터베이스 테이블은 StudentId 및 CourseTitle이라는 두 개의 필드를 포함할 수 있습니다.  이 경우 일치하는 Student.Id 및 Course.StudentId를 기반으로 이러한 두 데이터 소스의 그룹 조인은 각 Student를 Course 개체\(비어 있을 수도 있음\)의 컬렉션과 그룹화합니다.  
  
> [!NOTE]
>  첫 번째 컬렉션의 각 요소는 두 번째 컬렉션에서 연관된 요소가 발견되는지 여부에 상관없이 그룹 조인의 결과 집합에 나타납니다.  연관된 요소가 발견되지 않을 경우 해당 요소에 대한 연관된 요소의 시퀀스는 비어 있습니다.  따라서 결과 선택기는 첫 번째 컬렉션의 모든 요소에 액세스할 수 있습니다.  이는 두 번째 컬렉션에 일치하는 항목이 없는 첫 번째 컬렉션의 요소에 액세스할 수 없는 비그룹 조인의 결과 선택기와 다릅니다.  
  
 이 항목의 첫 번째 예제에서는 그룹 조인을 수행하는 방법을 보여 줍니다.  두 번째 예제에서는 그룹 조인을 사용하여 XML 요소를 만드는 방법을 보여 줍니다.  
  
## 예제  
  
### 그룹 조인 예제  
 다음 예제에서는 `Pet.Owner` 속성과 일치하는 `Person`을 기반으로 `Person` 및 `Pet` 형식의 개체에 대한 그룹 조인을 수행합니다.  각 일치 항목에 대해 요소 쌍을 생성하는 비그룹 조인과 달리 그룹 조인은 첫 번째 컬렉션의 각 요소\(이 예제에서는 `Person` 개체\)에 대해 하나의 결과 개체만 생성합니다.  두 번째 컬렉션의 해당 요소\(이 예제에서는 `Pet` 개체\)는 컬렉션으로 그룹화됩니다.  마지막으로 결과 선택기 함수는 `Person.FirstName` 및 `Pet` 개체의 컬렉션으로 구성된 각 일치 항목에 대해 익명 형식을 만듭니다.  
  
 [!code-cs[CsLINQProgJoining#5](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/how-to-perform-grouped-joins_1.cs)]  
  
## 예제  
  
### XML을 만들기 위한 그룹 조인 예제  
 그룹 조인은 [!INCLUDE[sqltecxlinq](../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)]을 사용하여 XML을 만드는 데 이상적입니다.  다음 예제는 결과 선택기 함수에서 익명 형식을 만드는 대신에 조인된 개체를 나타내는 XML 요소를 만든다는 점을 제외하고 위의 예제와 비슷합니다.  [!INCLUDE[sqltecxlinq](../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)]에 대한 자세한 내용은 [LINQ to XML](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)을 참조하십시오.  
  
 [!code-cs[CsLINQProgJoining#6](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/how-to-perform-grouped-joins_2.cs)]  
  
## 코드 컴파일  
  
-   [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs-current-short-md.md)]에서 **콘솔 응용 프로그램** 프로젝트를 새로 만듭니다.  
  
-   아직 참조되지 않은 경우 System.Core.dll 및 System.Xml.Linq.dll에 대한 참조를 추가합니다.  
  
-   <xref:System.Linq> 및 <xref:System.Xml.Linq> 네임스페이스를 포함합니다.  
  
-   예제에서 코드를 복사하여 `Main` 메서드 아래의 program.cs 파일에 붙여넣습니다.  `Main` 메서드에 코드 줄을 추가하여 붙여넣은 메서드를 호출합니다.  
  
-   프로그램을 실행합니다.  
  
## 참고 항목  
 <xref:System.Linq.Enumerable.Join%2A>   
 <xref:System.Linq.Enumerable.GroupJoin%2A>   
 [Join Operations](../../../visual-basic/programming-guide/concepts/linq/join-operations.md)   
 [방법: 내부 조인 수행](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-inner-joins.md)   
 [방법: 왼쪽 우선 외부 조인 수행](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-left-outer-joins.md)   
 [LINQ to XML](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)   
 [익명 형식](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)