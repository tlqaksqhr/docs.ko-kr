---
title: "문자 데이터 형식 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- data types [Visual Basic], character
- String data type, character data types
- character data types [Visual Basic]
- Char data type, character data types
- data types [Visual Basic], choosing
ms.assetid: 902479ef-1679-47fc-9911-0c1c5008226c
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 7ce600fe188c94593e4c07e37883ca11f90d9ae5
ms.lasthandoff: 03/13/2017

---
# <a name="character-data-types-visual-basic"></a>문자 데이터 형식(Visual Basic)
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]제공 *문자 데이터 형식* 인쇄 하거나 표시할 수 있는 문자를 처리 해야 합니다. 유니코드 문자를 모두 처리 하는 동안 `Char` 반면은 단일 문자를 `String` 불특정 개수의 문자를 포함 합니다.  
  
 나란히 비교를 표시 하는 테이블에 대 한는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 데이터 형식 참조 [데이터 형식](../../../../visual-basic/language-reference/data-types/data-type-summary.md)합니다.  
  
## <a name="char-type"></a>Char 형식  
 `Char` 데이터 형식은 단일&2; 바이트 (16 비트) 유니코드 문자입니다. 변수 항상 정확히 한 문자를 저장 하는 경우로 선언 `Char`합니다. 예:  
  
 [!code-vb[VbVbalrCharTypes #&1;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_1.vb)]  
  
 가능한 각 값에는 `Char` 또는 `String` 변수가 *코드 포인트*, 또는 유니코드 문자 집합에서 문자 코드입니다. 유니코드 문자는 기본 ASCII 문자 집합, 다양 한 다른 알파벳 문자, 악센트, 통화 기호, 분수, 분음 부호, 및 수학 및 공학 기호를 포함 합니다.  
  
> [!NOTE]
>  유니코드 문자 집합 코드 포인트 D800 ~ DFFF 55296 55551 10 진수에 대 한 *서로게이트 쌍*, 단일 코드 포인트를 나타내는 두 개의 16 비트 값 필요 합니다. A `Char` 변수는 서로게이트 쌍을 포함할 수 없습니다 및 `String` 이러한 쌍 유지 하기 위해 두 개의 위치를 사용 합니다.  
  
 자세한 내용은 참조 [Char 데이터 형식을](../../../../visual-basic/language-reference/data-types/char-data-type.md)합니다.  
  
## <a name="string-type"></a>문자열 형식  
 `String` 데이터 형식은&0; 개 이상의&2; 바이트 (16 비트) 유니코드 문자 시퀀스입니다. 변수를 무제한으로 문자를 포함할 수 있으면로 선언 `String`합니다. 예:  
  
 [!code-vb[VbVbalrCharTypes #&2;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_2.vb)]  
  
 자세한 내용은 참조 [문자열 데이터 형식](../../../../visual-basic/language-reference/data-types/string-data-type.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [기본 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [복합 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)   
 [Visual Basic의 제네릭 형식](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [값 형식과 참조 형식](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Visual Basic의 형식 변환](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [데이터 형식 문제 해결](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [형식 문자](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
