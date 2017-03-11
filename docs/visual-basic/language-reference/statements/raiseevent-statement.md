---
title: "RaiseEvent Statement | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.RaiseEventMethod"
  - "vb.RaiseEvent"
  - "RaiseEvent"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "raising events, RaiseEvent statement"
  - "RaiseEvent statement"
  - "event handlers, connecting events to"
ms.assetid: f82e380a-1e6b-4047-bea8-c853f4d2c742
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# RaiseEvent Statement
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

모듈 수준에서 클래스, 폼 또는 문서 내에 선언된 이벤트를 트리거합니다.  
  
## 구문  
  
```  
RaiseEvent eventname[( argumentlist )]  
```  
  
## 요소  
 `eventname`  
 필수 요소.  트리거할 이벤트의 이름입니다.  
  
 `argumentlist`  
 선택적 요소.  변수, 배열 또는 식의 쉼표로 구분된 목록입니다.  `argumentlist` 인수는 괄호로 묶어야 합니다.  인수가 없으면 괄호도 없어야 합니다.  
  
## 설명  
 필수적 요소인 `eventname`은 모듈 내에 선언된 이벤트의 이름으로  Visual Basic 변수 명명 규칙을 따릅니다.  
  
 이벤트가 발생한 모듈 내에 이벤트가 선언되지 않는 경우 오류가 발생합니다.  다음 코드 조각에서는 이벤트가 발생한 이벤트 선언과 프로시저에 대해 설명합니다.  
  
 [!code-vb[VbVbalrEvents#37](../../../visual-basic/language-reference/statements/codesnippet/visualbasic/VbVbalrEvents/Class1.vb#37)]  
  
 모듈 내에서 명시적으로 선언되지 않은 이벤트를 발생시킬 때는 `RaiseEvent`를 사용할 수 없습니다.  예를 들어, 모든 폼은 <xref:System.Windows.Forms.Form?displayProperty=fullName>에서 <xref:System.Windows.Forms.Control.Click> 이벤트를 상속하므로 파생된 폼에서 `RaiseEvent`를 사용하여 이벤트를 발생시킬 수 없습니다.  폼 모듈 내에 `Click` 이벤트를 선언하는 경우 폼 자체의 <xref:System.Windows.Forms.Control.Click> 이벤트는 숨겨집니다.  이때 폼의 <xref:System.Windows.Forms.Control.Click> 이벤트를 호출하려면 <xref:System.Windows.Forms.Control.OnClick%2A> 메서드를 호출합니다.  
  
 기본적으로 Visual Basic에서 정의한 이벤트는 연결이 설정된 순서대로 해당 이벤트 처리기를 호출합니다.  이벤트에 `ByRef` 매개 변수가 있을 수 있으므로 나중에 연결되는 프로세스는 먼저 호출된 이벤트 처리기에 의해 변경된 매개 변수를 받을 수도 있습니다.  이벤트 처리기가 실행된 후 컨트롤은 이벤트를 발생시킨 서브루틴으로 반환됩니다.  
  
> [!NOTE]
>  공유되지 않는 이벤트는 해당 이벤트가 선언된 클래스의 생성자 내에서 발생하면 안 됩니다.  이러한 이벤트는 런타임 오류를 발생시키지는 않지만 연결된 이벤트 처리기가 이러한 이벤트를 catch하지 못할 수 있습니다.  생성자에서 이벤트를 발생시켜야 하는 경우 `Shared` 한정자를 사용하여 공유 이벤트를 만듭니다.  
  
> [!NOTE]
>  사용자 지정 이벤트를 정의하여 이벤트의 기본 동작을 변경할 수 있습니다.  사용자 지정 이벤트의 경우 `RaiseEvent` 문이 이벤트의 `RaiseEvent` 접근자를 호출합니다.  사용자 지정 이벤트에 대한 자세한 내용은 [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md)을 참조하십시오.  
  
## 예제  
 다음 예제에서는 이벤트를 사용하여 10~0까지 초를 카운트다운합니다.  이 코드는 몇 가지의 이벤트 관련 메서드, 속성 및 문\(`RaiseEvent` 문 포함\)을 보여 줍니다.  
  
 이벤트를 발생시키는 클래스는 이벤트 소스이고 해당 이벤트를 처리하는 메서드는 이벤트 처리기입니다.  이벤트 소스에는 생성되는 이벤트에 대한 처리기를 여러 개 가질 수 있습니다.  클래스가 이벤트를 발생시키는 경우 개체의 해당 인스턴스에 대해 이벤트를 처리하도록 선택된 모든 클래스에서 해당 이벤트가 발생합니다.  
  
 또한 이 예제에서는 하나의 단추\(`Button1`\)와 하나의 텍스트 상자\(`TextBox1`\)가 있는 폼\(`Form1`\)을 사용합니다.  단추를 클릭하면 첫 번째 텍스트 상자에 10초에서 0초까지의 카운트다운이 표시됩니다.  전체 시간\(10초\)이 경과하면 첫 번째 텍스트 상자에 "Done"이 표시됩니다.  
  
 `Form1`의 코드는 폼의 초기 상태 및 종료 상태를 지정합니다.  또한 여기에는 이벤트가 발생할 때 실행되는 코드도 포함되어 있습니다.  
  
 이 예제를 사용하려면 새 Windows 응용 프로그램 프로젝트를 열고 `Button1`이라는 단추와 `TextBox1`이라는 텍스트 상자를 `Form1`이라는 기본 폼에 추가합니다.  그런 다음 폼을 마우스 오른쪽 단추로 클릭하고 **코드 보기**를 클릭하여 코드 편집기를 엽니다.  
  
 `WithEvents` 변수를 `Form1` 클래스의 선언 섹션에 추가합니다.  
  
 [!code-vb[VbVbalrEvents#14](../../../visual-basic/language-reference/statements/codesnippet/visualbasic/VbVbalrEvents/Class1.vb#14)]  
  
## 예제  
 `Form1` 코드에 다음 코드를 추가합니다.  `Form_Load` 또는 `Button_Click` 등과 같이 있을 수 있는 모든 중복 프로시저를 바꿉니다.  
  
 [!code-vb[VbVbalrEvents#15](../../../visual-basic/language-reference/statements/codesnippet/visualbasic/VbVbalrEvents/Class1.vb#15)]  
  
 F5 키를 눌러 이 예제를 실행하고 **Start** 단추를 클릭합니다.  첫 번째 텍스트 상자에 카운트다운이 시작됩니다.  전체 시간\(10초\)이 경과하면 첫 번째 텍스트 상자에 "Done"이 표시됩니다.  
  
> [!NOTE]
>  `My.Application.DoEvents` 메서드는 폼의 이벤트 처리 방식대로 이벤트를 처리하지 않습니다.  폼에서 이벤트를 직접 처리하도록 하려면 다중 스레딩을 사용합니다.  자세한 내용은 [스레딩](../Topic/Threading%20\(C%23%20and%20Visual%20Basic\).md)을 참조하십시오.  
  
## 참고 항목  
 [Events](../../../visual-basic/programming-guide/language-features/events/events.md)   
 [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md)   
 [AddHandler Statement](../../../visual-basic/language-reference/statements/addhandler-statement.md)   
 [RemoveHandler Statement](../../../visual-basic/language-reference/statements/removehandler-statement.md)   
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)