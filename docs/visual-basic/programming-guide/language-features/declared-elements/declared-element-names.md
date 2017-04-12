---
title: "선언 된 요소 이름 (Visual Basic) | Microsoft 문서"
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
- declared elements, case sensitivity
- names, Visual Basic rules
- naming conventions
- element names
- declared elements, identifiers
- declarations, elements
- declared elements, valid names
- '[] escape characters [Visual Basic]'
- names, elements
- declaration statements, declared elements
- declaring elements
- identifiers, declared elements
- case sensitivity, declared element names
- escape characters
- names, declared elements
- declared elements, about declared elements
- escaped names
- declared elements, names
- names, naming conventions
- identifiers, elements
ms.assetid: 09d8843b-c0dc-4afe-9dab-87c439a69e66
caps.latest.revision: 27
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
ms.openlocfilehash: 56ac0684e5176f33aa6f9600f20d9fe3fcf09416
ms.lasthandoff: 03/13/2017

---
# <a name="declared-element-names-visual-basic"></a>선언된 요소 이름(Visual Basic)
선언 된 모든 요소에 이름이 있는 라고도 *식별자*, 즉, 참조 하는 데 코드 사용 합니다.  
  
## <a name="rules"></a>규칙  
 요소 이름은 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 다음 규칙을 준수 해야 합니다.  
  
-   영문자 또는 밑줄으로 시작 해야 합니다 (`_`).  
  
-   알파벳 문자와&10; 진수 숫자, 밑줄에만 포함 해야 합니다.  
  
-   밑줄로 시작 하는 경우 하나 이상의 영문자 또는&10; 진수 포함 해야 합니다.  
  
-   개 이상의 1023 자 아니어야 합니다.  
  
 1023 자 길이 제한에도 적용 됩니다 정규화 된 이름, 전체 문자열 같은 `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`합니다.  
  
 다음 예제에서는 올바른 요소 이름을 보여 줍니다.  
  
 `aB123__45`  
  
 `_567`  
  
 다음 예제에서는 잘못 된 요소 이름을 보여 줍니다. 첫 번째는 밑줄만 포함,&10; 진수로 시작 하 고 두 번째 및 세 번째 잘못 된 문자 ($)를 포함 합니다.  
  
 `' Three INVALID element names`  
  
 `_`  
  
 `12ABC`  
  
 `xyz$wv`  
  
> [!CAUTION]
>  밑줄로 시작 하는 요소 이름 (`_`)의 일부가 [언어 독립성 및 언어 독립적 구성 요소](https://msdn.microsoft.com/library/12a7a7h3) CLS ()를 CLS 규격 코드에서 해당 이름을 정의 하는 구성 요소를 사용할 수 없습니다. 그러나 요소 이름에 다른 위치에는 밑줄은 CLS 규격입니다.  
  
### <a name="name-length-guidelines"></a>이름 길이 지침  
 명확히 요소의 특성을 식별 하는 동안 사용자 이름은 가능한 한 짧게 해야 합니다. 이 코드의 가독성을 향상 하 고 줄 길이 소스 파일 크기를 줄입니다.  
  
 반면에 사용자 이름을 설명 하지는 않습니다 적절 하 게 코드 방법을 사용 하 여 요소 무엇을 나타내는지를 짧은 되지 않아야 합니다. 이 코드의 가독성을 위해 중요 합니다. 이해 하려는 다른 사용자 또는 사용자가 직접 찾고 있는 경우에 쓰고 후 오랫동안 적합 한 요소 이름을 상당한 시간이 저장할 수 있습니다.  
  
## <a name="escaped-names"></a>이스케이프 이름  
 일반적으로 요소 이름은 같아서는 안 하 여 예약 된 키워드의 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], 예: `Case` 또는 `Friend`합니다. 그러나 정의할 수는 *이스케이프 이름*, 괄호로 묶여 있는 (`[ ]`). 일치 하는 이스케이프 된 이름 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 키워드를 대괄호 모호성이 있기 때문입니다. 코드에서 이름으로 참조할 때 대괄호를 사용 합니다.  
  
 이스케이프 된 이름을 사용 해야 하는 일반적으로 경우에만:  
  
-   코드의 이전 버전에서 마이그레이션된 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 되는 이름으로 사용 되는 키워드를 예약 하지 않은 또는  
  
-   지정 된 키워드는 예약 되지 않은 다른 언어로 작성 된 코드를 사용 하 여 작업할 합니다.  
  
 그렇지 않으면 해당 이름이 키워드와 충돌 하는 경우 해당 요소의 이름을 하는 것이 좋습니다. 통합된 개발 환경 (IDE)이 작업을 수행 하는 쉬운 방법을 제공 합니다. 자세한 내용은 참조 [Refactoring](https://docs.microsoft.com/visualstudio/vb-ide/refactoring-vb)합니다.  
  
## <a name="case-sensitivity-in-names"></a>이름에서 대/소문자 구분  
 요소 이름은 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 대/소문자 구분 합니다. 이 컴파일러에 소문자만 다른 두 이름이 같고, 것으로 해석 동일한 이름을 의미 합니다. 예를 들어, `ABC` 와 `abc` 는 동일한 선언 요소를 참조하는 것으로 간주합니다.  
  
 그러나 공용 언어 런타임 (CLR)에 대/소문자 구분 바인딩을 사용 합니다. 그러므로, 어셈블리나 DLL을 작성하여 다른 어셈블리에서 이를 사용하게 되면 이름의 대/소문자가 구분됩니다. 예를 들어, `ABC`라는 이름의 요소를 포함하는 클래스를 정의하고 다른 어셈블리에서 공용 언어 런타임을 통해 이 클래스를 사용할 경우 해당 어셈블리에서 이 요소를 `ABC`로 참조해야 합니다. 경우 이후에 클래스를 다시 컴파일한 요소의 이름을 `abc`, 클래스를 사용 하는 다른 어셈블리가 해당 요소를 더 이상 액세스할 수 없습니다. 따라서, 어셈블리를 업데이트하여 릴리스하는 경우 공용 요소의 알파벳 대/소문자를 변경하지 않아야 합니다.  
  
## <a name="names-and-locales"></a>이름 및 로캘  
 이름 비교는 로캘과 무관 합니다. 두 이름이 일치 한 로캘에서 모든 로캘에서 일치 하도록 보장 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [선언된 요소](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)   
 [선언된 요소의 특징](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)   
 [선언 된 요소에 대 한 참조](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [문](../../../../visual-basic/language-reference/statements/index.md)
