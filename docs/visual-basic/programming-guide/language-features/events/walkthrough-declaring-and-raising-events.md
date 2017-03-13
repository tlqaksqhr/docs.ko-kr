---
title: "Walkthrough: Declaring and Raising Events (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "declarations, events"
  - "events [Visual Basic], walkthroughs"
  - "declaring events, walkthroughs"
  - "events [Visual Basic], declaring"
  - "events [Visual Basic], raising"
  - "raising events, walkthroughs"
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Walkthrough: Declaring and Raising Events (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 연습에서는 `Widget`이라는 클래스에 대한 이벤트를 선언하고 발생시키는 방법을 설명합니다.  이 연습 단계를 완료한 다음 `Widget` 개체의 이벤트를 사용하여 응용 프로그램의 상태 정보를 제공하는 방법을 설명하는 [Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) 항목을 참고할 수 있습니다.  
  
## Widget 클래스  
 예를 들어, `Widget` 클래스가 있는 것으로 가정합니다.  이 `Widget` 클래스에는 실행하는 데 많은 시간이 소요되는 메서드가 있으며 응용 프로그램에 일종의 완료율 표시기를 나타내려고 합니다.  
  
 `Widget` 개체에서도 완료율 대화 상자가 표시되도록 할 수 있지만 이렇게 되면 이후에 `Widget` 클래스를 사용하는 모든 프로젝트에서 이 대화 상자가 나타나게 됩니다.  개체의 전반적인 용도가 폼이나 대화 상자를 관리하기 위한 것이 아니라면 개체를 사용하는 응용 프로그램에서 사용자 인터페이스를 처리하도록 해당 개체를 디자인하는 것이 좋습니다.  
  
 `Widget`은 다른 작업을 수행하는 데 사용됩니다. 따라서 `PercentDone` 이벤트를 추가하고 `Widget`의 메서드를 호출하는 프로시저에서 해당 이벤트를 처리하고 상태 업데이트를 표시하도록 하는 것이 좋습니다.  또한 `PercentDone` 이벤트에서 작업을 취소하는 메커니즘을 제공할 수도 있습니다.  
  
#### 이 항목의 코드 예제를 빌드하려면  
  
1.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] Windows 응용 프로그램 프로젝트를 열고 `Form1`이라는 폼을 만듭니다.  
  
2.  `Form1`에 두 개의 단추와 하나의 레이블을 추가합니다.  
  
3.  다음 표에 표시된 대로 개체를 명명합니다.  
  
    |개체|Property|설정|  
    |--------|--------------|--------|  
    |`Button1`|`Text`|Start Task|  
    |`Button2`|`Text`|Cancel|  
    |`Label`|`(Name)`, `Text`|lblPercentDone, 0|  
  
4.  **프로젝트** 메뉴에서 **클래스 추가**를 선택하여 프로젝트에 `Widget.vb` 클래스를 추가합니다.  
  
#### Widget 클래스에 대한 이벤트를 선언하려면  
  
-   `Event` 키워드를 사용하여 `Widget` 클래스에서 이벤트를 선언합니다.  `Widget`의 `PercentDone` 이벤트에서 볼 수 있는 것처럼 이벤트에 `ByVal` 및 `ByRef` 인수를 사용할 수 있습니다.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_1.vb)]  
  
 호출하는 개체가 `PercentDone` 이벤트를 받으면 `Percent` 인수에는 완료된 작업의 백분율이 포함됩니다.  `Cancel` 인수를 `True`로 설정하여 이벤트를 발생시킨 메서드를 취소할 수 있습니다.  
  
> [!NOTE]
>  프로시저 인수를 선언하는 것과 같은 방식으로 이벤트 인수를 선언할 수 있지만 이벤트에는 `Optional` 또는 `ParamArray` 인수를 사용할 수 없으며 반환 값이 없습니다.  
  
 `PercentDone` 이벤트는 `Widget` 클래스의 `LongTask` 메서드로 인해 발생합니다.  `LongTask`에는 메서드가 작업을 수행하게 될 기간을 나타내는 인수와 `LongTask`가 일시 중지되어 `PercentDone` 이벤트가 발생하기 전의 최소 시간 간격을 나타내는 인수가 사용됩니다.  
  
#### PercentDone 이벤트를 발생시키려면  
  
1.  이 클래스가 사용하는 `Timer` 속성에 간단하게 액세스하려면 클래스 모듈의 선언 부분 맨 위, 즉 `Class Widget` 문 위에 `Imports` 문을 추가합니다.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_2.vb)]  
  
2.  `Widget` 클래스에 다음 코드를 추가합니다.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_3.vb)]  
  
 응용 프로그램에서 `LongTask` 메서드를 호출하는 경우 `Widget` 클래스는 `MinimumInterval`\(초\)마다 `PercentDone` 이벤트를 발생시킵니다.  해당 이벤트가 반환되면 `LongTask`는 `Cancel` 인수가 `True`로 설정되었는지 확인합니다.  
  
 여기에서 몇 가지 사항을 고려해야 합니다.  간단한 처리를 위해 `LongTask` 프로시저에서는 해당 작업을 수행하는 데 소요되는 시간을 사용자가 미리 알고 있는 것으로 가정합니다.  그러나 이러한 경우는 거의 없습니다.  작업을 동일한 크기의 부분으로 나누는 것은 어려운 일이며, 특정 상황이 발생했음을 알기 전까지 경과되는 시간을 줄이는 것이 사용자에게 더 중요한 문제일 수 있습니다.  
  
 또한 이 예제에서 다른 문제가 발생할 수도 있습니다.  `Timer` 속성은 자정 이후의 시간\(초\)을 반환하므로 해당 응용 프로그램이 자정 직전에 시작된 경우에는 중단됩니다.  보다 신중하게 시간을 측정하려면 이와 같은 경계 조건을 고려하거나 `Now`와 같은 속성을 사용하여 경계 조건을 피하도록 합니다.  
  
 이제 `Widget` 클래스로 이벤트를 발생시킬 수 있으므로 다음 연습을 수행해 봅니다.  [Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)에서는 `WithEvents`를 사용하여 이벤트 처리기를 `PercentDone` 이벤트와 연결하는 방법을 보여 줍니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>   
 <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>   
 [Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)   
 [Events](../../../../visual-basic/programming-guide/language-features/events/events.md)