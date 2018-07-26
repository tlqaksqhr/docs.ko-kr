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
ms.openlocfilehash: bc0dce442db9d62b9fbee857b6e711696ad87fb8
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37936817"
---
# <a name="addhandler-statement"></a>AddHandler 문
런타임에 이벤트 처리기를 사용 하 여 이벤트를 연결합니다.  
  
## <a name="syntax"></a>구문  
  
```  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>요소  
|||
|---|---|
|이벤트(event)|처리할 이벤트의 이름입니다.|  
|`eventhandler`|이벤트를 처리 하는 프로시저의 이름입니다.|
|||
  
## <a name="remarks"></a>설명  
 합니다 `AddHandler` 고 `RemoveHandler` 문을 시작 하 고 프로그램 실행 중 언제 든 지 이벤트 처리를 중지할 수 있습니다.  
  
 서명의 합니다 `eventhandler` 프로시저는 이벤트의 시그니처와 일치 해야 `event`합니다.  
  
 `Handles` 키워드와 `AddHandler` 문 모두 특정 프로시저에서 특정 이벤트를 처리하도록 지정하는 데 사용할 수 있지만 차이가 있습니다. `AddHandler` 문은 런타임에 프로시저를 이벤트에 연결합니다. 특정 이벤트를 처리하도록 지정하는 프로시저를 정의할 때 `Handles` 키워드를 사용합니다. 자세한 내용은 [처리](../../../visual-basic/language-reference/statements/handles-clause.md)합니다.  
  
> [!NOTE]
>  사용자 지정 이벤트에 대 한 합니다 `AddHandler` 문은 호출 이벤트의 `AddHandler` 접근자입니다. 사용자 지정 이벤트에 대 한 자세한 내용은 참조 하세요. [이벤트 연결 문으로](../../../visual-basic/language-reference/statements/event-statement.md)합니다.  
  
## <a name="example"></a>예  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/addhandler-statement_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [RemoveHandler 문](../../../visual-basic/language-reference/statements/removehandler-statement.md)  
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)  
 [이벤트](../../../visual-basic/programming-guide/language-features/events/index.md)
