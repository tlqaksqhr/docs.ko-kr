---
title: "기본 쿼리 작업(Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "데이터 원본[Visual Basic의 LINQ]"
  - "Join 절[Visual Basic의 LINQ]"
  - "데이터 정렬[Visual Basic의 LINQ]"
  - "프로젝션[Visual Basic의 LINQ]"
  - "LINQ[Visual Basic], 쿼리 작업"
  - "Order By 절[Visual Basic의 LINQ]"
  - "데이터 조인[Visual Basic의 LINQ]"
  - "쿼리[Visual Basic의 LINQ], 기본 작업"
  - "데이터 선택[Visual Basic의 LINQ]"
  - "Group By 절[Visual Basic의 LINQ]"
  - "데이터 그룹화[Visual Basic의 LINQ]"
  - "Select 절[Visual Basic의 LINQ]"
ms.assetid: 1146f6d0-fcb8-4f4d-8223-c9db52620d21
caps.latest.revision: 37
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 35
---
# 기본 쿼리 작업(Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 항목에서는 Visual Basic의 [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext-md.md)] 식과 쿼리에서 수행하는 몇 가지 일반적인 작업 종류에 대해 간단히 소개합니다.  자세한 내용은 다음 항목을 참조하십시오.  
  
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
  
 [Queries](../../../../visual-basic/language-reference/queries/queries.md)  
  
 [연습: Visual Basic에서 쿼리 작성](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## 데이터 소스\(From\) 지정  
 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] 쿼리에서 첫 단계는 쿼리할 데이터 소스를 지정하는 것입니다.  따라서의 `From` 쿼리 절의 항상 첫 번째 제공 합니다. 쿼리 연산자는 선택 하 고 셰이프의 원본 형식에 따라 결과.  
  
 [!code-vb[VbLINQBasicOps#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/basic-query-operations_1.vb)]  
  
 `From` 절은 데이터 소스 `customers` 및 *범위 변수* `cust`를 지정합니다.  범위 변수는 쿼리 식에서 실제 반복이 발생하지 않는다는 점만 제외하고 루프 반복 변수와 유사합니다.  대체로 `For Each` 루프를 사용하여 쿼리를 실행할 때 범위 변수는 `customers`의 각 연속 요소에 대한 참조 역할을 합니다.  컴파일러는 `cust`의 형식을 추론할 수 있기 때문에 명시적으로 지정할 필요가 없습니다.  명시적 형식화를 사용하거나 사용하지 않고 작성된 쿼리의 예제를 보려면 [Type Relationships in Query Operations \(Visual Basic\)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md)를 참조하십시오.  
  
 Visual Basic의 `From` 절을 사용하는 방법에 대한 자세한 내용은 [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md)을 참조하십시오.  
  
## 데이터 필터링\(Where\)  
 아마도 가장 일반적인 쿼리 작업은 부울 식의 형식으로 필터를 적용하는 것입니다.  그러면 식이 true인 요소만 쿼리에서 반환됩니다.  `Where` 절은 필터링을 수행하는 데 사용됩니다.  필터는 결과 시퀀스에 포함할 데이터 소스의 요소를 지정합니다.  다음 예제에서는 London에 주소가 있는 고객만 포함됩니다.  
  
 [!code-vb[VbLINQBasicOps#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/basic-query-operations_2.vb)]  
  
 `And` 및 `Or` 같은 논리 연산자를 사용하여 `Where` 절에서 필터 식을 결합할 수 있습니다.  예를 들어 London의 고객 중에 이름이 Devon인 고객만 반환하려면 다음 코드를 사용합니다.  
  
```vb#  
Where cust.City = "London" And cust.Name = "Devon"   
```  
  
 London 또는 Paris의 고객을 반환하려면 다음 코드를 사용합니다.  
  
```vb#  
Where cust.City = "London" Or cust.City = "Paris"   
```  
  
 Visual Basic의 `Where` 절을 사용하는 방법에 대한 자세한 내용은 [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md)을 참조하십시오.  
  
## 데이터 정렬\(Order By\)  
 반환된 데이터를 특정 순서로 정렬하는 것이 편리한 경우가 많습니다.  `Order By` 절을 사용하면 반환된 시퀀스의 요소가 지정한 필드를 기준으로 정렬됩니다.  예를 들어 다음 쿼리는 `Name` 속성을 기준으로 결과를 정렬합니다.  `Name`은 문자열이므로 반환된 데이터가 A에서 Z까지 사전순으로 정렬됩니다.  
  
 [!code-vb[VbLINQBasicOps#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/basic-query-operations_3.vb)]  
  
 Z에서 A까지 역순으로 결과를 정렬하려면 `Order By...Descending` 절을 사용합니다.  `Ascending` 또는 `Descending`을 지정하지 않은 경우 기본값은 `Ascending`입니다.  
  
 Visual Basic의 `Order By` 절을 사용하는 방법에 대한 자세한 내용은 [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md)을 참조하십시오.  
  
## 데이터 선택\(Select\)  
 `Select` 절은 반환된 요소의 형식과 내용을 지정합니다.  예를 들어 결과를 전체 `Customer` 개체, 하나의 `Customer` 속성, 속성의 하위 집합, 여러 데이터 소스의 속성 조합, 계산 결과에 따른 새로운 형식 중 어느 것으로 구성할 것인지 지정할 수 있습니다.  `Select` 절이 소스 요소의 복사본 이외의 다른 내용을 생성하는 경우 해당 작업을 *프로젝션*이라고 합니다.  
  
 전체 `Customer` 개체로 구성된 컬렉션을 검색하려면 범위 변수 자체를 선택합니다.  
  
 [!code-vb[VbLINQBasicOps#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/basic-query-operations_4.vb)]  
  
 `Customer` 인스턴스가 많은 필드를 가진 대형 개체이고 이름만 검색하려는 경우 다음 예제와 같이 `cust.Name`을 선택할 수 있습니다.  지역 형식 유추는 이로 인해 결과 형식이 `Customer` 개체 컬렉션에서 문자열 컬렉션으로 변경됨을 인식합니다.  
  
 [!code-vb[VbLINQBasicOps#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/basic-query-operations_5.vb)]  
  
 데이터 소스에서 여러 필드를 선택하려는 경우 다음 두 가지 선택 사항이 있습니다.  
  
-   `Select` 절에서 결과에 포함할 필드를 지정합니다.  컴파일러는 해당 필드가 속성으로 포함된 익명 형식을 정의합니다.  자세한 내용은 [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)을 참조하십시오.  
  
     다음 예제에서 반환된 요소는 익명 형식의 인스턴스이므로 코드의 다른 위치에서 이 형식을 이름으로 참조할 수 없습니다.  컴파일러에서 지정된 형식 이름은 일반 Visual Basic 코드에서 유효하지 않은 문자를 포함합니다.  다음 예제에서 쿼리에 의해 `londonCusts4`에 반환된 컬렉션의 요소는 익명 형식의 인스턴스입니다.  
  
     [!code-vb[VbLINQBasicOps#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/basic-query-operations_6.vb)]  
  
     또는  
  
-   결과에 포함할 특정 필드가 있는 명명된 형식을 정의한 다음 `Select` 절에서 해당 형식의 인스턴스를 만들고 초기화합니다.  반환되는 컬렉션 외부에서 개별 결과를 사용해야 하는 경우 또는 메서드 호출에서 개별 결과를 매개 변수로 전달해야 하는 경우에만 이 옵션을 사용합니다.  다음 예제에서 `londonCusts5`의 형식은 IEnumerable\(Of NamePhone\)입니다.  
  
     [!code-vb[VbLINQBasicOps#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/basic-query-operations_7.vb)]  
  
     [!code-vb[VbLINQBasicOps#8](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/basic-query-operations_8.vb)]  
  
 Visual Basic의 `Select` 절을 사용하는 방법에 대한 자세한 내용은 [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md)을 참조하십시오.  
  
## 데이터 조인\(Join 및 Group Join\)  
 `From` 절에서 둘 이상의 데이터 소스를 여러 방식으로 결합할 수 있습니다.  예를 들어 다음 코드에서는 두 개의 데이터 소스를 사용하고 결과에서 두 데이터 소스의 속성을 암시적으로 결합합니다.  쿼리는 성이 모음으로 시작하는 학생을 선택합니다.  
  
 [!code-vb[VbLINQBasicOps#9](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/basic-query-operations_9.vb)]  
  
> [!NOTE]
>  [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)에서 만든 학생 목록을 사용하여 이 코드를 실행할 수 있습니다.  
  
 `Join` 키워드는 SQL의 `INNER JOIN`과 같습니다.  두 컬렉션의 요소 간에 일치하는 키 값을 기준으로 두 컬렉션을 결합합니다.  쿼리는 일치하는 키 값이 있는 컬렉션 요소를 모두 또는 일부만 반환합니다.  예를 들어 다음 코드는 이전 암시적 조인과 동일한 동작을 수행합니다.  
  
 [!code-vb[VbLINQBasicOps#10](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/basic-query-operations_10.vb)]  
  
 `Group Join`은 SQL의 `LEFT JOIN`과 마찬가지로 컬렉션을 하나의 계층적 컬렉션으로 결합합니다.  자세한 내용은 [Join Clause](../../../../visual-basic/language-reference/queries/join-clause.md) 및 [Group Join Clause](../../../../visual-basic/language-reference/queries/group-join-clause.md)을 참조하십시오.  
  
## 데이터 그룹화\(Group By\)  
 `Group By` 절을 추가하여 요소의 하나 이상 필드에 따라 쿼리 결과의 요소를 그룹화할 수 있습니다.  예를 들어 다음 코드에서는 학년별로 학생을 그룹화합니다.  
  
 [!code-vb[VbLINQBasicOps#11](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/basic-query-operations_11.vb)]  
  
 [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)에서 만든 학생 목록을 사용하여 이 코드를 실행하는 경우 `For Each` 문의 출력은 다음과 같습니다.  
  
 Year: Junior  
  
 Tucker, Michael  
  
 Garcia, Hugo  
  
 Garcia, Debra  
  
 Tucker, Lance  
  
 Year: Senior  
  
 Omelchenko, Svetlana  
  
 Osada, Michiko  
  
 Fakhouri, Fadi  
  
 Feng, Hanying  
  
 Adams, Terry  
  
 Year: Freshman  
  
 Mortensen, Sven  
  
 Garcia, Cesar  
  
 다음 코드와 같이 변형하면 학년별로 정렬된 다음 각 학년의 학생이 성별로 정렬됩니다.  
  
 [!code-vb[VbLINQBasicOps#12](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/basic-query-operations_12.vb)]  
  
 `Group By`에 대한 자세한 내용은 [Group By 절](../../../../visual-basic/language-reference/queries/group-by-clause.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Collections.Generic.IEnumerable%601>   
 [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [Queries](../../../../visual-basic/language-reference/queries/queries.md)   
 [Standard Query Operators Overview](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Basic LINQ Query Operations](../../../../csharp/programming-guide/concepts/linq/basic-linq-query-operations.md)