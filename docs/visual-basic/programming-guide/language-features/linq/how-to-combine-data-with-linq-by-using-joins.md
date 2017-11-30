---
title: "방법: 조인을 사용하여 데이터와 LINQ 결합(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- queries [LINQ in Visual Basic], joins
- joins [LINQ in Visual Basic]
- Join clause [LINQ in Visual Basic]
- Group Join clause [Visual Basic]
- joining [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 5b00a478-035b-41c6-8918-be1a97728396
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 432be646ce4353fd4627a34f363e7562f6181e92
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-combine-data-with-linq-by-using-joins-visual-basic"></a>방법: 조인을 사용하여 데이터와 LINQ 결합(Visual Basic)
Visual Basic에서 제공 된 `Join` 및 `Group Join` 쿼리 절을 사용 하면 컬렉션 간의 공통 값을 기반으로 하는 여러 컬렉션의 내용을 결합할 수 있습니다. 이러한 값 이라고 *키* 값입니다. 관계형 데이터베이스의 개념에 익숙한 개발자 인식 하는 `Join` 으로 INNER JOIN 절 및 `Group Join` 으로 효과적으로, LEFT OUTER JOIN 절.  
  
 이 항목의 예제를 사용 하 여 데이터를 결합 하는 몇 가지 방법을 보여 주기는 `Join` 및 `Group Join` 쿼리 절.  
  
## <a name="create-a-project-and-add-sample-data"></a>프로젝트를 만들고 샘플 데이터 추가  
  
#### <a name="to-create-a-project-that-contains-sample-data-and-types"></a>샘플 데이터 및 형식이 포함 된 프로젝트를 만들려면  
  
1.  이 항목의 예제를 실행 하려면 Visual Studio를 열고 새 Visual Basic 콘솔 응용 프로그램 프로젝트를 추가 합니다. Visual Basic에서 만든 Module1.vb 파일을 두 번 클릭 합니다.  
  
2.  이 항목 사용 샘플은 `Person` 및 `Pet` 유형 및 다음 코드 예제에서 데이터입니다. 이 코드는 기본 복사 `Module1` Visual Basic에서 만든 모듈입니다.  
  
     [!code-vb[VbLINQHowTos#1](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_1.vb)]  
    [!code-vb[VbLINQHowTos#2](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_2.vb)]  
  
## <a name="perform-an-inner-join-by-using-the-join-clause"></a>Join 절을 사용 하 여 내부 조인을 수행합니다  
 INNER JOIN 두 컬렉션에서 데이터를 결합합니다. 지정된 된 키 값과 일치 하는 항목이 포함 됩니다. 컬렉션 중 하나에서 다른 컬렉션에 일치 하는 항목이 없는 모든 항목은 제외 됩니다.  
  
 Visual Basic의 LINQ 제공 내부 조인을 수행 하기 위한 두 가지 옵션: 암시적 조인 및 명시적 조인을 합니다.  
  
 암시적 조인을 지정은 컬렉션 조인할 수는 `From` 절에 일치 하는 키 필드를 식별 하 고는 `Where` 절. Visual Basic에는 암시적으로 지정 된 키 필드에 따라 두 컬렉션 조인 합니다.  
  
 명시적 조인을 사용 하 여 지정할 수 있습니다는 `Join` 절에 조인에 사용 하는 키 필드에 대 한 정확 하 게 하려는 경우. 이 경우에 `Where` 절을 사용 하 여 쿼리 결과 필터링 할 수 있습니다.  
  
#### <a name="to-perform-an-inner-join-by-using-the-join-clause"></a>Join 절을 사용 하 여 Inner Join을 수행 하려면  
  
1.  다음 코드를 추가 하는 `Module1` 둘 다 명시적 및 암시적 내부 조인의 예제를 보려면 프로젝트에는 모듈입니다.  
  
     [!code-vb[VbLINQHowTos#4](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_3.vb)]  
  
## <a name="perform-a-left-outer-join-by-using-the-group-join-clause"></a>Group Join 절을 사용 하 여 왼쪽된 우선 외부 조인 수행  
 LEFT OUTER JOIN는 조인 및 조인 오른쪽 컬렉션의 값을 일치 하는 왼쪽 컬렉션에서 모든 항목을 포함 합니다. 왼쪽 컬렉션에 일치 하는 항목을 포함 하지 않은 조인의 오른쪽 컬렉션에서 모든 항목은 쿼리 결과에서 제외 됩니다.  
  
 `Group Join` 절 수행, 실제로 LEFT OUTER JOIN 합니다. 일반적으로 라고 LEFT OUTER JOIN과의 차이점은 `Group Join` 절 반환 하는 `Group Join` 절 결과의 왼쪽 컬렉션의 각 항목에 대 한 조인 오른쪽 컬렉션을 그룹화 합니다. 관계형 데이터베이스에는 왼쪽 우선 외부 조인과 두 컬렉션 조인에서의 일치 하는 항목을 포함 하는 각 항목에는 쿼리 결과를 그룹화 되지 않은 결과 반환 합니다. 이 경우 조인의 왼쪽 컬렉션의 항목은 오른쪽 컬렉션의 각 일치 항목에 대 한 반복 됩니다. 모양 다음 절차를 수행 하는 것이 나타납니다.  
  
 결과 검색할 수는 `Group Join` 각 그룹화 된 쿼리 결과 대 한 항목을 반환 하도록 쿼리를 확장 하 여 그룹화 되지 않은 결과를 쿼리 합니다. 쿼리할 하도록 해야이를 위해는 `DefaultIfEmpty` 그룹화 된 컬렉션의 메서드. 이렇게 하면 오른쪽 컬렉션 받은 일치 하는 결과가 있는 경우에 조인의 왼쪽 컬렉션에서 항목이 쿼리 결과에 포함 계속 됩니다. 쿼리에 조인 오른쪽 컬렉션에서 일치 하는 값이 없는 경우 기본 결과 값을 제공 하려면 코드를 추가할 수 있습니다.  
  
#### <a name="to-perform-a-left-outer-join-by-using-the-group-join-clause"></a>Group Join 절을 사용 하 여 Left Outer Join을 수행 하려면  
  
1.  다음 코드를 추가 하는 `Module1` 그룹화 된 왼쪽된 우선 외부 조인 및 그룹화 되지 않은 왼쪽된 우선 외부 조인을 모두의 예제를 보려면 프로젝트에는 모듈입니다.  
  
     [!code-vb[VbLINQHowTos#3](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_4.vb)]  
  
## <a name="perform-a-join-by-using-a-composite-key"></a>복합 키를 사용 하 여 조인을 수행합니다  
 사용할 수는 `And` 키워드는 `Join` 또는 `Group Join` 대조할 때 사용 하는 여러 키 필드를 식별 하는 절 조인 중인 컬렉션에서 값입니다. `And` 키워드 지정 지정한 모든 조인할 수는 항목에 대 한 키 필드가 일치 해야 합니다.  
  
#### <a name="to-perform-a-join-by-using-a-composite-key"></a>복합 키를 사용 하 여 조인을 수행 하려면  
  
1.  다음 코드를 추가 하는 `Module1` 복합 키를 사용 하는 조인이의 예제를 보려면 프로젝트에는 모듈입니다.  
  
     [!code-vb[VbLINQHowTos#5](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_5.vb)]  
  
## <a name="run-the-code"></a>코드 실행  
  
#### <a name="to-add-code-to-run-the-examples"></a>예제를 실행 하는 코드를 추가 하려면  
  
1.  대체는 `Sub Main` 에 `Module1` 이 항목의 예제를 실행 하려면 다음 코드의 프로젝트에는 모듈입니다.  
  
     [!code-vb[VbLINQHowTos#6](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_6.vb)]  
  
2.  F5 키를 눌러 예제를 실행 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [Visual Basic의 LINQ 소개](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Join 절](../../../../visual-basic/language-reference/queries/join-clause.md)  
 [Group Join 절](../../../../visual-basic/language-reference/queries/group-join-clause.md)  
 [From 절](../../../../visual-basic/language-reference/queries/from-clause.md)  
 [Where 절](../../../../visual-basic/language-reference/queries/where-clause.md)  
 [쿼리](../../../../visual-basic/language-reference/queries/queries.md)  
 [LINQ를 통한 데이터 변환(C#)](../../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md)
