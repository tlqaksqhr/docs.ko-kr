---
redirect_url: /dotnet/articles/csharp/linq/handle-exceptions-in-query-expressions
caps.handback.revision: 15
---
# 방법: 쿼리 식의 예외 처리(C# 프로그래밍 가이드)
쿼리 식의 컨텍스트에서 메서드를 호출할 수 있습니다.  그러나 데이터 소스의 내용 변경 및 예외 throw 등 의도하지 않은 결과가 발생할 수 있는 쿼리 식에서는 메서드를 호출하지 않는 것이 좋습니다.  이 예제에서는 예외 처리에 대한 일반적인 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] 지침을 위반하지 않고 쿼리 식에서 메서드를 호출할 때 예외가 발생하지 않도록 지정하는 방법을 보여 줍니다.  이러한 지침에서는 해당 컨텍스트에서 특정 예외가 throw되는 이유를 알고 있는 경우 해당 예외를 catch할 수 있다고 설명합니다.  자세한 내용은 [최선의 예외 구현 방법](../Topic/Best%20Practices%20for%20Exceptions.md)를 참조하십시오.  
  
 마지막 예제에서는 쿼리 실행 중에 예외를 throw해야 하는 경우를 처리하는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 예외 처리 코드를 쿼리 식 외부로 이동하는 방법을 보여 줍니다.  이러한 작업은 메서드가 쿼리에 대한 지역 변수에 종속되지 않는 경우에만 가능합니다.  
  
 [!code-cs[csProgGuideLINQ#10](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csrefLINQHowTos.cs#10)]  
  
## 예제  
 경우에 따라 쿼리 내에서 throw되는 예외에 대한 가장 좋은 응답은 쿼리 실행을 즉시 중지하는 것입니다.  다음 예제에서는 쿼리 본문 내부에서 throw되는 예외를 처리하는 방법을 보여 줍니다.  `SomeMethodThatMightThrow`에서 쿼리 실행을 중지하는 예외를 발생시킬 수 있다고 가정합니다.  
  
 `try` 블록에서는 쿼리 자체가 아니라 `foreach` 루프를 포함합니다.  이는 쿼리가 실제로 실행되는 지점에 `foreach` 루프가 있기 때문입니다.  자세한 내용은 [Introduction to LINQ Queries \(C\#\)](../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)를 참조하십시오.  
  
 [!code-cs[csProgGuideLINQ#12](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csrefLINQHowTos.cs#12)]  
  
## 코드 컴파일  
  
-   .NET Framework 버전 3.5를 대상으로 하는 [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs-current-short-md.md)] 프로젝트를 만듭니다.  기본적으로 프로젝트에는 System.Core.dll에 대한 참조 및 System.Linq 네임스페이스에 대한 `using` 지시문이 있습니다.  
  
-   프로젝트에 코드를 복사합니다.  
  
-   F5 키를 눌러 프로그램을 컴파일하고 실행합니다.  
  
 아무 키나 눌러 콘솔 창을 닫습니다.  
  
## 참고 항목  
 [LINQ 쿼리 식](../../../csharp/programming-guide/linq-query-expressions/index.md)