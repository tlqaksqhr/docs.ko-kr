---
title: "group 절(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "group"
  - "group_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "group 절[C#]"
  - "group 키워드[C#]"
ms.assetid: c817242e-b12c-4baa-a57e-73ee138f34d1
caps.latest.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 24
---
# group 절(C# 참조)
`group` 절은 그룹의 키 값과 일치하는 하나 이상의 항목을 포함하는 <xref:System.Linq.IGrouping%602> 개체 시퀀스를 반환합니다.  예를 들어 각 문자열의 첫 글자에 따라 문자열 시퀀스를 그룹화할 수 있습니다.  이 경우 첫 글자가 키가 되고 키의 형식은 [char](../../../csharp/language-reference/keywords/char.md)이며 각 <xref:System.Linq.IGrouping%602> 개체의 `Key` 속성에 저장됩니다.  컴파일러가 키의 형식을 유추합니다.  
  
 다음 예제와 같이 `group` 절을 사용하여 쿼리 식을 끝낼 수 있습니다.  
  
 [!code-cs[cscsrefQueryKeywords#10](../../../csharp/language-reference/keywords/codesnippet/csharp/csquerykeywords/Group.cs#10)]  
  
 각 그룹에서 추가 쿼리 작업을 수행하려면 [into](../../../csharp/language-reference/keywords/into.md) 컨텍스트 키워드를 사용하여 임시 식별자를 지정할 수 있습니다.  `into`를 사용하는 경우 다음 발췌 내용과 같이 쿼리를 계속하여 `select` 문이나 다른 `group` 절로 끝내야 합니다.  
  
 [!code-cs[cscsrefQueryKeywords#11](../../../csharp/language-reference/keywords/codesnippet/csharp/csquerykeywords/Group.cs#11)]  
  
 `into`를 사용하거나 사용하지 않고 `group`을 사용하는 방법을 보여 주는 보다 완전한 예제는 이 항목의 예제 단원을 참조하십시오.  
  
## 그룹 쿼리의 결과 열거  
 `group` 쿼리에 의해 생성된 <xref:System.Linq.IGrouping%602> 개체는 기본적으로 목록의 목록이므로 중첩 [foreach](../../../csharp/language-reference/keywords/foreach-in.md) 루프를 사용하여 각 그룹의 항목에 액세스해야 합니다.  바깥쪽 루프는 그룹 키를 반복하고 안쪽 루프는 그룹 자체의 각 항목을 반복합니다.  그룹에 키는 포함될 수 있지만 요소는 포함될 수 없습니다.  이전 코드 예제에서 쿼리를 실행하는 `foreach` 루프는 다음과 같습니다.  
  
 [!code-cs[cscsrefQueryKeywords#12](../../../csharp/language-reference/keywords/codesnippet/csharp/csquerykeywords/Group.cs#12)]  
  
## 키 형식  
 그룹 키는 문자열, 기본 제공 숫자 형식 또는 사용자 정의 명명된 형식이나 익명 형식과 같은 임의의 형식일 수 있습니다.  
  
### 문자열로 그룹화  
 앞의 코드 예제에서는 `char`를 사용했습니다.  전체 성 등의 문자열 키를 대신 지정할 수도 있습니다.  
  
 [!code-cs[cscsrefQueryKeywords#13](../../../csharp/language-reference/keywords/codesnippet/csharp/csquerykeywords/Group.cs#13)]  
  
### 부울 값으로 그룹화  
 다음 예제에서는 키에 부울 값을 사용하여 결과를 두 개의 그룹으로 나누는 방법을 보여 줍니다.  `group` 절의 하위 식에서 값이 생성됩니다.  
  
 [!code-cs[cscsrefQueryKeywords#14](../../../csharp/language-reference/keywords/codesnippet/csharp/csquerykeywords/Group.cs#14)]  
  
### 숫자 범위로 그룹화  
 다음 예제에서는 식을 사용하여 백분위수 범위를 나타내는 숫자 그룹 키를 만듭니다.  `group` 절에서 메서드를 두 번 호출할 필요가 없도록 메서드 호출 결과를 저장할 편리한 위치로 [let](../../../csharp/language-reference/keywords/let-clause.md)을 사용합니다.  또한 "0으로 나누기" 예외를 방지하기 위해 이 코드는 `group` 절에서 학생의 평균이 0이 아닌지 확인합니다.  쿼리 식에서 메서드를 안전하게 사용하는 방법에 대한 자세한 내용은 [방법: 쿼리 식의 예외 처리](../../../csharp/programming-guide/linq-query-expressions/how-to-handle-exceptions-in-query-expressions.md)를 참조하십시오.  
  
 [!code-cs[cscsrefQueryKeywords#15](../../../csharp/language-reference/keywords/codesnippet/csharp/csquerykeywords/Group.cs#15)]  
  
### 복합 키로 그룹화  
 둘 이상의 키에 따라 요소를 그룹화하려는 경우 복합 키를 사용합니다.  익명 형식이나 명명된 형식으로 복합 키를 만들어 키 요소를 포함합니다.  다음 예제에서는 `Person` 클래스가 `surname` 및 `city`라는 멤버로 선언되었다고 가정합니다.  `group` 클래스는 성과 구\/군\/시가 같은 각 개인 집합에 대해 별도의 그룹이 만들어지게 합니다.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 쿼리 변수를 다른 메서드로 전달해야 하는 경우 명명된 형식을 사용합니다.  키에 대해 자동 구현된 속성을 사용하여 특수 클래스를 만든 다음 <xref:System.Object.Equals%2A> 및 <xref:System.Object.GetHashCode%2A> 메서드를 재정의합니다.  이러한 메서드를 반드시 재정의할 필요가 없는 구조체를 사용할 수도 있습니다.  자세한 내용은 [방법: 자동으로 구현된 속성을 사용하여 간단한 클래스 구현](../../../csharp/programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md) 및 [How to: Query for Duplicate Files in a Directory Tree \(LINQ\)](../Topic/How%20to:%20Query%20for%20Duplicate%20Files%20in%20a%20Directory%20Tree%20\(LINQ\).md)을 참조하십시오.  두 번째 항목에는 복합 키에 명명된 형식을 사용하는 방법을 보여 주는 코드 예제가 있습니다.  
  
## 예제  
 다음 예제에서는 그룹에 적용되는 추가 쿼리 논리가 없을 때 소스 데이터를 그룹으로 정렬하기 위한 표준 패턴을 보여 줍니다.  이를 비연속 그룹화라고 합니다.  문자열 배열의 요소는 첫 글자에 따라 그룹화됩니다.  쿼리 결과는 그룹의 각 항목을 포함하는 <xref:System.Collections.Generic.IEnumerable%601> 컬렉션 및 `char` 형식의 public `Key` 속성을 포함하는 <xref:System.Linq.IGrouping%602> 형식입니다.  
  
 `group` 절의 결과는 시퀀스의 시퀀스입니다.  따라서 반환된 각 그룹 내의 개별 요소에 액세스하려면 다음 예제와 같이 그룹 키를 반복하는 루프 내부의 중첩 `foreach` 루프를 사용합니다.  
  
 [!code-cs[cscsrefQueryKeywords#16](../../../csharp/language-reference/keywords/codesnippet/csharp/csquerykeywords/Group.cs#16)]  
  
## 예제  
 이 예제에서는 *연속*에 `into`를 사용하여 그룹을 만든 후 그룹에서 추가 논리를 수행하는 방법을 보여 줍니다.  자세한 내용은 [into](../../../csharp/language-reference/keywords/into.md)를 참조하십시오.  다음 예제에서는 각 그룹을 쿼리하여 키 값이 모음인 그룹만 선택합니다.  
  
 [!code-cs[cscsrefQueryKeywords#17](../../../csharp/language-reference/keywords/codesnippet/csharp/csquerykeywords/Group.cs#17)]  
  
## 설명  
 컴파일 타임에 `group` 절은 <xref:System.Linq.Enumerable.GroupBy%2A> 메서드에 대한 호출로 변환됩니다.  
  
## 참고 항목  
 <xref:System.Linq.IGrouping%602>   
 <xref:System.Linq.Enumerable.GroupBy%2A>   
 <xref:System.Linq.Enumerable.ThenBy%2A>   
 <xref:System.Linq.Enumerable.ThenByDescending%2A>   
 [쿼리 키워드\(LINQ\)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [LINQ 쿼리 식](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [방법: 중첩 그룹 만들기](../../../csharp/programming-guide/linq-query-expressions/how-to-create-a-nested-group.md)   
 [방법: 쿼리 결과 그룹화](../../../csharp/programming-guide/linq-query-expressions/how-to-group-query-results.md)   
 [방법: 그룹화 작업에서 하위 쿼리 수행](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-a-subquery-on-a-grouping-operation.md)