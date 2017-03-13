---
title: "&#39;Custom&#39; modifier is not valid on events declared without explicit delegate types | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc31122"
  - "bc31122"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31122"
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# &#39;Custom&#39; modifier is not valid on events declared without explicit delegate types
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

사용자 지정하지 않은 이벤트와 달리 `Custom Event` 선언에는 이벤트에 대한 대리자 형식을 명시적으로 지정하는 이벤트 이름 다음에 `As` 절이 필요합니다.  
  
 사용자 지정하지 않은 이벤트는 `As` 절과 명시적 대리자 형식을 사용하거나 이벤트 이름 바로 다음에 매개 변수 목록을 사용하여 정의할 수 있습니다.  
  
 **오류 ID:** BC31122  
  
### 이 오류를 해결하려면  
  
1.  같은 매개 변수 목록을 사용하여 대리자를 사용자 지정 이벤트로 정의합니다.  
  
     예를 들어, `Custom Event`가 `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`에서 정의되면 해당하는 대리자는 다음과 같습니다.  
  
     [!code-vb[VbVbalrEventError#18](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_1.vb)]  
  
2.  사용자 지정 이벤트의 매개 변수 목록을 대리자 형식을 지정하는 `As` 절로 바꿉니다.  
  
     이렇게 수행하려면 `Custom Event` 선언을 다음과 같이 다시 쓸 수 있습니다.  
  
     [!code-vb[VbVbalrEventError#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_2.vb)]  
  
## 예제  
 이 예제에서는 `Custom Event`를 선언하고 대리자 형식과 함께 필요한 `As` 절을 지정합니다.  
  
 [!code-vb[VbVbalrEventError#2](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_3.vb)]  
  
## 참고 항목  
 [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md)   
 [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [Events](../../../visual-basic/programming-guide/language-features/events/events.md)