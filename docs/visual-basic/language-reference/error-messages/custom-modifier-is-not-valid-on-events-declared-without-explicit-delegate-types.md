---
title: '&#39;사용자 지정&#39; 한정자 명시적 대리자 형식 없이 선언 된 이벤트에서 유효 하지 않습니다.'
ms.date: 07/20/2015
f1_keywords:
- vbc31122
- bc31122
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
ms.openlocfilehash: 3f08bbbbbac4a01dfbac8d15cf9285c01262618a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587524"
---
# <a name="39custom39-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a>&#39;사용자 지정&#39; 한정자 명시적 대리자 형식 없이 선언 된 이벤트에서 유효 하지 않습니다.
사용자 지정이 아닌 이벤트와 달리는 `Custom Event` 선언에 필요는 `As` 이벤트 이름 다음에 이벤트에 대 한 대리자 형식을 명시적으로 지정 하는 절.  
  
 비-사용자 지정 이벤트 수 사용 하 여 정의할는 `As` 절과 명시적 대리자, 형식 또는 매개 변수가 즉시를 나열 이벤트 이름 다음에 있습니다.  
  
 **오류 ID:** BC31122  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  사용자 지정 이벤트로 동일한 매개 변수 목록 사용 하 여 대리자를 정의 합니다.  
  
     예를 들어 경우는 `Custom Event` 에 의해 정의 되었습니다 `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, 있으면 해당 대리자 다음 합니다.  
  
     [!code-vb[VbVbalrEventError#18](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_1.vb)]  
  
2.  매개 변수 목록으로 사용자 지정 이벤트 바꾸기는 `As` 절을 대리자 형식을 지정 합니다.  
  
     예제에 이어서 `Custom Event` 선언은 다음과 같이 작성 될 것입니다.  
  
     [!code-vb[VbVbalrEventError#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_2.vb)]  
  
## <a name="example"></a>예제  
 이 예제에서는 선언는 `Custom Event` 필요한 지정 `As` 대리자 형식으로는 절.  
  
 [!code-vb[VbVbalrEventError#2](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_3.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)  
 [Delegate 문](../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [이벤트](../../../visual-basic/programming-guide/language-features/events/index.md)
