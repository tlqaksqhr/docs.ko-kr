---
title: 문자 데이터 형식(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- data types [Visual Basic], character
- String data type [Visual Basic], character data types
- character data types [Visual Basic]
- Char data type [Visual Basic], character data types
- data types [Visual Basic], choosing
ms.assetid: 902479ef-1679-47fc-9911-0c1c5008226c
ms.openlocfilehash: 5a6a8dae63f3c0b5e3038304c1c2242f9e8c9c9d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="character-data-types-visual-basic"></a>문자 데이터 형식(Visual Basic)
Visual Basic에서는 *문자 데이터 형식과* 를 인쇄 하거나 표시할 수 있는 문자를 처리 합니다. 유니코드 문자는 모두 처리 하는 동안 `Char` 반면은 단일 문자를 `String` 불특정 개수의 문자를 포함 합니다.  
  
 Visual Basic 데이터 형식 비교 나란히 표시 하는 테이블을 참조 하십시오. [데이터 형식](../../../../visual-basic/language-reference/data-types/data-type-summary.md)합니다.  
  
## <a name="char-type"></a>Char 형식  
 `Char` 데이터 형식은 2 바이트 (16 비트) 단일 유니코드 문자입니다. 변수는 항상 정확히 한 문자를 저장, 하는 경우로 선언 `Char`합니다. 예를 들어:  
  
 [!code-vb[VbVbalrCharTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#1)]
  
 가능한 각 값에는 `Char` 또는 `String` 변수가 *코드 포인트*, 또는 유니코드 문자 집합에서 문자 코드입니다. 유니코드 문자 등이 기본 ASCII 문자 집합, 다양 한 다른 알파벳 글자, 악센트, 통화 기호, 분수, 분음 기호, 수학 및 기술 기호 있습니다.  
  
> [!NOTE]
>  유니코드 문자 집합는 코드 포인트에 대 한 55296 55551 10 진수 DFFF 까지의 D800 *서로게이트 쌍*, 단일 코드 포인트를 나타내기 위해 두 개의 16 비트 값이 필요한 합니다. A `Char` 변수는 서로게이트 쌍을 포함할 수 없습니다 및 `String` 이러한 쌍 유지 하기 위해 두 개의 위치를 사용 합니다.  
  
 자세한 내용은 참조 [Char 데이터 형식을](../../../../visual-basic/language-reference/data-types/char-data-type.md)합니다.  
  
## <a name="string-type"></a>문자열 형식  
 `String` 데이터 형식은 0 개 이상의 2 바이트 (16 비트) 유니코드 문자 시퀀스입니다. 변수에서 불특정 개수의 문자를 포함할 수 있으면로 선언 `String`합니다. 예를 들어:  
  
 [!code-vb[VbVbalrCharTypes#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#2)]
  
 자세한 내용은 참조 [문자열 데이터 형식](../../../../visual-basic/language-reference/data-types/string-data-type.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [기본 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [복합 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [Visual Basic의 제네릭 형식](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [값 형식과 참조 형식](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Visual Basic의 형식 변환](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [데이터 형식 문제 해결](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [형식 문자](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
