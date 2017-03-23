---
title: "Query Syntax and Method Syntax in LINQ (C#) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "LINQ [C#], query syntax vs. method syntax"
  - "queries [LINQ in C#], syntax comparisons"
ms.assetid: eedd6dd9-fec2-428c-9581-5b8783810ded
caps.latest.revision: 30
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 28
---
# Query Syntax and Method Syntax in LINQ (C#)
대부분의 쿼리에서 소개 언어 통합 쿼리 \([!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)]\) LINQ의 선언적 쿼리 구문을 사용 하 여 문서를 작성 합니다.  그러나 코드를 컴파일할 때 쿼리 구문이.NET 공용 언어 런타임 \(CLR\)에 대 한 메서드 호출으로 변환 합니다.  이러한 메서드 호출은 같은 이름을 사용 하는 표준 쿼리 연산자 `Where`, `Select`, `GroupBy`, `Join`, `Max`, 및 `Average`.  쿼리 구문 대신 메서드 구문을 직접 사용 하 여 기부할 수 있습니다.  
  
 쿼리 구문과 메서드 구문의 의미적으로 동일 하지만 쿼리 구문을 간단 하 고 쉽게 읽을 수 많은 사람들이 찾기.  일부 쿼리 메서드 호출으로 표현 해야 합니다.  예를 들어, 숫자의 지정 된 조건과 일치 하는 요소를 검색 하는 쿼리를 표현할 수 메서드 호출을 사용 해야 합니다.  또한 소스 시퀀스에서 최대 값을 가진 요소를 검색 하는 쿼리에 대 한 메서드 호출을 사용 해야 합니다.  <xref:System.Linq> 네임스페이스의 표준 쿼리 연산자에 대한 참조 설명서에서는 일반적으로 메서드 구문이 사용됩니다.  따라서 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] 쿼리를 작성하기 시작한 경우에도 쿼리 및 쿼리 식 자체에서 메서드 구문을 사용하는 방법에 익숙하면 도움이 됩니다.  
  
## 표준 쿼리 연산자 확장 메서드  
 다음 예제에서는 간단한 *쿼리 식* 및 *메서드 기반 쿼리*로 작성된 의미가 같은 쿼리를 보여 줍니다.  
  
 [!code-cs[csLINQGettingStarted#22](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/query-syntax-and-method-syntax-in-linq_1.cs)]  
  
 두 예제의 출력은 동일합니다.  쿼리 변수의 형식이 두 경우 모두에서 <xref:System.Collections.Generic.IEnumerable%601>로 동일하다는 것을 알 수 있습니다.  
  
 메서드 기반 쿼리를 이해하기 위해 좀더 자세히 살펴보도록 하겠습니다.  식의 오른쪽에서 `where` 절은 이제 `numbers` 개체에 대한 인스턴스 메서드로 표현되며 해당 형식은 `IEnumerable<int>`입니다.  제네릭 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스에 익숙한 경우 `Where` 메서드가 없다는 것을 알고 있을 것입니다.  그러나 Visual Studio IDE에서 IntelliSense 완성 목록을 호출할 경우 `Where` 메서드뿐만 아니라 `Select`, `SelectMany`, `Join` 및 `Orderby`와 같은 다른 많은 메서드를 보게 됩니다.  이러한 메서드는 모두 표준 쿼리 연산자입니다.  
  
 ![Intellisense의 표준 쿼리 연산자](../../../../csharp/programming-guide/concepts/linq/media/standardqueryops.png "StandardQueryOps")  
  
 <xref:System.Collections.Generic.IEnumerable%601>이 이러한 추가 메서드를 포함하도록 다시 정의된 것처럼 보이지만 실제로는 그렇지 않습니다.  표준 쿼리 연산자는 *확장 메서드*라는 새로운 종류의 메서드로 구현됩니다.  확장 메서드는 기존 "형식"을 확장하므로 해당 형식에 대한 인스턴스 메서드인 것처럼 호출될 수 있습니다.  표준 쿼리 연산자가 <xref:System.Collections.Generic.IEnumerable%601>을 확장하기 때문에 사용자는 `numbers.Where(...)`를 작성할 수 있습니다.  
  
 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)]를 사용하려면 올바른 `using` 지시문을 사용하여 확장 메서드를 응용 프로그램의 범위에 가져오는 방법만 알면 됩니다.  이 방법은 [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md)에 자세히 설명되어 있습니다.  응용 프로그램의 관점에서 보면 확장 메서드와 일반 인스턴스 메서드는 동일합니다.  
  
 확장 메서드에 대한 자세한 내용은 [확장 메서드](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md)를 참조하십시오.  표준 쿼리 연산자에 대한 자세한 내용은 [Standard Query Operators Overview](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)를 참조하십시오.  [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq-md.md)] 및 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)]과 같은 일부 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] 공급자는 <xref:System.Collections.Generic.IEnumerable%601> 외의 다른 형식에 대한 고유한 표준 쿼리 연산자와 추가 확장 메서드를 구현합니다.  
  
## 람다 식  
 앞의 예제에서 표시 조건식 \(`num % 2 == 0`\) 인라인 인수로 서 전달 되는 `Where` 메서드: `Where(num => num % 2 == 0).` 이 인라인 식을 람다 식 이라고 합니다.  이 인라인 식은 코드를 작성하는 편리한 방법이며 이 방법이 없을 경우 익명 메서드나 제네릭 대리자 또는 식 트리와 같은 더 번거로운 형식으로 코드를 작성해야 합니다.  C\#에서 `=>`는 "goes to"를 나타내는 람다 연산자입니다.  이 연산자 왼쪽의 `num`은 쿼리 식의 `num`에 해당하는 입력 변수입니다.  컴파일러에서는 `numbers`가 제네릭 <xref:System.Collections.Generic.IEnumerable%601> 형식이라는 것을 알고 있으므로 `num`의 형식을 유추할 수 있습니다.  람다의 본문은 쿼리 구문이나 다른 모든 C\# 식 또는 문의 식과 동일하므로 메서드 호출과 기타 복잡한 논리를 포함할 수 있습니다.  "반환 값"은 식 결과입니다.  
  
 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)]를 사용하기 위해 람다를 광범위하게 사용할 필요는 없습니다.  그러나 특정 쿼리는 메서드 구문으로만 표현할 수 있으며 이러한 쿼리 중 일부에 람다 식이 필요합니다.  람다에 더 익숙해지고 나면 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] 도구 상자에서 람다가 강력하고 유연한 도구라는 것을 알 수 있습니다.  자세한 내용은 [람다 식](../../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)을 참조하십시오.  
  
## 쿼리의 작성 가능성  
 이전 코드 예제에서는 `Where` 호출에 점 연산자를 사용하여 `OrderBy` 메서드가 호출됩니다.  `Where`에서 필터링된 시퀀스를 생성한 후 `Orderby`가 적용되어 시퀀스를 정렬합니다.  쿼리가 `IEnumerable`을 반환하므로 사용자는 메서드 호출을 함께 연결하여 메서드 구문에서 쿼리를 작성합니다.  쿼리 구문을 사용하여 쿼리를 작성할 때는 컴파일러가 이 작업을 내부적으로 수행합니다.  또한 쿼리 변수가 쿼리 결과를 저장하지 않으므로 쿼리 변수가 실행된 이후라도 언제든지 쿼리 변수를 수정하거나 새 쿼리의 기초로 사용할 수 있습니다.  
  
## 참고 항목  
 [Getting Started with LINQ in C\#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)