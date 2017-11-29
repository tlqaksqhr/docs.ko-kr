---
title: "기본 쿼리 작업(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data sources [LINQ in Visual Basic]
- Join clause [LINQ in Visual Basic]
- ordering data [LINQ in Visual Basic]
- projections [LINQ in Visual Basic]
- LINQ [Visual Basic], query operations
- Order By clause [LINQ in Visual Basic]
- joining data [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], basic operations
- selecting data [LINQ in Visual Basic]
- Group By clause [LINQ in Visual Basic]
- grouping data [LINQ in Visual Basic]
- Select clause [LINQ in Visual Basic]
ms.assetid: 1146f6d0-fcb8-4f4d-8223-c9db52620d21
caps.latest.revision: "37"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 794d77a18b50cc1667fddbad17c46735ae91be26
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="basic-query-operations-visual-basic"></a>기본 쿼리 작업(Visual Basic)
이 항목에서는에 대 한 간략 한 소개 [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] Visual Basic을 쿼리에서 수행 하는 작업의 일반적인 종류의 일부에 대 한 식입니다. 자세한 내용은 다음 항목을 참조하세요.  
  
 [Visual Basic의 LINQ 소개](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
  
 [쿼리](../../../../visual-basic/language-reference/queries/queries.md)  
  
 [연습: Visual Basic에서 쿼리 작성](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a>데이터 원본 (원본)를 지정합니다.  
 에 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리는 첫 번째 단계는 쿼리 하려는 데이터 원본을 지정할 수 있습니다. 따라서는 `From` 쿼리의 절에에서는 항상 먼저 발생 합니다. 쿼리 연산자는 선택 하 고 소스의 형식에 따라 결과 모양을 합니다.  
  
 [!code-vb[VbLINQBasicOps#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_1.vb)]  
  
 `From` 절에는 데이터 원본을 지정 합니다. `customers`, 및 *범위 변수*, `cust`합니다. 쿼리 식에서 실제 반복이 발생 하지 한다는 점을 제외 하 고 범위 변수는 루프 반복 변수는 같습니다. 쿼리가 실행 될 때, 자주 사용 하 여 한 `For Each` 루프의 각 연속 요소에 대 한 참조로 사용 범위 변수 `customers`합니다. 컴파일러에서 `cust` 형식을 유추할 수 있으므로 명시적으로 지정할 필요가 없습니다. 가 있거나 없는 명시적인 입력을 작성 하는 쿼리의 예 참조 [쿼리 작업 (Visual Basic)의 형식 관계](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md)합니다.  
  
 사용 하는 방법에 대 한 자세한 내용은 `From` 절 Visual basic에서 참조 [From 절이](../../../../visual-basic/language-reference/queries/from-clause.md)합니다.  
  
## <a name="filtering-data-where"></a>데이터 필터링 (위치)  
 아마도 가장 일반적인 쿼리 작업 하는 부울 식 형태로 필터를 적용 하는 합니다. 다음 쿼리 식이 true 인 요소에만 반환 합니다. A `Where` 절을 사용 하 여 필터링을 수행 하 합니다. 필터 결과 시퀀스에 포함할 데이터 원본에 있는 요소를 지정 합니다. 다음 예제에서는 주소 런던에 살고 있는 고객만 포함 됩니다.  
  
 [!code-vb[VbLINQBasicOps#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_2.vb)]  
  
 와 같은 논리 연산자를 사용할 수 `And` 및 `Or` 에서 필터 식을 결합 하는 `Where` 절. 예를 들어 고객에 대해서만 Devon 이름이 고 런던에서는 반환 하려면 다음 코드를 사용 합니다.  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"   
```  
  
 런던 또는 파리에서 고객을 반환 하려면 다음 코드를 사용 합니다.  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"   
```  
  
 사용 하는 방법에 대 한 자세한 내용은 `Where` 절 Visual basic에서 참조 [Where 절](../../../../visual-basic/language-reference/queries/where-clause.md)합니다.  
  
## <a name="ordering-data-order-by"></a>(Order By) 데이터 정렬  
 자주 하는 것을 특정 순서로 반환 되는 데이터 정렬입니다. `Order By` 절에서 지정된 된 필드 또는 필드 정렬할 반환된 된 시퀀스의 요소를 발생 합니다. 예를 들어 다음 쿼리는 정렬 기준으로 결과 `Name` 속성입니다. 때문에 `Name` 문자열인 경우 A에서 Z까지 반환된 된 데이터를 사전순으로 정렬 됩니다.  
  
 [!code-vb[VbLINQBasicOps#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_3.vb)]  
  
 결과를 역순으로 정렬하려면 `Order By...Descending` 절을 사용합니다. 기본값은 `Ascending` 하지 않은 경우 `Ascending` 나 `Descending` 지정 됩니다.  
  
 사용 하는 방법에 대 한 자세한 내용은 `Order By` 절 Visual basic에서 참조 [Order By 절](../../../../visual-basic/language-reference/queries/order-by-clause.md)합니다.  
  
## <a name="selecting-data-select"></a>(선택) 데이터 선택  
 `Select` 절 형식과 반환 된 요소의 콘텐츠를 지정 합니다. 결과의 전체으로 구성할 것인지를 지정할 수는 예를 들어 `Customer` 개체를 하나만 `Customer` 계산에 따라 속성, 속성 하위 집합, 다양 한 데이터 원본 또는 몇 가지 새로운 결과 형식에서 속성을 결합 합니다. `Select` 절이 소스 요소의 복사본이 아닌 다른 항목을 생성하는 경우 이 작업을 *프로젝션*이라고 합니다.  
  
 전체로 구성 된 컬렉션을 검색 하려면 `Customer` 개체 자체 범위 변수를 선택 합니다.  
  
 [!code-vb[VbLINQBasicOps#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_4.vb)]  
  
 경우는 `Customer` 인스턴스는 많은 필드를 가진 대형 개체 하 고 검색 하려는 모든 이름이 고, 선택할 수 있습니다 `cust.Name`다음 예제에 나온 것 처럼 합니다. 지역 형식 유추의 컬렉션에서이 결과 유형을 변경 인식 `Customer` 개체를 문자열 컬렉션입니다.  
  
 [!code-vb[VbLINQBasicOps#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_5.vb)]  
  
 데이터 원본에서 여러 필드를 선택 하는 두 가지 옵션이 있습니다.  
  
-   에 `Select` 절의 결과에 포함할 필드를 지정 합니다. 컴파일러에 해당 필드가 속성으로 익명 형식을 정의 합니다. 자세한 내용은 [무명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)을 참조하세요.  
  
     다음 예에서 반환 되는 요소는 익명 형식의 인스턴스 이기 때문에 참조할 수 없습니다 형식 이름으로 다른 곳에서 사용자 코드에서 합니다. 컴파일러에서 지정 된 이름 형식에 대 한 일반 Visual Basic 코드에서 유효 하지 않은 문자가 있습니다. 다음 예제에서는의 쿼리에 의해 반환 되는 컬렉션의 요소에서에서 `londonCusts4` 익명 형식의 인스턴스인  
  
     [!code-vb[VbLINQBasicOps#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_6.vb)]  
  
     또는  
  
-   명명 된 유형을 정의 하는 결과에 포함 하 고 만들고에서 형식의 인스턴스를 초기화 하 고 원하는 특정 필드가 `Select` 절. 반환 되는 컬렉션 외부 개별 결과 사용 해야 하는 경우에 또는 메서드 호출에 매개 변수로 전달 해야 할 경우이 옵션을 사용 합니다. 유형의 `londonCusts5` 다음 예제는 IEnumerable (Of NamePhone).  
  
     [!code-vb[VbLINQBasicOps#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_7.vb)]  
  
     [!code-vb[VbLINQBasicOps#8](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_8.vb)]  
  
 사용 하는 방법에 대 한 자세한 내용은 `Select` 절 Visual basic에서 참조 [Select 절](../../../../visual-basic/language-reference/queries/select-clause.md)합니다.  
  
## <a name="joining-data-join-and-group-join"></a>조인 데이터 (조인 및 그룹 조인)  
 둘 이상의 데이터 원본에 결합할 수는 `From` 여러 가지 방법으로 절. 예를 들어 다음 코드는 두 개의 데이터 원본이 사용 하 고 암시적으로 결과에서 둘 모두에서 속성을 결합 합니다. 쿼리는 마지막 이름이 함께 시작 하는 학생은 선택 합니다.  
  
 [!code-vb[VbLINQBasicOps#9](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_9.vb)]  
  
> [!NOTE]
>  만든 학생의 목록으로이 코드를 실행할 수 [하는 방법: 항목 목록 만들기](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)합니다.  
  
 `Join` 키워드는 해당 하는 `INNER JOIN` sql에서 합니다. 두 컬렉션의 요소 간에 일치 하는 키 값을 기반으로 하는 두 컬렉션을 결합 합니다. 쿼리 키 값이 일치 하는 컬렉션 요소를의 전체 또는 일부를 반환 합니다. 예를 들어 다음 코드는 이전 암시적 조인과의 동작을 복제합니다.  
  
 [!code-vb[VbLINQBasicOps#10](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_10.vb)]  
  
 `Group Join`마찬가지로 컬렉션을 단일 계층 구조 컬렉션으로 결합 한 `LEFT JOIN` sql에서 합니다. 자세한 내용은 참조 [Join 절](../../../../visual-basic/language-reference/queries/join-clause.md) 및 [Group Join 절](../../../../visual-basic/language-reference/queries/group-join-clause.md)합니다.  
  
## <a name="grouping-data-group-by"></a>데이터 그룹화 (Group By)  
 추가할 수는 `Group By` 요소 중 하나 이상의 필드에 따라 쿼리 결과의 요소를 그룹화 하는 절. 예를 들어 다음 코드는 클래스 연도별 학생 들을 그룹화합니다.  
  
 [!code-vb[VbLINQBasicOps#11](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_11.vb)]  
  
 만든 학생의 목록을 사용 하 여이 코드를 실행 하는 경우 [하는 방법: 항목 목록 만들기](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)의 출력은 `For Each` 문이:  
  
 연도: Junior  
  
 Tucker, Michael  
  
 Garcia, Hugo  
  
 Garcia, Debra  
  
 Tucker, 창  
  
 연도: 수석  
  
 Omelchenko, Svetlana  
  
 홍현아라, Michiko  
  
 Fakhouri, Fadi  
  
 Hanying Feng,  
  
 Terry Adams,  
  
 연도: 대학 1 학년  
  
 Mortensen, Sven  
  
 Garcia을 경우  
  
 다음 코드에 표시 된 변형 클래스 년을 정렬 한 다음 성을 기준으로 각 연도 내에서 학습자를 정렬 합니다.  
  
 [!code-vb[VbLINQBasicOps#12](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_12.vb)]  
  
 에 대 한 자세한 내용은 `Group By`, 참조 [그룹 By 절](../../../../visual-basic/language-reference/queries/group-by-clause.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Collections.Generic.IEnumerable%601>  
 [Visual Basic에서 LINQ 시작](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [쿼리](../../../../visual-basic/language-reference/queries/queries.md)  
 [표준 쿼리 연산자 개요(Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
