---
redirect_url: /dotnet/articles/csharp/linq/query-a-collection-of-objects
caps.handback.revision: 8
---
# 방법: 개체 컬렉션 쿼리(C# 프로그래밍 가이드)
이 예제에서는 `Student` 개체의 목록에서 간단한 쿼리를 수행하는 방법을 보여 줍니다.  각 `Student` 개체에는 학생과 네 개의 시험에 대한 학생 성적을 나타내는 목록에 관한 몇 가지 기본 정보가 포함되어 있습니다.  
  
 동일한 `students` 데이터 소스를 사용하는 이 단원에서는 이 응용 프로그램을 다른 예제용 프레임워크로 사용할 수 있습니다.  
  
## 예제  
 다음 쿼리에서는 첫 번째 시험에서 점수가 90점 이상인 학생을 반환합니다.  
  
 [!code-cs[csProgGuideLINQ#15](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-query-a-collection-of-objects_1.cs)]  
  
 이 쿼리는 테스트할 수 있도록 의도적으로 간단하게 만들었습니다.  예를 들어 `where` 절에서 자세한 조건자를 사용해 보거나 `orderby` 절을 사용하여 결과를 정렬할 수 있습니다.  
  
## 코드 컴파일  
  
-   .NET Framework 버전 3.5를 대상으로 하는 [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs-current-short-md.md)] 프로젝트를 만듭니다.  기본적으로 프로젝트에는 System.Core.dll에 대한 참조 및 System.Linq 네임스페이스에 대한 `using` 지시문이 있습니다.  
  
-   프로젝트에 코드를 복사합니다.  
  
-   F5 키를 눌러 프로그램을 컴파일하고 실행합니다.  
  
-   아무 키나 눌러 콘솔 창을 닫습니다.  
  
## 참고 항목  
 [LINQ 쿼리 식](../../../csharp/programming-guide/linq-query-expressions/index.md)