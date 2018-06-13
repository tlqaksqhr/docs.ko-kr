---
title: AddHandler 문
ms.date: 07/20/2015
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
ms.openlocfilehash: db8131dc82aed40e725c9375efef274fb6917d41
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603654"
---
# <a name="addhandler-statement"></a>AddHandler 문
이벤트 처리기에서 런타임에 이벤트에 연결합니다.  
  
## <a name="syntax"></a>구문  
  
```  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>요소  
 `event`  
 처리할 이벤트의 이름입니다.  
  
 `eventhandler`  
 이벤트를 처리 하는 프로시저의 이름입니다.  
  
## <a name="remarks"></a>설명  
 `AddHandler` 및 `RemoveHandler` 문을 사용 하면 시작 하 고 프로그램 실행 중 언제 든 지 이벤트 처리를 중지 합니다.  
  
 시그니처는 `eventhandler` 이벤트의 서명이 일치 해야 `event`합니다.  
  
 `Handles` 키워드와 `AddHandler` 문 모두 특정 프로시저에서 특정 이벤트를 처리하도록 지정하는 데 사용할 수 있지만 차이가 있습니다. `AddHandler` 문은 런타임에 프로시저를 이벤트에 연결합니다. 특정 이벤트를 처리하도록 지정하는 프로시저를 정의할 때 `Handles` 키워드를 사용합니다. 자세한 내용은 참조 [처리](../../../visual-basic/language-reference/statements/handles-clause.md)합니다.  
  
> [!NOTE]
>  사용자 지정 이벤트에는 `AddHandler` 문은 이벤트의 호출 `AddHandler` 접근자입니다. 사용자 지정 이벤트에 대 한 자세한 내용은 참조 하십시오. [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)합니다.  
  
## <a name="example"></a>예제  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/addhandler-statement_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [RemoveHandler 문](../../../visual-basic/language-reference/statements/removehandler-statement.md)  
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)  
 [이벤트](../../../visual-basic/programming-guide/language-features/events/index.md)
