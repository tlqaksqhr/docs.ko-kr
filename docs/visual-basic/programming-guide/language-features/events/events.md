---
title: "Events (Visual Basic) | Microsoft Docs"
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
  - "events [Visual Basic], about events"
  - "events [Visual Basic]"
ms.assetid: 8fb0353a-e41b-4e23-b78f-da65db832f70
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Events (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../../../csharp/includes/vsprvs_md.md)] 프로젝트를 순서대로 실행되는 일련의 프로시저로 시각화할 수 있지만 실제로 대부분의 프로그램은 이벤트 구동 방식이므로 *이벤트*라는 외부 발생 요인에 따라 실행 흐름이 결정됩니다.  
  
 이벤트는 중요한 사항이 발생했음을 응용 프로그램에 알리는 신호입니다.  예를 들어, 사용자가 폼에 있는 컨트롤을 클릭하면 해당 폼은 `Click` 이벤트를 발생시키고 이 이벤트를 처리하는 프로시저를 호출합니다.  또한 이벤트는 별개의 작업들이 서로 통신할 수 있도록 합니다.  예를 들어, 응용 프로그램이 주 응용 프로그램과는 별도로 정렬 작업을 수행하는 경우  사용자가 정렬을 취소하면 응용 프로그램에서는 정렬 프로세스를 중지하도록 지시하는 cancel 이벤트를 보냅니다.  
  
## 이벤트 관련 용어 및 개념  
 이 단원에서는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에 사용되는 이벤트 관련 용어 및 개념에 대해 설명합니다.  
  
