---
redirect_url: /dotnet/articles/csharp/linq/create-a-nested-group
caps.handback.revision: 12
---
# 방법: 중첩 그룹 만들기(C# 프로그래밍 가이드)
다음 예제에서는 [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)] 쿼리 식에서 중첩 그룹을 만드는 방법을 보여 줍니다.  학년이나 등급에 따라 만들어진 각 그룹은 개인의 이름에 기초한 그룹으로 더 세분화됩니다.  
  
## 예제  
 [!code-cs[csProgGuideLINQ#24](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csrefLINQHowTos.cs#24)]  
  
 중첩 그룹의 내부 요소를 반복하려면 세 개의 중첩 `foreach` 루프가 필요합니다.  
  
## 코드 컴파일  
 이 예제에는 [방법: 개체 컬렉션 쿼리](../../../csharp/programming-guide/linq-query-expressions/how-to-query-a-collection-of-objects.md)에서 샘플 응용 프로그램에 정의된 개체에 대한 참조가 포함되어 있습니다.  이 메서드를 컴파일하고 실행하려면 해당 응용 프로그램의 `StudentClass` 클래스에 이 메서드를 붙여넣고 이 메서드에 대한 `Main` 메서드의 호출을 추가합니다.  
  
 사용자 고유의 응용 프로그램에 이 메서드를 적용하는 경우 LINQ에서는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] 버전 3.5를 필요로 하며 프로젝트에는 System.Core.dll에 대한 참조와 System.Linq에 대한 using 지시문이 포함되어야 합니다.  LINQ to SQL, LINQ to XML 및 LINQ to DataSet 형식에는 추가 usings 및 참조가 필요합니다.  자세한 내용은 [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md)를 참조하십시오.  
  
## 참고 항목  
 [LINQ 쿼리 식](../../../csharp/programming-guide/linq-query-expressions/index.md)