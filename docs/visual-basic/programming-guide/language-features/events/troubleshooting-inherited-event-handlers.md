---
title: "Visual Basic에서 이벤트 처리기를 상속 문제 해결 | Microsoft 문서"
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
- troubleshooting events
- inherited events
- troubleshooting Visual Basic, event handlers
- event handling, troubleshooting
- event handlers, troubleshooting
ms.assetid: e1c8759f-5370-4308-8476-8c48b73509bf
caps.latest.revision: 11
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
ms.openlocfilehash: 0dae6b48b1885a52b99ae3e7328340cac7b2d7d4
ms.lasthandoff: 03/13/2017

---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a>Visual Basic에서 상속된 이벤트 처리기 관련 문제 해결
이 항목에서는 이벤트 처리기 상속 된 구성 요소에서 발생 하는 일반적인 문제입니다.  
  
## <a name="procedures"></a>절차  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a>이벤트 처리기의 코드는 모든 호출에 대 한 두 번 실행  
  
-   상속된 된 이벤트 처리기를 포함 하지 않아야는 [처리](../../../../visual-basic/language-reference/statements/handles-clause.md) 절. 기본 클래스의 메서드는 이벤트와 이미 연결 되어 하 고 그에 따라 실행 됩니다. 제거는 `Handles` 상속 된 메서드에서 절.  
  
     [!code-vb[VbVbalrEvents #&32;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/troubleshooting-inherited-event-handlers_1.vb)]  
  
-   상속 된 메서드가 없는 경우는 `Handles` 키워드를 코드는 포함 되지 않았는지 확인 [AddHandler 문](../../../../visual-basic/language-reference/statements/addhandler-statement.md) 또는 동일한 이벤트를 처리 하는 추가 메서드가 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [이벤트](../../../../visual-basic/programming-guide/language-features/events/index.md)
