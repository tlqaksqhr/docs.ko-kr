---
title: "파생 클래스는 기본 클래스 이벤트를 발생시킬 수 없습니다."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords: BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 70dde8b96980adfd618e38b9ce142cdec56a6b13
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="derived-classes-cannot-raise-base-class-events"></a>파생 클래스는 기본 클래스 이벤트를 발생시킬 수 없습니다.
이벤트 선언 된 선언 공간 에서만에서 발생할 수 있습니다. 따라서 클래스 다른 클래스와 파생 된 하나에서 이벤트를 발생 시킬 수 없습니다.  
  
 **오류 ID:** BC30029  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   이동의 `Event` 문 또는 `RaiseEvent` 문을 동일한 클래스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)  
 [RaiseEvent 문](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
