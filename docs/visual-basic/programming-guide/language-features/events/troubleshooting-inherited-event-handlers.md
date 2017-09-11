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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: f64395975821226d42664bbf78b04120d49a38bc
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a><span data-ttu-id="dacc3-102">Visual Basic에서 상속된 이벤트 처리기 관련 문제 해결</span><span class="sxs-lookup"><span data-stu-id="dacc3-102">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>
<span data-ttu-id="dacc3-103">이 항목에서는 이벤트 처리기 상속 된 구성 요소에서 발생 하는 일반적인 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="dacc3-103">This topic lists common issues that arise with event handlers in inherited components.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="dacc3-104">절차</span><span class="sxs-lookup"><span data-stu-id="dacc3-104">Procedures</span></span>  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a><span data-ttu-id="dacc3-105">이벤트 처리기의 코드는 모든 호출에 대 한 두 번 실행</span><span class="sxs-lookup"><span data-stu-id="dacc3-105">Code in Event Handler Executes Twice for Every Call</span></span>  
  
-   <span data-ttu-id="dacc3-106">상속된 된 이벤트 처리기를 포함 하지 않아야는 [처리](../../../../visual-basic/language-reference/statements/handles-clause.md) 절.</span><span class="sxs-lookup"><span data-stu-id="dacc3-106">An inherited event handler must not include a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause.</span></span> <span data-ttu-id="dacc3-107">기본 클래스의 메서드는 이벤트와 이미 연결 되어 하 고 그에 따라 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dacc3-107">The method in the base class is already associated with the event and will fire accordingly.</span></span> <span data-ttu-id="dacc3-108">제거는 `Handles` 상속 된 메서드에서 절.</span><span class="sxs-lookup"><span data-stu-id="dacc3-108">Remove the `Handles` clause from the inherited method.</span></span>  
  
     <span data-ttu-id="dacc3-109">[!code-vb[VbVbalrEvents #&32;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/troubleshooting-inherited-event-handlers_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="dacc3-109">[!code-vb[VbVbalrEvents#32](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/troubleshooting-inherited-event-handlers_1.vb)]</span></span>  
  
-   <span data-ttu-id="dacc3-110">상속 된 메서드가 없는 경우는 `Handles` 키워드를 코드는 포함 되지 않았는지 확인 [AddHandler 문](../../../../visual-basic/language-reference/statements/addhandler-statement.md) 또는 동일한 이벤트를 처리 하는 추가 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dacc3-110">If the inherited method does not have a `Handles` keyword, verify that your code does not contain an extra [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) or any additional methods that handle the same event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dacc3-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dacc3-111">See Also</span></span>  
 [<span data-ttu-id="dacc3-112">이벤트</span><span class="sxs-lookup"><span data-stu-id="dacc3-112">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
