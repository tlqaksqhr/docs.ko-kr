---
title: "방법: 열거형 선언(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- enumerations [Visual Basic], declaring
- declaring enumerations [Visual Basic]
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 938550ebbfcf099729db3de96b809549cb234d81
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-enumerations-visual-basic"></a>방법: 열거형 선언(Visual Basic)
구성 된 열거형을 만들면는 `Enum` 클래스 또는 모듈 선언 섹션에서 설명 합니다. 메서드 내에서 열거형을 선언할 수 없습니다. 적절 한 액세스 수준을 지정 하려면 `Private`, `Protected`, `Friend`, 또는 `Public`합니다.  
  
 `Enum` 형식에는 이름, 내부 형식 및 필드의 집합을 각각 나타내는 상수입니다. 이름은 올바른 Visual Basic.NET 한정자 이어야 합니다. 내부 형식은 정수 형식 중 하나 여야 합니다-`Byte`, `Short`, `Long` 또는 `Integer`합니다. 기본값은 `Integer`입니다. 열거형에는 항상 강력한 형식 및 정수 숫자 형식 메서드와 호환 되지 않습니다.  
  
 열거형 부동 소수점 값을 가질 수 없습니다. 열거형에는 부동 소수점 값을 지정 되 면 `Option Strict On`, 컴파일러 오류가 발생 합니다. 경우 `Option Strict` 은 `Off`에 자동으로 변환 된 값은 `Enum` 형식입니다.  
  
 이름에 대 한 사용 하는 방법에 대 한는 `Imports` 문을 이름 한정, 불필요 한 참조 [열거형 및 이름 한정](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)합니다.  
  
### <a name="to-declare-an-enumeration"></a>열거형 선언  
  
1.  코드 액세스 수준을 포함 하는 선언을 작성 된 `Enum` 키워드 및 한 올바른 이름으로 다음 예제와 같이 각각 서로 다른 선언 `Enum`합니다.  
  
     [!code-vb[VbEnumsTask#3](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_1.vb)]  
  
2.  열거형에서 상수를 정의 합니다. 기본적으로 열거형의 첫 번째 상수에 초기화 `0`, 고 후속 상수 이전 상수 보다 하나 더 큰 값으로 초기화 됩니다. 예를 들어 다음 열거형 `Days`, 명명 된 상수를 포함 `Sunday` 값과 `0`, 명명 된 상수 `Monday` 값과 `1`, 명명 된 상수 `Tuesday` 값을가진`2`등입니다.  
  
     [!code-vb[VbEnumsTask#4](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_2.vb)]  
  
3.  명시적으로 할당 문을 사용 하 여 열거형에서 상수에 값을 할당할 수 있습니다. 음수를 포함 하는 정수 값을 할당할 수 있습니다. 예를 들어 상수를 오류 상태를 나타내는 0 보다 작은 값으로 좋습니다. 다음 열거형 상수 `Invalid` 값이 명시적으로 할당 `–1`, 상수 및 `Sunday` 값이 할당 됩니다 `0`합니다. 열거형에서 첫 번째 상수 이므로 `Saturday` 또한 값으로 초기화 됩니다 `0`합니다. 값 `Monday` 은 `1` (의 값 보다 하나 더 큰 `Sunday`);의 값 `Tuesday` 은 `2`등입니다.  
  
     [!code-vb[VbEnumsTask#5](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_3.vb)]  
  
### <a name="to-declare-an-enumeration-as-an-explicit-type"></a>명시적 형식으로 열거형 선언  
  
-   열거형 형식을 사용 하 여 지정 된 `As` 절, 다음 예제와 같이 합니다.  
  
     [!code-vb[VbEnumsTask#6](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_4.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [열거형 및 이름 한정](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [방법: 열거형 멤버 참조](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [방법: Visual Basic에서 열거형 반복](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [방법: 열거형 값과 연결된 문자열 확인](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [열거형을 사용하는 경우](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [상수 개요](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [상수 및 리터럴 데이터 형식](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)  
 [상수 및 열거형](../../../../visual-basic/language-reference/constants-and-enumerations.md)
