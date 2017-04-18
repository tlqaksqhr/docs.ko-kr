---
title: "이벤트 &quot;&lt;행사 이름&1;&gt;&quot;이벤트를 구현할 수 없습니다&quot;&lt;eventname2&gt;인터페이스&quot; &quot;에&lt;인터페이스&gt;&quot; 때문에 대리자 형식&lt;delegate1&gt;&quot;및&quot;&lt;delegate2&gt;&quot; 일치 하지 않는 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31423
- bc31423
dev_langs:
- VB
helpviewer_keywords:
- BC31423
ms.assetid: 2e754b66-5836-48ff-9697-b9c0d7085f18
caps.latest.revision: 6
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
ms.openlocfilehash: b6253b3e9ad07c3715c55a8cfd0891792b45a452
ms.lasthandoff: 03/13/2017

---
# <a name="event-39lteventname1gt39-cannot-implement-event-39lteventname2gt39-on-interface-39ltinterfacegt39-because-their-delegate-types-39ltdelegate1gt39-and-39ltdelegate2gt39-do-not-match"></a>이벤트 '&lt;행사 이름&1;&gt;'이벤트를 구현할 수 없습니다'&lt;eventname2&gt;인터페이스' '에&lt;인터페이스&gt;' 때문에 대리자 형식&lt;delegate1&gt;'및'&lt;delegate2&gt;' 일치 하지 않습니다
[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]이벤트의 대리자 형식이 인터페이스에서 이벤트의 대리자 형식과 일치 하지 않으므로 이벤트를 구현할 수 없습니다. 이 오류는 인터페이스에서 여러 이벤트를 정의한 다음 동일한 이벤트로 함께 구현하려고 하는 경우에 발생할 수 있습니다. 구현된 모든 이벤트가 `As` 구문을 사용하여 선언되고 동일한 대리자 형식을 지정하는 경우에만 이벤트에서 둘 이상의 이벤트를 구현할 수 있습니다.  
  
 **오류 ID:** BC31423  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   이벤트를 개별적으로 구현합니다.  
  
     또는  
  
-   사용 하 여 인터페이스의 이벤트를 정의 `As` 구문 동일한 대리자 형식을 지정 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)   
 [Delegate 문](../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [이벤트](../../../visual-basic/programming-guide/language-features/events/index.md)
