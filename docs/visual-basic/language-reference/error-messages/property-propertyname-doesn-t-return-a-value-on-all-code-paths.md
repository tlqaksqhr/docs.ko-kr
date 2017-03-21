---
title: "속성 &quot;&lt;propertyname&gt;&quot; 모든 코드 경로에서 값을 반환 하지 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42107
- vbc42107
dev_langs:
- VB
helpviewer_keywords:
- BC42107
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
caps.latest.revision: 7
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
ms.openlocfilehash: e7c94d827761ad26d517b44a06734c5db4480a62
ms.lasthandoff: 03/13/2017

---
# <a name="property-39ltpropertynamegt39-doesn39t-return-a-value-on-all-code-paths"></a>속성 '&lt;propertyname&gt;' 모든 코드 경로 대해서만 값을 반환
속성 '\<propertyname > ' 모든 코드 경로 대해서만 값을 반환 합니다. 이 결과를 사용하면 런타임에 null 참조 예외가 발생할 수 있습니다.  
  
 속성 `Get` 프로시저 코드 값을 반환 하지 않는 통해 하나 이상의 경로가 있습니다.  
  
 속성에서 값을 반환할 수 `Get` 절차는 다음 방법 중 하나:  
  
-   속성 이름에 값을 할당 한 다음 수행할는 `Exit Property` 문입니다.  
  
-   속성 이름에 값을 할당 한 후 수행 된 `End Get` 문.  
  
-   값을 포함 한 [Return 문을](../../../visual-basic/language-reference/statements/return-statement.md)합니다.  
  
 컨트롤을 전달 하는 경우 `Exit Property` 또는 `End Get` 속성 이름에 값을 할당 하지 않은 및는 `Get` 프로시저 속성의 데이터 형식의 기본 값을 반환 합니다. 자세한 내용은 "동작"의 참조 [Function 문의](../../../visual-basic/language-reference/statements/function-statement.md)합니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기 거 나 경고를 오류로 처리에 대 한 자세한 내용은 참조 하십시오. [Visual Basic에서 경고 구성](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)합니다.  
  
 **오류 ID:** BC42107  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   제어 흐름 논리를 검사 하 고 반환의 원인이 되는 모든 문 앞에 값을 할당 해야 합니다.  
  
     항상 사용 하는 경우 프로시저에서 모든 반환 값을 반환 하 게 하는 것이 쉽습니다는 `Return` 문입니다. 이렇게 하면, 앞의 마지막 문이 `End Get` 있어야는 `Return` 문입니다.  
  
## <a name="see-also"></a>참고 항목  
 [속성 프로시저](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Get 문](../../../visual-basic/language-reference/statements/get-statement.md)
