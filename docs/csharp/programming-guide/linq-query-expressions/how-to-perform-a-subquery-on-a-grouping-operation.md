---
redirect_url: /dotnet/articles/csharp/linq/perform-a-subquery-on-a-grouping-operation
caps.handback.revision: 15
---
# 방법: 그룹화 작업에서 하위 쿼리 수행(C# 프로그래밍 가이드)
이 항목에서는 소스 데이터를 그룹으로 순서 정렬하는 쿼리를 만들어 각 그룹에 대한 하위 쿼리를 개별적으로 수행하는 두 가지 방법에 대해 설명합니다.  각 예제에서 기본적인 방법은 `newGroup`이라는 *연속 문자*를 사용하여 `newGroup`에 대한 새로운 하위 쿼리를 생성하여 소스 개체를 그룹화하는 것입니다.  이 하위 쿼리는 외부 쿼리를 사용하여 만든 각각의 새로운 그룹에 대해 실행됩니다.  이 특정 예제에서 마지막 출력은 그룹이 아니라 익명 형식의 기본 시퀀스입니다.  
  
 그룹화하는 방법에 대한 자세한 내용은 [group 절](../../../csharp/language-reference/keywords/group-clause.md)을 참조하십시오.  
  
 연속에 대한 자세한 내용은 [into](../../../csharp/language-reference/keywords/into.md)를 참조하십시오.  다음 예제에서는 메모리 내 데이터 구조를 데이터 소스로 사용하지만 모든 종류의 [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)] 데이터 소스에 적용되는 동일한 원칙을 사용합니다.  
  
## 예제  
 [!code-cs[csProgGuideLINQ#23](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-perform-a-subquery-on-a-grouping-operation_1.cs)]  
  
## 코드 컴파일  
 이 예제에는 [방법: 개체 컬렉션 쿼리](../../../csharp/programming-guide/linq-query-expressions/how-to-query-a-collection-of-objects.md)에서 샘플 응용 프로그램에 정의된 개체에 대한 참조가 포함되어 있습니다.  이 메서드를 컴파일하고 실행하려면 해당 응용 프로그램의 `StudentClass` 클래스에 이 메서드를 붙여넣고 이 메서드에 대한 `Main` 메서드의 호출을 추가합니다.  
  
 사용자 고유의 응용 프로그램에 이 메서드를 적용하는 경우 LINQ에서는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] 버전 3.5를 필요로 하며 프로젝트에는 System.Core.dll에 대한 참조와 System.Linq에 대한 using 지시문이 포함되어야 합니다.  LINQ to SQL, LINQ to XML 및 LINQ to DataSet 형식에는 추가 usings 및 참조가 필요합니다.  자세한 내용은 [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md)를 참조하십시오.  
  
## 참고 항목  
 [LINQ 쿼리 식](../../../csharp/programming-guide/linq-query-expressions/index.md)