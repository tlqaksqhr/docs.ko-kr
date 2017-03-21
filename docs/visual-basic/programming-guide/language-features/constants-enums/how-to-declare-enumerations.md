---
title: "방법: 열거형 선언 (Visual Basic) | Microsoft 문서"
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
- declarations, enumerations
- enumerations [Visual Basic], declaring
- declaring enumerations
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
caps.latest.revision: 24
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 8ff8bf2df39bed0597740bcda968283ec854f447
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-declare-enumerations-visual-basic"></a>방법: 열거형 선언(Visual Basic)
구성 된 열거형을 만들면는 `Enum` 클래스 또는 모듈의 선언 섹션에서 문. 메서드 내에서 열거형을 선언할 수 없습니다. 적절 한 수준의 액세스를 지정 하려면 `Private`, `Protected`, `Friend`, 또는 `Public`합니다.  
  
 `Enum` 형식에는 이름, 내부 형식 및 필드 집합을 각각 나타내는 상수입니다. 이 이름은 유효한 해야 [!INCLUDE[vbprvblong](../../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] 한정자입니다. 기본 형식이 정수 형식 중 하나 여야 합니다-`Byte`, `Short`, `Long` 또는 `Integer`합니다. 기본값은 `Integer`입니다. 열거형에는 항상 강력한 형식 및 정수 숫자 형식에는 서로 호환 되지 않습니다.  
  
 열거형에는 부동 소수점 값은 포함할 수 없습니다. 열거형에는 부동 소수점 값을 할당 되 면 `Option Strict On`, 컴파일러 오류가 발생 합니다. 경우 `Option Strict` 는 `Off`에 자동으로 변환 된 값은 `Enum` 형식입니다.  
  
 이름에 대 한 정보 및 사용 하는 방법에 대 한는 `Imports` 이름 한정 불필요 하다 고 확인 하는 문을 참조 [열거형 및 이름 한정](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)합니다.  
  
### <a name="to-declare-an-enumeration"></a>열거형 선언  
  
1.  작성 한 코드 액세스 수준을 포함 하는 선언을 `Enum` 키워드 및 다른 선언는 각각 다음 예제에서와 같이 유효한 이름을 `Enum`합니다.  
  
     [!code-vb[VbEnumsTask #&3;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_1.vb)]  
  
2.  열거형에서 상수를 정의 합니다. 기본적으로 열거형의 첫 번째 상수에 초기화 `0`, 후속 상수 이전 상수 보다 하나 더 큰 값으로 초기화 됩니다. 예를 들어, 다음 열거형 `Days`, 명명 된 상수를 포함 `Sunday` 값으로 `0`, 명명 된 상수 `Monday` 값으로 `1`, 명명 된 상수 `Tuesday` 값을 가진 `2`등.  
  
     [!code-vb[VbEnumsTask #&4;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_2.vb)]  
  
3.  명시적으로 할당 문을 사용 하 여 열거형에서 상수 값을 할당할 수 있습니다. 음수를 포함 하 여 모든 정수 값을 할당할 수 있습니다. 예를 들어 오류 조건을 나타낼 수는&0; 보다 작은 값으로 상수 좋습니다. 다음 열거 상수 `Invalid` 값이 명시적으로 할당 `–1`, 상수 및 `Sunday` 값이 할당 됩니다 `0`합니다. 열거형에서 첫 번째 상수 이므로 `Saturday` 또한 값으로 초기화 됩니다 `0`합니다. 값 `Monday` 는 `1` (의 값 보다&1; `Sunday`);의 값 `Tuesday` 는 `2`등입니다.  
  
     [!code-vb[VbEnumsTask #&5;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_3.vb)]  
  
### <a name="to-declare-an-enumeration-as-an-explicit-type"></a>명시적 형식으로 열거형 선언  
  
-   열거형 형식을 사용 하 여 지정 된 `As` 절을 다음 예와에서 같이 합니다.  
  
     [!code-vb[VbEnumsTask #&6;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_4.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [열거형 및 이름 한정](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [방법: 열거형 멤버 참조](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)   
 [방법: Visual Basic에서 열거형 반복](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)   
 [방법: 열거형 값과 연결 된 문자열 확인](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)   
 [열거형을 사용 하는 경우](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)   
 [상수 개요](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)   
 [상수 및 리터럴 데이터 형식](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)   
 [상수 및 열거형](../../../../visual-basic/language-reference/constants-and-enumerations.md)
