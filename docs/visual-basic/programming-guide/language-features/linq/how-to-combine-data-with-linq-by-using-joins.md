---
title: "How to: Combine Data with LINQ by Using Joins (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "queries [LINQ in Visual Basic], joins"
  - "joins [LINQ in Visual Basic]"
  - "Join clause [LINQ in Visual Basic]"
  - "Group Join clause [Visual Basic]"
  - "joining [LINQ in Visual Basic]"
  - "queries [LINQ in Visual Basic], how-to topics"
ms.assetid: 5b00a478-035b-41c6-8918-be1a97728396
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# How to: Combine Data with LINQ by Using Joins (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Visual Basic에서는 컬렉션 간의 공통 값을 기준으로 여러 컬렉션의 내용을 결합할 수 있는 `Join` 및 `Group Join` 쿼리 절을 제공합니다.  이러한 값을 *키* 값이라고 합니다.  관계형 데이터베이스 개념에 익숙한 개발자는 `Join` 절을 INNER JOIN으로, `Group Join` 절을 사실상 LEFT OUTER JOIN으로 인식합니다.  
  
 이 항목의 예제에서는 `Join` 및 `Group Join` 쿼리 절을 사용하여 데이터를 결합하는 몇 가지 방법을 보여 줍니다.  
  
## 프로젝트 만들기 및 샘플 데이터 추가  
  
#### 샘플 데이터 및 형식이 포함된 프로젝트를 만들려면  
  
1.  이 항목의 샘플을 실행하려면 Visual Studio를 열고 새 Visual Basic 콘솔 응용 프로그램 프로젝트를 추가합니다.  Visual Basic에서 만든 Module1.vb 파일을 두 번 클릭합니다.  
  
