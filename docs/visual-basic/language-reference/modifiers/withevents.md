---
title: "WithEvents (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.WithEvents
- WithEvents
dev_langs:
- VB
helpviewer_keywords:
- WithEvents keyword
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
caps.latest.revision: 17
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
ms.openlocfilehash: 708cf6fec78faf2c7a5959a3a2694d237d728882
ms.lasthandoff: 03/13/2017

---
# <a name="withevents-visual-basic"></a>WithEvents(Visual Basic)
선언 된 멤버 변수를 하나 이상의 이벤트를 발생 시킬 수 있는 클래스의 인스턴스를 참조 하도록 지정 합니다.  
  
## <a name="remarks"></a>주의  
 변수를 사용 하 여 정의 되 면 `WithEvents`, 메서드를 사용 하 여 변수의 이벤트를 처리 하는 선언적으로 지정할 수는 `Handles` 키워드입니다.  
  
 사용할 수 있습니다 `WithEvents` 클래스 또는 모듈 수준에만 있습니다. 즉, 선언 컨텍스트는 `WithEvents` 변수는 클래스 또는 모듈 이어야 하며 소스 파일, 네임 스페이스, 구조체 또는 프로시저 될 수 없습니다.  
  
 사용할 수 없습니다 `WithEvents` 구조체 멤버에 있습니다.  
  
 개별 변수만 선언할 수 있습니다-배열은 하지-와 `WithEvents`합니다.  
  
## <a name="rules"></a>규칙  
  
-   **요소 형식입니다.** 선언 해야 `WithEvents` 클래스 인스턴스 변수를 받아들일 수 있도록 개체 변수입니다. 그러나 매개 변수를 선언할 수 없습니다 `Object`합니다. 이벤트를 발생 시킬 수 있는 특정 클래스로 선언 해야 합니다.  
  
 `WithEvents` 한정자는이 컨텍스트에서 사용할 수 있습니다: [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## <a name="see-also"></a>참고 항목  
 [핸들](../../../visual-basic/language-reference/statements/handles-clause.md)   
 [키워드](../../../visual-basic/language-reference/keywords/index.md)   
 [이벤트](../../../visual-basic/programming-guide/language-features/events/index.md)
