---
title: "기본 쿼리 작업 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
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
caps.latest.revision: 37
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 87ff9173b5ff72385c8ecdc3ff13735e7be2a21d
ms.lasthandoff: 03/13/2017

---
# <a name="basic-query-operations-visual-basic"></a>기본 쿼리 작업(Visual Basic)
이 항목에 대 한 간략 한 소개를 제공 합니다. [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] 식 Visual basic에서 및 쿼리에서 수행 하는 작업의 일반적인 종류의 일부입니다. 자세한 내용은 다음 항목을 참조하세요.  
  
 [Visual Basic의 LINQ 소개](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
  
 [쿼리](../../../../visual-basic/language-reference/queries/queries.md)  
  
 [연습: Visual Basic에서 쿼리 작성](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a>데이터 원본 (원본)를 지정합니다.  
 에 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 쿼리, 첫 번째 단계는 쿼리 하려는 데이터 소스를 지정 합니다. 따라서는 `From` 쿼리의 절에에서는 항상 먼저 발생 합니다. 쿼리 연산자는 선택 하 고 소스의 형식에 따라 결과 셰이프.  
  
 [!code-vb[VbLINQBasicOps #&1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_1.vb)]  
  
 `From` 데이터 소스를 지정 하는 절 `customers`, 및 *범위 변수*, `cust`합니다. 범위 변수는 루프 반복 변수를 제외 하 고 쿼리 식에서 실제 반복이 발생 하지. 쿼리가 실행 되 면 자주 사용 하 여 한 `For Each` 루프의 각 연속 요소에 대 한 참조 역할도 범위 변수 `customers`합니다. 컴파일러의 형식을 유추할 수 있기 때문에 `cust`를 명시적으로 지정할 필요가 없습니다. 명시적 형식 지정 하지 않고 작성 된 쿼리 예제를 보려면 참조 [쿼리 작업 (Visual Basic)의 형식 관계](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md)합니다.  
  
 사용 하는 방법에 대 한 자세한 내용은 `From` 절 Visual basic에서 참조 [From 절이](../../../../visual-basic/language-reference/queries/from-clause.md)합니다.  
  
## <a name="filtering-data-where"></a>데이터 필터링 (위치)  
 아마도 가장 일반적인 쿼리 작업 하는 부울 식 형태로 필터를 적용 합니다. 쿼리는 다음 식이 true 인 요소만 반환 합니다. A `Where` 절은 필터링을 수행 하는 데 사용 됩니다. 필터 결과 시퀀스에 포함할 데이터 원본에 있는 요소를 지정 합니다. 다음 예제에서는 London에 있는 주소를 가진 고객만 포함 됩니다.  
  
 [!code-vb[VbLINQBasicOps #&2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_2.vb)]  
  
 와 같은 논리 연산자를 사용할 수 `And` 및 `Or` 에서 필터 식을 결합 하는 `Where` 절. 예를 들어 Devon 이름이 고 london에서는 고객 에게만 반환 하려면 다음 코드를 사용 합니다.  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"   
```  
  
 런던 또는 파리에서 고객을 반환 하려면 다음 코드를 사용 합니다.  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"   
```  
  
 사용 하는 방법에 대 한 자세한 내용은 `Where` 절 Visual basic에서 참조 [Where 절](../../../../visual-basic/language-reference/queries/where-clause.md)합니다.  
  
## <a name="ordering-data-order-by"></a>(Order By) 데이터 정렬  
 것이 편리한 경우가 많습니다 반환 된 데이터를 특정 순서로 정렬 합니다. `Order By` 절 지정된 된 필드 또는 필드를 기준으로 정렬 됩니다 반환된 된 시퀀스의 요소를 발생 합니다. 예를 들어 다음 쿼리는 정렬 기준으로 결과 `Name` 속성입니다. 때문에 `Name` 문자열이 면 반환된 된 데이터는 A에서 Z까지 사전순으로 정렬 됩니다.  
  
 [!code-vb[VbLINQBasicOps #&3;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_3.vb)]  
  
 사용 하 여 Z에서 A로 결과 반대 순서로 정렬 된 `Order By...Descending` 절. 기본값은 `Ascending` 하지 않은 경우 `Ascending` 나 `Descending` 지정 됩니다.  
  
 사용 하는 방법에 대 한 자세한 내용은 `Order By` 절 Visual basic에서 참조 [Order By 절](../../../../visual-basic/language-reference/queries/order-by-clause.md)합니다.  
  
## <a name="selecting-data-select"></a>(선택) 데이터 선택  
 `Select` 절 형식과 반환 된 요소의 내용을 지정 합니다. 결과의 전체으로 구성할 것인지를 지정할 수는 예를 들어 `Customer` 개체를 하나만 `Customer` 속성, 속성의 하위 집합, 다양 한 데이터 원본 또는 몇 가지 새로운 결과 형식에서 속성의 조합을 기반으로 계산 합니다. 때는 `Select` 절을 생성 하는 소스 요소의 복사본 이외의 작업이 호출 되는 *프로젝션*합니다.  
  
 전체로 구성 된 컬렉션을 검색 하려면 `Customer` 개체를 자체 범위 변수를 선택 합니다.  
  
 [!code-vb[VbLINQBasicOps #&4;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_4.vb)]  
  
 하는 경우는 `Customer` 인스턴스는 많은 필드를 포함 하는 큰 개체 및 검색 하려는 모든 이름이 고, 선택할 수 있습니다 `cust.Name`다음 예제와 같이 합니다. 지역 형식 유추는이 형식을 변경 하는 결과의 컬렉션에서 인식 `Customer` 개체를 문자열의 컬렉션입니다.  
  
 [!code-vb[VbLINQBasicOps #&5;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_5.vb)]  
  
 데이터 원본에서 여러 필드를 선택 하는 두 가지 옵션이 있습니다.  
  
-   에 `Select` 절의 결과에 포함할 필드를 지정 합니다. 컴파일러는 해당 속성으로 해당 필드가 있는 익명 형식을 정의 합니다. 자세한 내용은 참조 [익명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)합니다.  
  
     다음 예에서 반환 되는 요소는 익명 형식의 인스턴스는 이기 때문에 참조할 수 없습니다 형식 이름으로 다른 곳에서 코드에서. 형식에 대해 컴파일러에서 지정 된 이름에 표준 Visual Basic 코드에서 유효 하지 않은 문자가 있습니다. 다음 예제에서는의 쿼리에 의해 반환 되는 컬렉션의 요소에서에서 `londonCusts4` 익명 형식의 인스턴스인  
  
     [!code-vb[VbLINQBasicOps #&6;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_6.vb)]  
  
     또는  
  
-   결과에 포함 하 고 만드는에서 형식의 인스턴스를 초기화 하려는 특정 필드를 포함 하는 명명 된 형식을 정의 `Select` 절. 반환 되는 컬렉션 외부 개별 결과 사용 해야 하는 경우에 또는 메서드 호출에 매개 변수로 전달 해야 할 경우이 옵션을 사용 합니다. 유형의 `londonCusts5` 다음 예제는 IEnumerable (Of NamePhone).  
  
     [!code-vb[VbLINQBasicOps #&7;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_7.vb)]  
  
     [!code-vb[VbLINQBasicOps #&8;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_8.vb)]  
  
 사용 하는 방법에 대 한 자세한 내용은 `Select` 절 Visual basic에서 참조 [Select 절](../../../../visual-basic/language-reference/queries/select-clause.md)합니다.  
  
## <a name="joining-data-join-and-group-join"></a>조인 데이터 (예: 조인 및 그룹 조인)  
 둘 이상의 데이터 원본에 결합할 수는 `From` 여러 가지 방법으로 절. 예를 들어 다음 코드는 두 개의 데이터 소스를 사용 하 여 하 고 암시적으로 고 결과 둘 다에서 속성을 결합 합니다. 쿼리는 성이 함께 시작 하는 학생을 선택 합니다.  
  
 [!code-vb[VbLINQBasicOps #&9;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_9.vb)]  
  
> [!NOTE]
>  만든 학생 목록을 사용 하 여이 코드를 실행할 수 있습니다 [하는 방법: 항목 목록 만들기](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)합니다.  
  
 `Join` 키워드는 해당 하는 `INNER JOIN` sql에서입니다. 두 컬렉션의 요소 간에 일치 하는 키 값을 기반으로 하는 두 개의 컬렉션을 결합 합니다. 쿼리는 전체 또는 일부 일치 하는 키 값이 있는 컬렉션 요소를 반환 합니다. 예를 들어 다음 코드는 이전 암시적 조인과의 동작을 복제합니다.  
  
 [!code-vb[VbLINQBasicOps #&10;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_10.vb)]  
  
 `Group Join`와 동일 하 게 컬렉션을 단일 계층적 컬렉션으로 결합 한 `LEFT JOIN` sql에서입니다. 자세한 내용은 참조 [Join 절](../../../../visual-basic/language-reference/queries/join-clause.md) 및 [Group Join 절](../../../../visual-basic/language-reference/queries/group-join-clause.md)합니다.  
  
## <a name="grouping-data-group-by"></a>데이터 그룹화 (Group By)  
 추가할 수는 `Group By` 요소 하나 이상의 필드에 따라 쿼리 결과의 요소를 그룹화 하는 절. 예를 들어 다음 코드는 학년으로 학생을 그룹화합니다.  
  
 [!code-vb[VbLINQBasicOps #&11;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_11.vb)]  
  
 만든 학생 목록을 사용 하 여이 코드를 실행 하는 경우 [하는 방법: 항목 목록 만들기](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)에서 출력은 `For Each` 문이:  
  
 연도: Junior  
  
 Tucker, Michael  
  
 Garcia, Hugo  
  
 Garcia, Debra  
  
 Tucker, Lance  
  
 연도: 수석  
  
 Omelchenko, Svetlana  
  
 홍현아라, Michiko  
  
 Fakhouri, Fadi  
  
 인, Hanying Feng  
  
 Terry Adams,  
  
 연도: 대학&1; 학년  
  
 Mortensen, Sven  
  
 Garcia를 경우  
  
 다음 코드에 나온 변형 클래스 년 순서 지정 하 고 성을 기준으로 각 연도 내에서 학생을 정렬 합니다.  
  
 [!code-vb[VbLINQBasicOps #&12;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_12.vb)]  
  
 에 대 한 자세한 내용은 `Group By`, 참조 [그룹 By 절](../../../../visual-basic/language-reference/queries/group-by-clause.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>   
 [Visual Basic에서 LINQ 시작](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [쿼리](../../../../visual-basic/language-reference/queries/queries.md)   
 [표준 쿼리 연산자 개요 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
