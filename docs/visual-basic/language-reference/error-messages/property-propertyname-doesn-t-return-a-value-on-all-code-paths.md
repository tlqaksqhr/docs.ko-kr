---
title: 속성 &#39; &lt;propertyname&gt; &#39; 대상이&#39;모든 코드 경로 에서만 값을 반환 하는 t
ms.date: 07/20/2015
f1_keywords:
- bc42107
- vbc42107
helpviewer_keywords:
- BC42107
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
ms.openlocfilehash: 72bc7e45cadd2528f29c88bf6e80ee5f381052dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33594216"
---
# <a name="property-39ltpropertynamegt39-doesn39t-return-a-value-on-all-code-paths"></a>속성 &#39; &lt;propertyname&gt; &#39; 대상이&#39;모든 코드 경로 에서만 값을 반환 하는 t
속성 '\<propertyname >' 모든 코드 경로 대해서만 값을 반환 합니다. 이 결과를 사용하면 런타임에 null 참조 예외가 발생할 수 있습니다.  
  
 속성 `Get` 프로시저 코드 값을 반환 하지 않는 통해 하나 이상의 경로가 있습니다.  
  
 속성에서 값을 반환할 수 `Get` 절차는 다음과 같은 방법 중 하나:  
  
-   속성 이름에 값을 할당 한 후 수행 된 `Exit Property` 문.  
  
-   속성 이름에 값을 할당 한 후 수행 된 `End Get` 문.  
  
-   에 대 한 값이 포함 된 [Return 문을](../../../visual-basic/language-reference/statements/return-statement.md)합니다.  
  
 컨트롤을 전달 하는 경우 `Exit Property` 또는 `End Get` 속성 이름에 값을 할당 하지 않은 하 고는 `Get` 프로시저가 속성의 데이터 형식의 기본 값을 반환 합니다. 자세한 내용은의 "동작" 참조 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)합니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기 거 나 경고를 오류로 처리 하는 방법에 대 한 자세한 내용은 참조 하십시오. [Visual Basic에서 경고 구성](/visualstudio/ide/configuring-warnings-in-visual-basic)합니다.  
  
 **오류 ID:** BC42107  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   제어 흐름 논리를 검사 하 고 반환의 원인이 되는 모든 문 앞에 값을 할당 해야 합니다.  
  
     항상 사용 하는 경우 프로시저에서 모든 반환 값을 반환 하 게 하는 것이 쉽습니다는 `Return` 문. 이렇게 하면, 앞의 마지막 문이 `End Get` 이어야 합니다는 `Return` 문.  
  
## <a name="see-also"></a>참고 항목  
 [속성 프로시저](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)  
 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Get 문](../../../visual-basic/language-reference/statements/get-statement.md)