2.  이 항목의 샘플은 `Person` 및 `Pet` 형식과 다음 코드 예제의 데이터를 사용합니다.  Visual Basic에서 만든 `Module1` 모듈에 이 코드를 복사합니다.  
  
     [!code-vb[VbLINQHowTos#1](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/visualbasic/VbLINQHowTos/Module1.vb#1)]  
    [!code-vb[VbLINQHowTos#2](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/visualbasic/VbLINQHowTos/Module1.vb#2)]  
  
## Join 절을 사용하여 내부 조인 수행  
 INNER JOIN은 두 컬렉션의 데이터를 결합합니다.  지정된 키 값이 일치하는 항목이 포함됩니다.  어느 한 컬렉션에 일치하는 항목이 없는 다른 쪽 컬렉션의 항목은 제외됩니다.  
  
 Visual Basic에서 LINQ는 INNER JOIN을 수행하는 두 가지 옵션인 암시적 조인과 명시적 조인을 제공합니다.  
  
 암시적 조인은 컬렉션이 `From` 절에서 조인되도록 지정하고 `Where` 절에서 일치하는 키 필드를 식별합니다.  Visual Basic은 지정된 키 필드를 기준으로 두 컬렉션을 암시적으로 조인합니다.  
  
 조인에 어떤 키 필드를 사용할 것인지 보다 구체적으로 지정하려는 경우 `Join` 절을 사용하여 명시적 조인을 지정할 수 있습니다.  이 경우에도 `Where` 절을 사용하여 쿼리 결과를 필터링할 수 있습니다.  
  
#### Join 절을 사용하여 내부 조인을 수행하려면  
  
1.  다음 코드를 사용자 프로젝트의 `Module1` 모듈에 추가하여 암시적 내부 조인과 명시적 내부 조인의 예를 살펴 보십시오.  
  
     [!code-vb[VbLINQHowTos#4](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/visualbasic/VbLINQHowTos/Module1.vb#4)]  
  
## Group Join 절을 사용하여 왼쪽 우선 외부 조인 수행  
 LEFT OUTER JOIN에는 조인의 왼쪽 컬렉션의 항목은 모두 포함하고 오른쪽 컬렉션의 값 중에서는 일치하는 값만 포함합니다.  조인의 왼쪽 컬렉션에 일치하는 항목이 없는 오른쪽 컬렉션의 항목은 쿼리 결과에서 제외됩니다.  
  
 `Group Join` 절은 사실상 LEFT OUTER JOIN을 수행합니다.  일반적으로 LEFT OUTER JOIN으로 알려져 있는 것과 `Group Join` 절이 반환하는 것의 차이점은 `Group Join` 절은 왼쪽 컬렉션의 각 항목에 대해 조인의 오른쪽 컬렉션의 결과를 그룹화한다는 점입니다.  관계형 데이터베이스에서 LEFT OUTER JOIN은 쿼리 결과의 각 항목에 조인의 두 컬렉션의 일치 항목이 모두 들어 있는 그룹화되지 않은 결과를 반환합니다.  이 경우 조인의 왼쪽 컬렉션의 항목은 오른쪽 컬렉션의 각 일치 항목에 대해 반복됩니다.  다음 절차를 수행하면 이 내용을 확인할 수 있습니다.  
  
 사용자 쿼리를 그룹화된 각 쿼리 결과에 대한 항목을 반환하도록 확장하여 `Group Join` 쿼리 결과를 그룹화되지 않은 결과로 검색할 수 있습니다.  이를 위해서는 그룹화된 컬렉션의 `DefaultIfEmpty` 메서드에 대해 쿼리해야 합니다.  그렇게 해야 조인의 왼쪽 컬렉션 항목이 오른쪽 컬렉션에 일치하는 결과가 없어도 쿼리 결과에 포함됩니다.  조인의 오른쪽 컬렉션에 일치하는 값이 없을 경우 기본 결과 값을 제공하도록 쿼리에 코드를 추가할 수 있습니다.  
  
#### Group Join 절을 사용하여 왼쪽 우선 외부 조인을 수행하려면  
  
1.  다음 코드를 사용자 프로젝트의 `Module1` 모듈에 추가하여 그룹화된 왼쪽 우선 외부 조인 및 그룹화되지 않은 왼쪽 우선 외부 조인의 예를 살펴 보십시오.  
  
     [!code-vb[VbLINQHowTos#3](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/visualbasic/VbLINQHowTos/Module1.vb#3)]  
  
## 복합 키를 사용하여 조인 수행  
 `Join` 또는 `Group Join` 절에 `And` 키워드를 사용하여 컬렉션의 일치하는 값이 조인될 때 사용할 여러 개의 키 필드를 식별할 수 있습니다.  `And` 키워드는 모든 지정된 키 필드가 조인될 항목에 대해 일치해야 함을 지정합니다.  
  
#### 복합 키를 사용하여 조인을 수행하려면  
  
1.  다음 코드를 사용자 프로젝트의 `Module1` 모듈에 추가하여 복합 키를 사용하는 조인의 예를 살펴 보십시오.  
  
     [!code-vb[VbLINQHowTos#5](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/visualbasic/VbLINQHowTos/Module1.vb#5)]  
  
## 코드 실행  
  
#### 코드를 추가하여 예제를 실행하려면  
  
1.  프로젝트에 있는 `Module1` 모듈의 `Sub Main`을 다음 코드로 대체하여 이 항목의 예제를 실행합니다.  
  
     [!code-vb[VbLINQHowTos#6](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/visualbasic/VbLINQHowTos/Module1.vb#6)]  
  
2.  F5 키를 눌러 예제를 실행합니다.  
  
## 참고 항목  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Join Clause](../../../../visual-basic/language-reference/queries/join-clause.md)   
 [Group Join Clause](../../../../visual-basic/language-reference/queries/group-join-clause.md)   
 [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md)   
 [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md)   
 [Queries](../../../../visual-basic/language-reference/queries/queries.md)   
 [LINQ를 통한 데이터 변환\(C\#\)](../../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md)