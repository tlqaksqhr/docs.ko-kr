---
title: 선언된 요소 이름(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic], case sensitivity
- names [Visual Basic], Visual Basic rules
- naming conventions [Visual Basic]
- element names [Visual Basic]
- declared elements [Visual Basic], identifiers
- declarations [Visual Basic], elements
- declared elements [Visual Basic], valid names
- '[] escape characters [Visual Basic]'
- names [Visual Basic], elements
- declaration statements [Visual Basic], declared elements
- declaring elements [Visual Basic]
- identifiers [Visual Basic], declared elements
- case sensitivity, declared element names
- escape characters [Visual Basic]
- names [Visual Basic], declared elements
- declared elements [Visual Basic], about declared elements
- escaped names [Visual Basic]
- declared elements [Visual Basic], names
- names [Visual Basic], naming conventions
- identifiers [Visual Basic], elements
ms.assetid: 09d8843b-c0dc-4afe-9dab-87c439a69e66
ms.openlocfilehash: 2f48f885b66f99ecc8c6c7e13fea7e75f0e3d24a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="declared-element-names-visual-basic"></a>선언된 요소 이름(Visual Basic)
선언 된 모든 요소 이름이 라고도 *식별자*는 코드는 참조 하는 데 사용 하는 하 합니다.  
  
## <a name="rules"></a>규칙  
 Visual Basic의 요소 이름은 다음 규칙을 따라야 합니다.  
  
-   알파벳 문자 또는 밑줄로 시작 해야 합니다 (`_`).  
  
-   영문자, 10 진수 숫자 및 밑줄로 포함 해야 합니다.  
  
-   밑줄로 시작 하는 경우 하나 이상의 영문자 또는 10 진수 포함 해야 합니다.  
  
-   1, 024 개 이상의 자 않아야 합니다.  
  
 1023 자 길이 제한에도 적용 됩니다는 정규화 된 이름, 전체 문자열 같은 `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`합니다.  
  
 다음 예제에서는 올바른 요소 이름을 보여 줍니다.  
  
 `aB123__45`  
  
 `_567`  
  
 다음 예제에서는 잘못 된 요소 이름을 보여 줍니다. 첫 번째만 밑줄을 포함 하 고, 10 진수로 시작 하는 두 번째 및 세 번째에 잘못 된 문자 ($).  
  
 `' Three INVALID element names`  
  
 `_`  
  
 `12ABC`  
  
 `xyz$wv`  
  
> [!CAUTION]
>  밑줄로 시작 하는 요소 이름 (`_`)의 일부가 [언어 독립성 및 언어 독립적 구성 요소](../../../../standard/language-independence-and-language-independent-components.md) (CLS), 하므로 CLS 규격 코드에서 해당 이름을 정의 하는 구성 요소를 사용할 수 없습니다. 그러나 다른 위치에서 요소 이름에 밑줄은 CLS 규격이 합니다.  
  
### <a name="name-length-guidelines"></a>이름 길이 지침  
 명확히 요소의 특성을 식별 하는 동안 사용자 이름은 최대한 단축 해야 합니다. 이 코드의 가독성을 높일 수 및 줄 길이 소스 파일 크기를 줄입니다.  
  
 반면에 사용자 이름이 너무 짧아서는 설명 하지는 않습니다 적절 하 게 코드 방법을 사용 하 여 요소 무엇을 나타내는지가 되지 않아야 합니다. 이 코드의 가독성을 위해 중요 합니다. 다른 사람을 이해 하려고 하거나 자신을 원하는 경우에 쓰고 이때 후 오랫동안 적합 한 요소 이름을 상당한 시간이 저장할 수 있습니다.  
  
## <a name="escaped-names"></a>이스케이프 이름  
 일반적으로 요소 이름이 일치 하지 않아야 Visual Basic의 경우에서 같은 예약 된 키워드 `Case` 또는 `Friend`합니다. 정의할 수 있습니다는 *이스케이프 이름*, 대괄호로 묶여 있는 (`[ ]`). 이스케이프 된 이름의 대괄호는 모호성을 제거 하는 이후 Visual Basic 키워드, 일치할 수 있습니다. 코드에서 이름으로 참조할 때 대괄호를 사용 합니다.  
  
 이스케이프 된 이름을 사용 해야 하는 일반적으로 경우에만:  
  
-   이전 버전의 이름으로 사용 되는 키워드를 예약 하지 않은 Visual Basic에서 코드를 마이그레이션한 또는  
  
-   지정 된 키워드가 예약 되지 않은 다른 언어로 작성 된 코드를 사용 하 여 작업할 합니다.  
  
 그렇지 않으면 해당 이름이 키워드와 충돌 하는 경우 해당 요소의 이름을 하는 것이 좋습니다. 통합된 개발 환경 (IDE)이 작업을 수행 하는 쉬운 방법을 제공 합니다. 자세한 내용은 참조 [Refactoring](/visualstudio/vb-ide/refactoring-vb)합니다.  
  
## <a name="case-sensitivity-in-names"></a>이름에서 대/소문자 구분  
 Visual Basic의 요소 이름이 대/소문자를 구분 하지 않습니다. 이 컴파일러에는 소문자만 다르고 이름은 동일한 두 개의 비교를 해석 동일한 이름으로 의미 합니다. 예를 들어, `ABC` 와 `abc` 는 동일한 선언 요소를 참조하는 것으로 간주합니다.  
  
 그러나 공용 언어 런타임 (CLR) 대/소문자 구분 바인딩을 사용 합니다. 그러므로, 어셈블리나 DLL을 작성하여 다른 어셈블리에서 이를 사용하게 되면 이름의 대/소문자가 구분됩니다. 예를 들어, `ABC`라는 이름의 요소를 포함하는 클래스를 정의하고 다른 어셈블리에서 공용 언어 런타임을 통해 이 클래스를 사용할 경우 해당 어셈블리에서 이 요소를 `ABC`로 참조해야 합니다. 경우 하면 이후에 클래스를 다시 컴파일하고 요소 하 고 이름을 `abc`, 클래스를 사용 하는 다른 어셈블리가 해당 요소를 더 이상 액세스할 수 없습니다. 따라서, 어셈블리를 업데이트하여 릴리스하는 경우 공용 요소의 알파벳 대/소문자를 변경하지 않아야 합니다.  
  
## <a name="names-and-locales"></a>이름 및 로캘  
 이름 비교는 로캘과 무관 합니다. 1 개 로캘만에 두 이름이 일치 하는 경우 모든 로캘에서 일치 하도록 보장 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [선언 요소](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)  
 [선언 요소의 특징](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [선언된 요소 참조](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [문](../../../../visual-basic/language-reference/statements/index.md)
