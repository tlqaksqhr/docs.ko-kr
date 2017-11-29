---
title: "RemoveHandler 문"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
helpviewer_keywords:
- RemoveHandler keyword [Visual Basic]
- RemoveHandler statement [Visual Basic]
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 82d130c6536df7d72977a028333293b4e0ee89de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="removehandler-statement"></a>RemoveHandler 문
이벤트와 이벤트 처리기가 연결을 제거합니다.  
  
## <a name="syntax"></a>구문  
  
```  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`event`|처리 중인 이벤트의 이름입니다.|  
|`eventhandler`|현재 이벤트를 처리 하는 프로시저의 이름입니다.|  
  
## <a name="remarks"></a>설명  
 `AddHandler` 및 `RemoveHandler` 문을 사용 하면 시작 하 고 언제 든 지 프로그램 실행 중 특정 이벤트에 대 한 이벤트 처리를 중지 합니다.  
  
> [!NOTE]
>  사용자 지정 이벤트에는 `RemoveHandler` 문은 이벤트의 호출 `RemoveHandler` 접근자입니다. 사용자 지정 이벤트에 대 한 자세한 내용은 참조 하십시오. [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)합니다.  
  
## <a name="example"></a>예제  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/removehandler-statement_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [AddHandler 문](../../../visual-basic/language-reference/statements/addhandler-statement.md)  
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)  
 [이벤트](../../../visual-basic/programming-guide/language-features/events/index.md)
