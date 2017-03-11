---
redirect_url: /dotnet/articles/csharp/linq/perform-left-outer-joins
caps.handback.revision: 23
---
# 방법: 왼쪽 우선 외부 조인 수행(C# 프로그래밍 가이드)
왼쪽 외부 조인은 두 번째 컬렉션에 연관된 요소가 있는지 여부에 상관없이 첫 번째 컬렉션의 각 요소가 반환되는 조인입니다.  사용 하면 [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)] 를 호출 하 여 왼쪽된 외부 조인을 수행 하는 <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> 메서드 그룹 조인의 결과를 합니다.  
  
## 예제  
 다음 예제에서는 그룹 조인의 결과에서 <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> 메서드를 사용하여 왼쪽 외부 조인을 수행하는 방법을 보여 줍니다.  
  
 두 컬렉션의 왼쪽 외부 조인을 생성하는 첫 번째 단계는 그룹 조인을 사용하여 내부 조인을 수행하는 것입니다.  이 프로세스에 대한 설명은 [방법: 내부 조인 수행](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-inner-joins.md)을 참조하십시오. 이 예제에서는 목록 `Person` 개체는 목록에 내부 조인 `Pet` 기반으로 하는 개체는 `Person` 일치 하는 개체 `Pet.Owner`.  
  
 두 번째 단계는 해당 요소가 오른쪽 컬렉션에 일치하는 항목이 없는 경우에도 결과 집합에서 첫 번째\(왼쪽\) 컬렉션의 각 요소를 포함하는 것입니다.  이렇게 하려면 그룹 조인에서 일치하는 요소의 각 시퀀스에 <xref:System.Linq.Enumerable.DefaultIfEmpty%2A>를 호출합니다.  이 예제에서 <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> 각 시퀀스에 일치 하는 라고 `Pet` 개체입니다.  메서드 경우 단일 기본값이 포함 된 컬렉션이 반환 시퀀스에 일치 하는 `Pet` 개체 수에 대 한 빈 `Person` 함으로써 각 보장 하는 개체를 `Person` 결과 컬렉션에 개체를 표현 합니다.  
  
> [!NOTE]
>  기본값은 참조 형식에 대 한 `null`. 따라서 예제 각각의 각 요소에 액세스 하기 전에 null 참조를 확인 합니다. `Pet` 컬렉션입니다.  
  
 [!code-cs[CsLINQProgJoining#7](../../../csharp/programming-guide/linq-query-expressions/codesnippet/csharp/Joins/joins.cs#7)]  
  
## 코드 컴파일  
  
-   [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs-current-short-md.md)]에서 콘솔 응용 프로그램 프로젝트를 새로 만듭니다.  
  
-   이미 참조되지 않았다면 System.Core.dll에 대한 참조를 추가합니다.  
  
-   <xref:System.Linq> 네임스페이스를 포함합니다.  
  
-   복사 하 고 program.cs 파일에 아래 예제에서 코드를 붙여 넣습니다.는 `Main` 메서드에서 `Program` 클래스입니다.  줄을 코드에 추가 된 `Main` 메서드를 호출 하는 `LeftOuterJoinExample` 메서드.  
  
-   프로그램을 실행합니다.  
  
## 참고 항목  
 <xref:System.Linq.Enumerable.Join%2A>   
 <xref:System.Linq.Enumerable.GroupJoin%2A>   
 [Join Operations](../../../visual-basic/programming-guide/concepts/linq/join-operations.md)   
 [방법: 내부 조인 수행](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-inner-joins.md)   
 [방법: 그룹화 조인 수행](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-grouped-joins.md)   
 [익명 형식](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)