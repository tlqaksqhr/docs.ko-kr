---
title: "Basic LINQ Query Operations (C#) | Microsoft Docs"
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
  - "orderby clause [LINQ in C#]"
  - "ordering data [LINQ in C#]"
  - "selecting data [LINQ in C#]"
  - "queries [LINQ in C#], basic operations"
  - "grouping data [LINQ in C#]"
  - "data sources [LINQ in C#]"
  - "sorting data [LINQ in C#]"
  - "projections [LINQ in C#]"
  - "filtering data [LINQ in C#]"
  - "joining data [LINQ in C#]"
  - "select clause [LINQ in C#]"
  - "LINQ [C#], basic query operations"
  - "join clause [LINQ in C#]"
  - "group clause [LINQ in C#]"
ms.assetid: a7ea3421-1cf4-4df7-832a-aa22fe6379e9
caps.latest.revision: 39
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 37
---
# Basic LINQ Query Operations (C#)
이 항목에서는 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] 쿼리 식에 대한 간단한 개요 및 쿼리에서 수행하는 일반적인 작업 종류를 몇 가지 제공합니다.  자세한 내용은 다음 항목을 참조하십시오.  
  
 [LINQ 쿼리 식](../../../../csharp/programming-guide/linq-query-expressions/index.md)  
  
 [Standard Query Operators Overview](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
  
 [Walkthrough: Writing Queries in C\#](../../../../csharp/programming-guide/concepts/linq/walkthrough-writing-queries-linq.md)  
  
> [!NOTE]
>  SQL 또는 XQuery와 같은 쿼리 언어에 이미 익숙한 경우 이 항목 중 대부분을 건너뛸 수 있습니다.  [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] 쿼리 식에서의 절 순서에 대한 자세한 내용은 다음 단원의 "`from` 절"을 참조하십시오.  
  
## 데이터 소스 가져오기  
 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] 쿼리에서 첫 번째 단계는 데이터 소스를 지정하는 것입니다.  대부분의 프로그래밍 언어와 마찬가지로 C\#에서는 변수를 사용하기 전에 선언해야 합니다.  [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] 쿼리에서 데이터 소스\(`customers`\) 및 *범위 변수*\(`cust`\)를 제공하려면 `from` 절이 먼저 와야 합니다.  
  
 [!code-cs[csLINQGettingStarted#23](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#23)]  
  
 범위 변수는 쿼리 식에서 실제 반복이 발생하지 않는다는 점만 제외하면 `foreach` 루프의 반복 변수와 유사합니다.  쿼리가 실행될 때 범위 변수는 `customers`의 각 연속 요소에 대한 참조 역할을 합니다.  컴파일러는 `cust`의 형식을 추론할 수 있기 때문에 명시적으로 지정할 필요가 없습니다.  `let` 절에서 추가 범위 변수를 제공할 수 있습니다.  자세한 내용은 [let 절](../../../../csharp/language-reference/keywords/let-clause.md)을 참조하십시오.  
  
> [!NOTE]
>  <xref:System.Collections.ArrayList>와 같은 제네릭이 아닌 데이터 소스의 경우 범위 변수를 명시적으로 형식화해야 합니다.  자세한 내용은 [How to: Query an ArrayList with LINQ](../Topic/How%20to:%20Query%20an%20ArrayList%20with%20LINQ.md) 및 [from 절](../../../../csharp/language-reference/keywords/from-clause.md)을 참조하십시오.  
  
## 필터링  
 아마도 가장 일반적인 쿼리 작업은 부울 식의 형식으로 필터를 적용하는 것입니다.  필터는 쿼리에서 식이 true인 요소만 반환하게 합니다.  결과는 `where` 절을 사용하여 생성됩니다.  적용된 필터는 소스 시퀀스에서 제외할 요소를 지정합니다.  다음 예제에서는 London에 주소가 있는 `customers`만 반환됩니다.  
  
 [!code-cs[csLINQGettingStarted#24](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#24)]  
  
 친근한 C\# 논리 `AND` 및 `OR` 연산자를 사용하여 `where` 절에 필요한 만큼의 필터 식을 적용할 수 있습니다.  예를 들어 "London"의 고객이면서 동시에\(`AND`\) 이름이 "Devon"인 고객만 반환하려면 다음 코드를 작성합니다.  
  
 [!code-cs[csLINQGettingStarted#25](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#25)]  
  
 London 또는 Paris에서 고객을 반환하려면 다음 코드를 작성합니다.  
  
 [!code-cs[csLINQGettingStarted#26](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#26)]  
  
 자세한 내용은 [where 절](../../../../csharp/language-reference/keywords/where-clause.md)을 참조하십시오.  
  
## 정렬  
 반환된 데이터를 정렬하는 것이 편리한 경우가 많습니다.  `orderby` 절은 반환된 시퀀스의 요소가 정렬하고 있는 형식의 기본 비교자에 따라 정렬되게 합니다.  예를 들어 `Name` 속성을 기반으로 결과를 정렬하도록 다음 쿼리를 확장할 수 있습니다.  `Name`은 문자열이므로 기본 비교자는 A에서 Z로 사전순 정렬을 수행합니다.  
  
 [!code-cs[csLINQGettingStarted#27](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#27)]  
  
 역순인 Z에서 A로 결과를 정렬하려면 `orderby…descending` 절을 사용합니다.  
  
 자세한 내용은 [orderby 절](../../../../csharp/language-reference/keywords/orderby-clause.md)을 참조하십시오.  
  
## 그룹화  
 `group` 절을 사용하면 지정한 키에 따라 결과를 그룹화할 수 있습니다.  예를 들어 London이나 Paris의 모든 고객이 개별 그룹에 있도록 `City`를 기준으로 결과를 그룹화하도록 지정할 수 있습니다.  이 경우 `cust.City`가 키입니다.  
  
 [!code-cs[csLINQGettingStarted#28](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#28)]  
  
 쿼리를 `group` 절로 끝내면 결과에서 목록 형식을 사용합니다.  목록의 각 요소는 `Key` 멤버가 있는 개체나 해당 키로 그룹화된 요소의 목록입니다.  그룹 시퀀스를 생성하는 쿼리에 대해 반복하는 경우 중첩된 `foreach` 루프를 사용해야 합니다.  바깥쪽 루프는 각 그룹에 대해 반복하며 안쪽 루프는 각 그룹의 멤버에 대해 반복합니다.  
  
 그룹 작업의 결과를 참조해야 하는 경우 `into` 키워드를 사용하여 계속 쿼리할 수 있는 식별자를 만들어야 합니다.  다음 쿼리는 세 명 이상의 고객을 포함하는 그룹만 반환합니다.  
  
 [!code-cs[csLINQGettingStarted#29](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#29)]  
  
 자세한 내용은 [group 절](../../../../csharp/language-reference/keywords/group-clause.md)을 참조하십시오.  
  
## 조인  
 조인 작업은 데이터 소스에서 명시적으로 모델링되지 않은 시퀀스 간 연결을 만듭니다.  예를 들어 조인을 수행하여 동일 위치에 있는 모든 고객과 배포자를 찾을 수 있습니다.  [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)]에서 `join` 절은 데이터베이스 테이블에 직접 작업하는 대신 항상 개체 컬렉션에 대해 작업합니다.  
  
 [!code-cs[csLINQGettingStarted#36](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#36)]  
  
 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)]의 외래 키는 항목의 컬렉션을 포함하는 속성으로 개체 모델에 나타나므로 SQL에서 일반적으로 사용하는 것처럼 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)]에서 `join`을 사용할 필요가 없습니다.  예를 들어 `Customer` 개체에는 `Order` 개체의 컬렉션이 포함됩니다.  조인을 수행하는 대신 점 표기를 사용하여 주문에 액세스합니다.  
  
```  
from order in Customer.Orders...  
```  
  
 자세한 내용은 [join 절](../../../../csharp/language-reference/keywords/join-clause.md)을 참조하십시오.  
  
## 선택\(프로젝션\)  
 `select` 절에서 쿼리 결과를 생성하고 각 반환된 요소의 "모양"이나 형식을 지정합니다.  예를 들어 계산 또는 새 개체 생성에 따라 결과를 전체 `Customer` 개체, 한 멤버만, 멤버의 하위 집합 또는 몇 가지 완전히 다른 결과 형식으로 구성할 것인지 여부를 지정할 수 있습니다.  `select` 절이 소스 요소의 복사본 이외의 다른 내용을 생성하는 경우 해당 작업을 *프로젝션*이라고 합니다.  데이터를 변환하는 프로젝션의 사용은 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] 쿼리 식의 강력한 기능입니다.  자세한 내용은 [LINQ를 통한 데이터 변환\(C\#\)](../../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md) 및 [select 절](../../../../csharp/language-reference/keywords/select-clause.md)을 참조하십시오.  
  
## 참고 항목  
 [Getting Started with LINQ in C\#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [LINQ 쿼리 식](../../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Walkthrough: Writing Queries in C\#](../../../../csharp/programming-guide/concepts/linq/walkthrough-writing-queries-linq.md)   
 [쿼리 키워드\(LINQ\)](../../../../csharp/language-reference/keywords/query-keywords.md)   
 [익명 형식](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [기본 쿼리 작업\(Visual Basic\)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md)