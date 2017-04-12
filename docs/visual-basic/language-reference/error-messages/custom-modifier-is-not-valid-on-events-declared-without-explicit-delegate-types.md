---
title: "&quot;Custom&quot; 한정자 명시적 대리자 형식 없이 선언 된 이벤트에서 유효 하지 않습니다. | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31122
- bc31122
dev_langs:
- VB
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
caps.latest.revision: 9
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
ms.openlocfilehash: 0e70fca6a0608df5db43156f70196b4e5c9b2339
ms.lasthandoff: 03/13/2017

---
# <a name="39custom39-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a>'Custom' 한정자 명시적 대리자 형식 없이 선언 된 이벤트에서 유효 하지 않습니다.
사용자 지정이 아닌 이벤트와 달리는 `Custom Event` 선언 필요는 `As` 이벤트 이름 다음에 이벤트에 대 한 대리자 형식을 명시적으로 지정 하는 절.  
  
 비-사용자 지정 이벤트 수 사용 하 여 정의할는 `As` 절과 명시적 대리자 형식, 또는 매개 변수와 함께 나열 즉시 이벤트 이름 다음에 있습니다.  
  
 **오류 ID:** BC31122  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  사용자 지정 이벤트와 동일한 매개 변수 목록 사용 하 여 대리자를 정의 합니다.  
  
     예를 들어 하는 경우는 `Custom Event` 정의한 `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, 해당 대리자에는 다음 됩니다.  
  
     [!code-vb[VbVbalrEventError #&18;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_1.vb)]  
  
2.  매개 변수 목록을 사용 하 여 사용자 지정 이벤트의 대체는 `As` 절을 대리자 형식을 지정 합니다.  
  
     예를 들어 계속 `Custom Event` 선언을 다음과 같이 다시 작성 합니다.  
  
     [!code-vb[VbVbalrEventError #&19;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_2.vb)]  
  
## <a name="example"></a>예제  
 이 예제에서는 선언는 `Custom Event` 필수 지정 `As` 대리자 형식으로 절.  
  
 [!code-vb[VbVbalrEventError #&2;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_3.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)   
 [Delegate 문](../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [이벤트](../../../visual-basic/programming-guide/language-features/events/index.md)
