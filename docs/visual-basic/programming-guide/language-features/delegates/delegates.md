---
title: "Delegates (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "delegates [Visual Basic]"
  - "Visual Basic code, delegates"
ms.assetid: 410b60dc-5e60-4ec0-bfae-426755a2ee28
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Delegates (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

대리자는 메서드를 참조하는 개체입니다.  또한 다른 프로그래밍 언어에서 사용되는 함수 포인터와 비슷하기 때문에 종종 *형식이 안전한 함수 포인터*로 설명되기도 합니다.  그러나 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]의 대리자는 함수 포인터와 달리 <xref:System.Delegate?displayProperty=fullName> 클래스를 기반으로 하는 참조 형식입니다.  대리자는 공유 메서드\(클래스의 특정 인스턴스 없이도 호출할 수 있는 메서드\)와 인스턴스 메서드를 모두 참조할 수 있습니다.  
  
## 대리자 및 이벤트  
 대리자는 호출 프로시저와 호출되는 프로시저 간의 매개자가 필요한 경우에 유용합니다.  예를 들어, 이벤트를 발생시키는 개체에서 상황에 따라 서로 다른 이벤트 처리기를 호출할 수 있도록 만들어야 하는 경우가 있습니다.  이 경우 이벤트를 발생시키는 개체는 어느 이벤트 처리기에서 특정 이벤트를 처리하는지 미리 알지 못합니다.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 사용자가 `AddHandler` 문을 사용할 때 대리자를 자동으로 만들어 이벤트 처리기를 이벤트와 동적으로 연결할 수 있게 합니다.  이 대리자는 런타임에 적절한 이벤트 처리기에 대한 호출을 전달합니다.  
  
 사용자가 직접 대리자를 만들 수도 있지만 대부분의 경우에는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서 대리자를 만들어 세부 사항을 관리합니다.  예를 들어, `Event` 문은 `<EventName>EventHandler`라는 대리자 클래스를 해당 이벤트와 동일한 시그니처를 갖는 `Event` 문이 들어 있는 클래스의 중첩 클래스로 암시적으로 정의합니다.  `AddressOf` 문은 특정 프로시저를 참조하는 대리자의 인스턴스를 암시적으로 만들므로  다음 두 줄의 코드는 서로 동일합니다.  첫 번째 줄에서는 인수로 전달된 `Button1_Click` 메서드에 대한 참조를 사용하여 `Eventhandler`의 인스턴스를 만드는 것을 보여 줍니다.  이와 동일한 작업을 두 번째 줄에서는 보다 편리하게 수행할 수 있습니다.  
  
 [!code-vb[VbVbalrDelegates#6](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/delegates_1.vb)]  
  
 컴파일러가 컨텍스트에 따라 대리자의 형식을 확인할 수 있는 모든 위치에서 이와 같이 간단한 방법으로 대리자를 만들 수 있습니다.  
  
## 기존 대리자 형식을 사용하는 이벤트 선언  
 일부 경우에는 기존 대리자 형식을 내부 대리자로 사용하는 이벤트를 선언할 수 있습니다.  다음 구문은 이러한 방법을 보여 줍니다.  
  
 [!code-vb[VbVbalrDelegates#7](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/delegates_2.vb)]  
  
 이 방법은 여러 개의 이벤트를 동일한 처리기에 라우팅하려는 경우에 유용합니다.  
  
## 대리자 변수 및 매개 변수  
 이벤트와 관련되지 않은 기타 작업\(예: 자유 스레딩\) 또는 런타임에 다른 버전의 함수를 호출해야 하는 프로시저에 대리자를 사용할 수 있습니다.  
  
 예를 들어, 자동차 이름이 있는 목록 상자가 포함된 항목별 광고 응용 프로그램이 있습니다.  광고는 대개 자동차 생산업체 이름인 제목을 기준으로 정렬됩니다.  이때 일부 자동차의 경우 생산업체 앞에 연도가 포함되면 문제가 생길 수 있습니다.  목록 상자의 내장 정렬 기능은 문자 코드만을 기준으로 정렬하므로 날짜로 시작하는 광고들을 먼저 표시한 다음 생산업체로 시작하는 광고들을 표시하게 됩니다.  
  
 이 문제를 해결하려면 대부분의 목록 상자에 표준 영문자 정렬을 사용하고 런타임에 자동차 광고에 대해서는 사용자 지정 정렬 프로시저로 전환할 수 있는 클래스에 정렬 프로시저를 만듭니다.  이 작업을 수행하려면 대리자를 사용하여 런타임에 사용자 지정 정렬 프로시저를 정렬 클래스에 전달합니다.  
  
## AddressOf 및 람다 식  
 각 대리자 클래스는 개체 메서드의 사양이 전달되는 생성자를 정의합니다.  대리자 생성자의 인수는 메서드에 대한 참조이거나 람다 식이어야 합니다.  
  
 메서드에 대한 참조를 지정하려면 다음 구문을 사용합니다.  
  
 `AddressOf` \[`expression`.\]`methodName`  
  
 `expression`의 컴파일 타임 형식은 지정된 이름의 시그니처가 대리자 클래스의 시그니처와 일치하는 메서드가 포함된 클래스 또는 인터페이스의 이름이어야 합니다.  `methodName`은 공유 메서드 또는 인스턴스 메서드가 될 수 있습니다.  `methodName`은 클래스의 기본 메서드에 대한 대리자를 만드는 경우에도 반드시 지정해야 합니다.  
  
 람다 식을 지정하려면 다음 구문을 사용합니다.  
  
 `Function` \(\[`parm` As `type`, `parm2` As `type2`, ...\]\) `expression`  
  
 다음 예제에서는 대리자에 대한 참조를 지정하는 데 사용되는 `AddressOf` 및 람다 식을 보여 줍니다.  
  
 [!code-vb[VbVbalrDelegates#15](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/delegates_3.vb)]  
  
 함수의 시그니처는 대리자 형식의 시그니처와 일치해야 합니다.  람다 식에 대한 자세한 내용은 [Lambda Expressions](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)을 참조하십시오.  대리자에 대한 람다 식 및 `AddressOf` 할당에 대한 추가 예제는 [Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)을 참조하십시오.  
  
## 관련 항목  
  
|제목|설명|  
|--------|--------|  
|[How to: Invoke a Delegate Method](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)|메서드와 대리자를 연결한 다음 대리자를 통해 해당 메서드를 호출하는 방법을 보여 주는 예제를 제공합니다.|  
|[How to: Pass Procedures to Another Procedure in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)|대리자를 사용하여 한 프로시저를 다른 프로시저에 전달하는 방법을 보여 줍니다.|  
|[Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)|시그니처가 동일하지 않은 경우에도 대리자나 처리기에 sub 및 함수를 할당하는 방법을 설명합니다.|  
|[Events](../../../../visual-basic/programming-guide/language-features/events/events.md)|Visual Basic의 이벤트에 대해 간략하게 설명합니다.|