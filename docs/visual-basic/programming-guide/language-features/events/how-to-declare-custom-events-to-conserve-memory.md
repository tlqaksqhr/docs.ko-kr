---
title: "방법: (Visual Basic) 메모리를 절약 하기 위해 사용자 지정 이벤트 선언 | Microsoft 문서"
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
- declaring events, custom
- events [Visual Basic], custom
- custom events
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
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
ms.openlocfilehash: 4f8ce32a3b4da411a73010119283ce9661b82a6c
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a>방법: 메모리를 절약하는 사용자 지정 이벤트 선언(Visual Basic)
이 응용 프로그램 메모리 사용을 낮게 유지 하는 중요 한 몇 가지 경우가 있습니다. 사용자 지정 이벤트를 처리 하는 이벤트에 대해서만 메모리를 사용 하 여 응용 프로그램을 수 있습니다.  
  
 기본적으로 컴파일러는 클래스에서 이벤트를 선언 이벤트 정보를 저장 하는 필드에 대 한 메모리를 할당 합니다. 클래스에 사용 하지 않는 이벤트 수, 메모리를 불필요 하 게 수행 합니다.  
  
 Visual Basic에서 제공 하는 이벤트의 기본 구현을 사용 하 여, 대신 메모리 사용을 신중 하 게 관리 하려면 사용자 지정 이벤트를 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 클래스의 인스턴스 하나를 사용는 <xref:System.ComponentModel.EventHandlerList>에 저장 된 클래스는 `Events` 필드를 사용 하 여의 이벤트에 대 한 정보를 저장 합니다.</xref:System.ComponentModel.EventHandlerList> <xref:System.ComponentModel.EventHandlerList>클래스가 대리자를 보관 하도록 최적화 된 목록 클래스입니다.</xref:System.ComponentModel.EventHandlerList>  
  
 클래스 사용에 대 한 모든 이벤트는 `Events` 각 이벤트를 처리 하는 방법에 대해 추적 하는 필드입니다.  
  
 [!code-vb[VbVbalrEvents #&22;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-conserve-memory_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ComponentModel.EventHandlerList></xref:System.ComponentModel.EventHandlerList>   
 [이벤트](../../../../visual-basic/programming-guide/language-features/events/index.md)   
 [방법: 차단을 방지하는 사용자 지정 이벤트 선언](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)