### 이벤트 선언  
 이벤트는 다음 예제에서와 같이 `Event` 키워드를 사용하여 클래스, 구조체, 모듈 및 인터페이스 내에 선언됩니다.  
  
 [!code-vb[VbVbalrEvents#24](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_1.vb)]  
  
### 이벤트 발생  
 이벤트는 중요한 사항이 발생했음을 알리는 메시지와 같으며,  이러한 메시지를 브로드캐스팅하는 동작을 일컬어 이벤트를 *발생*시킨다고 합니다.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 다음 예제와 같이 `RaiseEvent` 문을 사용하여 이벤트를 발생시킵니다.  
  
 [!code-vb[VbVbalrEvents#25](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_2.vb)]  
  
 이벤트는 선언된 클래스, 모듈 또는 구조체의 범위 내에서 발생되어야 합니다.  예를 들어, 파생 클래스는 기본 클래스에서 상속된 이벤트를 발생시킬 수 없습니다.  
  
### 이벤트 전송자  
 이벤트를 발생시킬 수 있는 개체를 *이벤트 전송자* 또는 *이벤트 소스*라고 합니다.  이벤트 전송자의 예로는 폼, 컨트롤 및 사용자 정의 개체가 있습니다.  
  
### 이벤트 처리기  
 *이벤트 처리기*는 해당되는 이벤트가 발생할 때 호출되는 프로시저입니다.  시그니처가 일치하는 모든 유효한 서브루틴의 경우 이벤트 처리기로 사용할 수 있지만  함수의 경우 이벤트 소스에 값을 반환하지 않기 때문에 이벤트 처리기로 사용될 수 없습니다.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 이벤트 처리기에 대해 해당 이벤트 전송자의 이름, 밑줄 및 이벤트 이름을 결합하는 표준 명명 규칙을 사용합니다.  예를 들어, `button1`이라는 단추의 `Click` 이벤트의 이름은 `Sub button1_Click`으로 지정됩니다.  
  
> [!NOTE]
>  사용자의 이벤트에 대해 이벤트 처리기를 정의할 때에는 이 명명 규칙을 사용하는 것이 좋습니다. 그러나 유효한 서브루틴 이름을 임의로 사용할 수도 있습니다.  
  
## 이벤트와 이벤트 처리기 연결  
 이벤트 처리기를 사용하려면 먼저 `Handles` 문이나 `AddHandler` 문을 사용하여 해당 이벤트 처리기와 이벤트를 연결해야 합니다.  
  
### WithEvents 및 Handles 절  
 `WithEvents` 문과 `Handles` 절을 사용하여 선언함으로써 이벤트 처리기를 지정할 수 있습니다.  `WithEvents` 키워드를 사용하여 선언된 개체가 발생시킨 이벤트는 다음과 같이 이 이벤트에 대한 `Handles` 문이 포함된 프로시저에서 처리될 수 있습니다.  
  
 [!code-vb[VbVbalrEvents#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_3.vb)]  
  
 일반적으로 `WithEvents` 문과 `Handles` 절의 선언 구문을 사용하면 이벤트 처리 시 쉽게 코딩, 읽기 및 디버깅할 수 있기 때문에 이벤트 처리기에 대해 WithEvents 문과 Handles 절을 사용하는 것이 가장 좋습니다.  그러나 `WithEvents` 변수를 사용할 때에는 다음과 같은 제한 사항이 있습니다.  
  
-   `WithEvents` 변수를 개체 변수로 사용할 수 없습니다.  즉, 이 변수를 `Object`로 선언할 수는 없으며 변수 선언 시 클래스 이름을 지정해야 합니다.  
  
-   공유 이벤트는  `` 클래스 인스턴스에 연결되지 않으므로 `WithEvents`를 사용하여 공유 이벤트를 선언적으로 처리할 수 없습니다.  마찬가지로, `WithEvents` 또는 `Handles`을 사용하여 `Structure`에서 이벤트를 처리할 수 없습니다.  두 경우 모두 `AddHandler` 문을 사용하여 공유 이벤트를 처리할 수 있습니다.  
  
-   `WithEvents` 변수의 배열을 만들 수 없습니다.  
  
 `WithEvents` 변수를 사용하면 하나의 이벤트 처리기가 한 종류 이상의 이벤트를 처리하거나 하나 이상의 이벤트 처리기가 같은 종류의 이벤트를 처리할 수 있습니다.  
  
 `Handles` 절은 이벤트와 이벤트 처리기를 연결하는 표준 방법이지만 컴파일 타임에 연결하는 것은 제한됩니다.  
  
 폼이나 컨트롤과 연결된 이벤트 등의 경우에는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서 자동으로 빈 이벤트 처리기와의 연결을 끊고 이를 이벤트와 연결합니다.  예를 들어, 디자인 모드에서 폼에 있는 명령 단추를 두 번 클릭하면 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서 다음 코드와 같이 해당 명령 단추에 대해 빈 이벤트 처리기와 `WithEvents` 변수를 만듭니다.  
  
 [!code-vb[VbVbalrEvents#26](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_4.vb)]  
  
### AddHandler 및 RemoveHandler  
 `AddHandler` 문과 `Handles` 절은 둘 다 이벤트를 처리할 이벤트 처리기를 지정할 수 있다는 점에서 비슷합니다.  그러나 `AddHandler`와 `RemoveHandler`는 이벤트와 관련된 이벤트 처리기를 동적으로 추가, 제거 및 변경할 수 있으므로 `Handles` 절보다 좀 더 융통성을 제공합니다.  공유 이벤트나 구조체 이벤트를 처리하려면 `AddHandler`를 사용해야 합니다.  
  
 `AddHandler`에는 두 가지 인수, 즉 컨트롤 등의 이벤트 전송자에서 보낸 이벤트의 이름과 대리자로 평가되는 식이 사용됩니다.  `AddressOf` 문이 항상 대리자에 대한 참조를 반환하므로 `AddHandler`를 사용할 때에는 대리자 클래스를 명시적으로 지정하지 않아도 됩니다.  다음 예제에서는 이벤트 처리기와 개체가 발생시킨 이벤트를 연결합니다.  
  
 [!code-vb[VbVbalrEvents#28](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_5.vb)]  
  
 이벤트 처리기와 이벤트의 연결을 끊는 `RemoveHandler`는 `AddHandler`와 같은 구문을 사용합니다.  예를 들면 다음과 같습니다.  
  
 [!code-vb[VbVbalrEvents#29](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_6.vb)]  
  
 다음 예제에서는 이벤트 처리기가 이벤트와 연결되고 해당 이벤트가 발생합니다.  이벤트 처리기는 이벤트를 catch하고 메시지를 표시합니다.  
  
 그런 다음 첫 번째 이벤트 처리기가 제거되고 다른 이벤트 처리기가 이벤트와 연결됩니다.  이벤트가 다시 발생하면 다른 메시지가 표시됩니다.  
  
 마지막으로, 두 번째 이벤트 처리기가 제거되고 이벤트가 세 번째로 발생합니다.  더 이상 이벤트와 연결된 이벤트 처리기가 없으므로 아무 작업도 수행되지 않습니다.  
  
 [!code-vb[VbVbalrEvents#38](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_7.vb)]  
  
## 기본 클래스에서 상속된 이벤트 처리  
 *파생 클래스*는 기본 클래스의 특징을 상속받는 클래스입니다. 파생 클래스에서는 `Handles` `MyBase` 문을 사용하여 기본 클래스에서 발생시킨 이벤트를 처리할 수 있습니다.  
  
#### 기본 클래스에서 발생된 이벤트를 처리하려면  
  
-   파생 클래스에서 이벤트 처리기 프로시저의 선언 줄에 `Handles MyBase.`*eventname* 문을 추가하여 이벤트 처리기를 선언합니다. 여기서 *eventname*은 처리할 기본 클래스의 이벤트 이름입니다.  예를 들면 다음과 같습니다.  
  
     [!code-vb[VbVbalrEvents#12](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_8.vb)]  
  
## 관련 단원  
  
|제목|설명|  
|--------|--------|  
|[Walkthrough: Declaring and Raising Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)|클래스에 대한 이벤트를 선언하고 발생시키는 방법을 단계별로 설명합니다.|  
|[Walkthrough: Handling Events](../Topic/Walkthrough:%20Handling%20Events%20\(Visual%20Basic\).md)|이벤트 처리기 프로시저를 작성하는 방법을 보여 줍니다.|  
|[How to: Declare Custom Events To Avoid Blocking](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)|이벤트 처리기를 비동기적으로 호출할 수 있는 사용자 지정 이벤트를 정의하는 방법을 보여 줍니다.|  
|[How to: Declare Custom Events To Conserve Memory](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)|이벤트를 처리할 때만 메모리를 사용하는 사용자 지정 이벤트를 정의하는 방법을 보여 줍니다.|  
|[Troubleshooting Inherited Event Handlers in Visual Basic](../../../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)|상속된 구성 요소의 이벤트 처리기에서 발생하는 일반적인 문제를 설명합니다.|  
|[이벤트](../Topic/Handling%20and%20Raising%20Events.md)|[!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)]의 이벤트 모델에 대해 간략하게 설명합니다.|  
|[Windows Forms에서 이벤트 처리기 만들기](../Topic/Creating%20Event%20Handlers%20in%20Windows%20Forms.md)|Windows Forms 개체와 관련된 이벤트를 사용하여 작업하는 방법에 대해 설명합니다.|  
|[Delegates](../../../../visual-basic/programming-guide/language-features/delegates/delegates.md)|Visual Basic의 대리자에 대해 간략하게 설명합니다.|