---
title: "AddHandler 문 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
dev_langs:
- VB
helpviewer_keywords:
- AddHandler statement
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
caps.latest.revision: 15
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
ms.openlocfilehash: 728d8393c44d777f9cc016d9cf66030036582ae4
ms.lasthandoff: 03/13/2017

---
# <a name="addhandler-statement"></a>AddHandler 문
런타임 시 이벤트 처리기와 이벤트를 연결합니다.  
  
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
  
 시그니처는 `eventhandler` 프로시저는 이벤트의 시그니처와 일치 해야 `event`합니다.  
  
 `Handles` 키워드와 `AddHandler` 문 모두 특정 프로시저에서 특정 이벤트를 처리하도록 지정하는 데 사용할 수 있지만 차이가 있습니다. `AddHandler` 문은 런타임에 프로시저를 이벤트에 연결합니다. 특정 이벤트를 처리하도록 지정하는 프로시저를 정의할 때 `Handles` 키워드를 사용합니다. 자세한 내용은 참조 [처리](../../../visual-basic/language-reference/statements/handles-clause.md)합니다.  
  
> [!NOTE]
>  사용자 지정 이벤트는 `AddHandler` 문은 이벤트의 호출 `AddHandler` 접근자입니다. 사용자 지정 이벤트에 대 한 자세한 내용은 참조 하십시오. [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)합니다.  
  
## <a name="example"></a>예제  
 [!code-vb[VbVbalrEvents #&17;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/addhandler-statement_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [RemoveHandler 문](../../../visual-basic/language-reference/statements/removehandler-statement.md)   
 [핸들](../../../visual-basic/language-reference/statements/handles-clause.md)   
 [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)   
 [이벤트](../../../visual-basic/programming-guide/language-features/events/index.md)
