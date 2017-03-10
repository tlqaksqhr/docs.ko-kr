---
redirect_url: /dotnet/articles/csharp/linq/group-results-by-contiguous-keys
caps.handback.revision: 11
---
# 방법: 연속 키를 기준으로 결과 그룹화(C# 프로그래밍 가이드)
다음 예제에서는 요소를 연속 키의 하위 시퀀스를 나타내는 청크로 그룹화하는 방법을 보여 줍니다.  예를 들어 다음과 같은 시퀀스의 키\-값 쌍이 있다고 가정해 보겠습니다.  
  
|키|값|  
|-------|-------|  
|A|We|  
|A|think|  
|A|that|  
|B|Linq|  
|C|이 선언은 아래 선언과 같습니다.|  
|A|really|  
|B|cool|  
|B|\!|  
  
 다음과 같은 순서로 그룹이 만들어집니다.  
  
1.  We, think, that  
  
2.  Linq  
  
3.  이 선언은 아래 선언과 같습니다.  
  
4.  really  
  
5.  cool, \!  
  
 이 솔루션은 스레드로부터 안전하며 스트리밍 방식으로 결과를 반환하는 확장 메서드로 구현됩니다.  즉, 이 솔루션은 소스 시퀀스 전체를 이동하면서 그룹을 생성합니다.  `group` 또는 `orderby` 연산자와 달리 이 솔루션은 모든 시퀀스를 읽기 전에 호출자에 대한 그룹 반환을 시작할 수 있습니다.  
  
 소스 코드 주석에 설명된 것처럼, 스레드로부터의 안전성을 보장하기 위해 소스 시퀀스를 반복할 때 각 그룹이나 청크의 복사본을 만듭니다.  소스 시퀀스에 연속 항목 시퀀스가 많이 있다면 공용 언어 런타임에서 <xref:System.OutOfMemoryException>을 throw할 수 있습니다.  
  
## 예제  
 다음 예제에서는 확장 메서드와 해당 메서드를 사용하는 클라이언트 코드를 모두 보여 줍니다.  
  
 [!code-cs[cscsrefContiguousGroups#1](../../../csharp/programming-guide/linq-query-expressions/codesnippet/csharp/how-to-group-results-by-_1.cs)]  
  
 프로젝트에서 확장 메서드를 사용하려면 `MyExtensions` 정적 클래스를 새 소스 코드 파일이나 기존 소스 코드 파일에 복사하고 필요한 경우 적절한 네임스페이스에 대한 `using` 지시문을 추가합니다.  
  
## 참고 항목  
 [LINQ 쿼리 식](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Classification of Standard Query Operators by Manner of Execution](../../../visual-basic/programming-guide/concepts/linq/classification-of-standard-query-operators-by-manner-of-execution.md)