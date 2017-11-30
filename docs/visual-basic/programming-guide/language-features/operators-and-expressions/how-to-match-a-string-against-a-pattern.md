---
title: "방법: 패턴에 대해 문자열 비교(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- comparison operators [Visual Basic], comparing strings
- pattern matching
- strings [Visual Basic], comparing
- string comparison [Visual Basic], operators
- Visual Basic code, operators
- pattern matching [Visual Basic], string comparison
- string comparison [Visual Basic]
- Like operator [Visual Basic], pattern matching
- pattern matching, empty strings
- operators [Visual Basic], comparison
ms.assetid: 19a83804-b5af-4739-928b-ac93e64e457f
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 83433bdb41df0ce40d0979f3f44603f10ba1c7d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-match-a-string-against-a-pattern-visual-basic"></a>방법: 패턴에 대해 문자열 비교(Visual Basic)
식을 확인 하려는 경우는 [문자열 데이터 형식](../../../../visual-basic/language-reference/data-types/string-data-type.md) 사용 하 여 패턴을 만족는 [Like 연산자](../../../../visual-basic/language-reference/operators/like-operator.md)합니다.  
  
 `Like`두 개의 피연산자를 사용 합니다. 왼쪽된 피연산자가 문자열 식 및 오른쪽 피연산자는 일치 하는 데 사용할 패턴을 포함 하는 문자열입니다. `Like`반환 된 `Boolean` 문자열 식의 패턴을 충족 하는지 여부를 나타내는 값입니다.  
  
 특정 문자, 와일드 카드 문자, 문자 목록, 또는 문자 범위에서 문자열 식의 각 문자를 일치 시킬 수 있습니다. 패턴 문자열에 지정 된 위치는 문자열 식에 일치 시킬 문자 위치에 해당 합니다.  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-specific-character"></a>특정 문자는 문자열 식의 문자를 검색 하려면  
  
-   직접 패턴 문자열에에서 특정 문자를 넣습니다. 특수 문자를 대괄호로 묶어야 합니다 (`[ ]`). 자세한 내용은 참조 [Like 연산자](../../../../visual-basic/language-reference/operators/like-operator.md)합니다.  
  
     다음 예에서는 테스트 여부 `myString` 단일 문자를 정확 하 게 이루어져 `H`합니다.  
  
     [!code-vb[VbVbalrOperators#70](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_1.vb)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-wildcard-character"></a>와일드 카드 문자는 문자열 식의 문자를 검색 하려면  
  
-   물음표 (`?`) 패턴 문자열에 있습니다. 이 위치에 있는 유효한 문자가 일치를 만듭니다.  
  
     다음 예제에서는 테스트 여부 `myString` 단일 문자 `W` 모든 값에 정확히 두 개의 문자로 이어지는 합니다.  
  
     [!code-vb[VbVbalrOperators#71](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_2.vb)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters"></a>문자 목록에서 문자열 식의 문자를 검색 하려면  
  
-   대괄호 (`[ ]`) 패턴 문자열에서 한 문자 목록을 추가 대괄호 안에 있습니다. 쉼표 또는 다른 구분 기호 문자를 구분 하지 않습니다. 목록에 있는 한 문자 일치를 만듭니다.  
  
     다음 예에서는 테스트 여부 `myString` 모든 유효한 문자는 문자 하나에 의해 뒤 `A`, `C`, 또는 `E`합니다.  
  
     [!code-vb[VbVbalrOperators#72](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_3.vb)]  
  
     이 일치는 대/소문자 구분을 참고 합니다.  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-range-of-characters"></a>문자 범위에서 문자열 식의 문자를 검색 하려면  
  
-   대괄호 (`[ ]`) 하이픈으로 구분 된 패턴 문자열 및 최저 및 최고 문자 범위를 넣을 대괄호 안에 (`–`). 범위 내 임의의 단일 문자와 일치를 하면 있습니다.  
  
     다음 예제에서는 테스트 여부 `myString` 문자로 구성 `num` 뒤에 문자 중 하나에 의해 `i`, `j`, `k`, `l`, `m`, 또는 `n`합니다.  
  
     [!code-vb[VbVbalrOperators#73](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_4.vb)]  
  
     이 일치는 대/소문자 구분을 참고 합니다.  
  
## <a name="matching-empty-strings"></a>일치 하는 빈 문자열  
 `Like`시퀀스는 처리 `[]` 길이가 0 인 문자열 (`""`). 사용할 수 있습니다 `[]` 전체 문자열 식이 비어 있지만 문자열 식에서 특정 위치가 비어 있는지를 테스트 하려면 사용할 수 없습니다 있는지 여부를 테스트 합니다. 사용할 수 있습니다에 대 한 테스트 해야 하는 빈 위치를 사용 하는 옵션 중 하나인 경우 `Like` 두 번 이상.  
  
#### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters-or-no-character"></a>문자 또는 문자가 없는 목록에서 문자열 식의 문자를 검색 하려면  
  
1.  호출 된 `Like` 연산자에 동일한 두 번 문자열 식, 및 중 하나를 사용 하 여 두 번 호출 연결는 [또는 연산자](../../../../visual-basic/language-reference/operators/or-operator.md) 또는 [OrElse 연산자](../../../../visual-basic/language-reference/operators/orelse-operator.md)합니다.  
  
2.  첫 번째에 대 한 패턴 문자열에 `Like` 절 대괄호로 묶은 문자 목록을 포함 (`[ ]`).  
  
3.  두 번째 패턴 문자열에 `Like` 절을 배치 하지 않는 모든 문자 위치에 해당 합니다.  
  
     다음 예제에서는 테스트 7 자리 전화 번호 `phoneNum` 정확히 3 자리 숫자, 공백, 하이픈 뒤에 (`–`), 마침표 (`.`), 또는 숫자와 전혀 문자가 없습니다.  
  
     [!code-vb[VbVbalrOperators#74](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_5.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [비교 연산자](../../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [연산자 및 식](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [Like 연산자](../../../../visual-basic/language-reference/operators/like-operator.md)  
 [String 데이터 형식](../../../../visual-basic/language-reference/data-types/string-data-type.md)
