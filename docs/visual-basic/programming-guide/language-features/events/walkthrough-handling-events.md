---
title: "Walkthrough: Handling Events (Visual Basic) | Microsoft Docs"
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
  - "event handling [Visual Basic], walkthroughs"
  - "walkthroughs [Visual Basic], event handling"
  - "variables [Visual Basic], WithEvents"
  - "events [Visual Basic], walkthroughs"
  - "WithEvents keyword, walkthroughs"
  - "event handlers [Visual Basic], walkthroughs"
ms.assetid: f145b3fc-5ae0-4509-a2aa-1ff6934706bd
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Walkthrough: Handling Events (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 연습 과정은 이벤트로 작업하는 방법을 설명하는 두 번째 항목입니다.  첫 번째 항목인 [연습: 이벤트 선언 및 발생](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)에서는 이벤트를 선언하고 발생시키는 방법을 설명합니다.  이 단원에서는 첫 번째 연습 과정의 폼과 클래스를 사용하여 발생하는 이벤트를 처리하는 방법을 설명합니다.  
  
 `Widget` 클래스 예제에서는 일반적인 이벤트 처리 문을 사용합니다.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 다른 기술을 사용하여 이벤트 작업을 수행할 수 있습니다.  연습으로 `AddHandler` 및 `Handles` 문을 사용하도록 이 예제를 수정할 수 있습니다.  
  
### Widget 클래스의 PercentDone 이벤트를 처리하려면  
  
1.  `Form1`에 다음과 같은 코드를 입력합니다.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#4](../../../../visual-basic/programming-guide/language-features/events/codesnippet/visualbasic/VbEventWalkthrough/Form1.vb#4)]  
  
     `WithEvents` 키워드는 변수 `mWidget`을 사용하여 개체의 이벤트를 처리하도록 지정합니다.  개체의 종류를 지정하려면 개체가 만들어지는 클래스의 이름을 제공합니다.  
  
     `WithEvents` 변수가 클래스 수준이어야 하므로 `mWidget` 변수는 `Form1`에 선언됩니다.  이는 변수가 배치되는 클래스 형식에 관계없이 적용됩니다.  
  
     변수 `mblnCancel`은 `LongTask` 메서드를 취소하는 데 사용됩니다.  
  
## 이벤트를 처리하는 코드 작성  
 `WithEvents`를 사용하여 변수를 선언하면 즉시 클래스 **코드 편집기**의 왼쪽 드롭다운 목록에 해당 변수 이름이 나타납니다.  `mWidget`을 선택하면 `Widget` 클래스의 이벤트가 오른쪽 드롭다운 목록에 나타납니다.  이벤트를 선택하면 접두사 `mWidget`과 밑줄이 표시된 해당 이벤트 프로시저가 나타납니다.  `WithEvents` 변수와 연관된 모든 이벤트 프로시저에는 변수 이름이 접두사로 제공됩니다.  
  
#### 이벤트를 처리하려면  
  
1.  **코드 편집기**의 왼쪽 드롭다운 목록에서 `mWidget`을 선택합니다.  
  
2.  오른쪽 드롭다운 목록에서 `PercentDone` 이벤트를 선택합니다.  **코드 편집기**에서 `mWidget_PercentDone` 이벤트 프로시저가 열립니다.  
  
    > [!NOTE]
    >  새 이벤트 처리기를 삽일할 때 **코드 편집기**가 유용하지만 반드시 필요한 것은 아닙니다.  이 연습에서는 이벤트 처리기를 직접 코드에 복사하는 것이 보다 쉽습니다.  
  
3.  `mWidget_PercentDone` 이벤트 처리기에 다음 코드를 추가합니다.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#5](../../../../visual-basic/programming-guide/language-features/events/codesnippet/visualbasic/VbEventWalkthrough/Form1.vb#5)]  
  
     `PercentDone` 이벤트가 발생할 때마다 이벤트 프로시저는 `Label` 컨트롤에 완료율을 표시합니다.  `DoEvents` 메서드를 사용하면 레이블을 다시 그릴 수 있으며 **Cancel** 단추를 클릭할 수도 있습니다.  
  
4.  `Button2_Click` 이벤트 처리기에 다음 코드를 추가합니다.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#6](../../../../visual-basic/programming-guide/language-features/events/codesnippet/visualbasic/VbEventWalkthrough/Form1.vb#6)]  
  
 `LongTask`가 실행되는 동안 **Cancel** 단추를 클릭하면 `DoEvents` 문을 통해 이벤트가 처리되는 즉시 `Button2_Click` 이벤트가 실행됩니다.  클래스 수준 변수 `mblnCancel`이 `True`로 설정되고 `mWidget_PercentDone` 이벤트에서 해당 변수를 테스트한 다음 `ByRef Cancel` 인수를 `True`로 설정합니다.  
  
## 개체에 WithEvents 변수 연결  
 `Form1`이 `Widget` 개체의 이벤트를 처리하도록 설정된 다음에는  `Widget`을 찾아야 합니다.  
  
 디자인 타임에서 변수 `WithEvents`를 선언하는 경우 해당 변수는 개체와 연관되지 않습니다.  `WithEvents` 변수는 다른 모든 개체 변수와 같습니다.  따라서 개체를 만든 다음 `WithEvents` 변수를 사용하여 해당 개체에 참조를 할당해야 합니다.  
  
#### 개체를 만들고 해당 개체에 참조를 할당하려면  
  
1.  **코드 편집기**의 왼쪽 드롭다운 목록에서 **\(Form1 이벤트\)**를 선택합니다.  
  
2.  오른쪽 드롭다운 목록에서 `Load` 이벤트를 선택합니다.  **코드 편집기**에서 `Form1_Load` 이벤트 프로시저가 열립니다.  
  
3.  다음 코드를 `Form1_Load` 이벤트 프로시저에 추가하여 `Widget`을 만듭니다.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#7](../../../../visual-basic/programming-guide/language-features/events/codesnippet/visualbasic/VbEventWalkthrough/Form1.vb#7)]  
  
 이 코드가 실행되면 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 `Widget` 개체를 만들고 `mWidget`과 연관된 이벤트 프로시저에 해당 이벤트를 연결합니다.  이 때부터 `Widget`이 해당 `PercentDone` 이벤트를 발생시킬 때마다 `mWidget_PercentDone` 이벤트 프로시저가 실행됩니다.  
  
#### LongTask 메서드를 호출하려면  
  
-   `Button1_Click` 이벤트 처리기에 다음 코드를 추가합니다.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#8](../../../../visual-basic/programming-guide/language-features/events/codesnippet/visualbasic/VbEventWalkthrough/Form1.vb#8)]  
  
 `LongTask` 메서드를 호출하기 전에 완료율을 표시하는 레이블을 초기화해야 하며 해당 메서드를 취소하는 클래스 수준의 `Boolean` 플래그를 `False`로 설정해야 합니다.  
  
 `LongTask`는 12.2초의 작업 기간으로 호출됩니다.  `PercentDone` 이벤트는 1\/3초마다 한 번씩 발생합니다.  해당 이벤트가 발생할 때마다 `mWidget_PercentDone` 이벤트 프로시저가 실행됩니다.  
  
 `LongTask`가 완료되면 `mblnCancel`을 테스트하여 `LongTask`가 정상적으로 종료되었는지, 아니면 `mblnCancel`이 `True`로 설정되어 LongTask가 중단되었는지를 확인합니다.  완료율은 LongTask가 정상적으로 종료된 경우에만 업데이트됩니다.  
  
#### 프로그램을 실행하려면  
  
1.  F5 키를 눌러 프로젝트를 실행 모드로 전환합니다.  
  
2.  **Start Task** 단추를 클릭합니다.  `PercentDone` 이벤트가 발생할 때마다 완료되는 작업의 백분율이 레이블에 새로 표시됩니다.  
  
3.  **Cancel** 단추를 클릭하여 작업을 중지합니다.  **Cancel** 단추를 클릭할 때 이 단추의 모양이 즉시 변경되지는 않습니다.  `My.Application.DoEvents` 문에서 이벤트 처리를 허용해야 `Click` 이벤트가 발생할 수 있습니다.  
  
    > [!NOTE]
    >  `My.Application.DoEvents` 메서드는 폼의 이벤트 처리 방식대로 이벤트를 처리하지 않습니다.  예를 들어, 이 연습에서는 **Cancel** 단추를 두 번 클릭해야 합니다.  폼에서 이벤트를 직접 처리하도록 하려면 다중 스레딩을 사용합니다.  자세한 내용은 [스레딩](../Topic/Threading%20\(C%23%20and%20Visual%20Basic\).md)을 참조하십시오.  
  
 F11 키를 눌러 프로그램을 실행하고 한 번에 한 줄씩 코드를 단계별로 실행하는 방법도 사용할 수 있습니다.  이렇게 하면 `LongTask`가 실행된 다음 `PercentDone` 이벤트가 발생할 때마다 `Form1`이 다시 실행되는 방법을 확인할 수 있습니다.  
  
 `Form1`의 코드가 다시 실행될 때 `LongTask` 메서드를 다시 호출하면 어떻게 될까요?  해당 이벤트가 발생할 때마다 `LongTask`가 호출되면 스택 오버플로가 발생할 수도 있습니다.  
  
 `mWidget`에 새 `Widget`에 대한 참조를 할당하여 변수 `mWidget`에서 다른 `Widget` 개체의 이벤트를 처리하도록 할 수 있습니다.  실제로 해당 단추를 클릭할 때마다 `Button1_Click`의 코드에서 이 작업을 수행하도록 할 수 있습니다.  
  
#### 다른 widget의 이벤트를 처리하려면  
  
-   `Button1_Click` 프로시저에서 `mWidget.LongTask(12.2, 0.33)` 바로 앞에 다음 코드 줄을 추가합니다.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#9](../../../../visual-basic/programming-guide/language-features/events/codesnippet/visualbasic/VbEventWalkthrough/Form1.vb#9)]  
  
 해당 단추를 클릭할 때마다 위의 코드에서 새 `Widget`을 만듭니다.  `LongTask` 메서드가 완료되는 즉시 `Widget`에 대한 참조가 해제되고 `Widget`은 소멸됩니다.  
  
 `WithEvents` 변수는 한 번에 하나의 개체 참조만 포함할 수 있으므로 다른 `Widget` 개체를 `mWidget`에 할당하면 이전 `Widget` 개체의 이벤트는 더 이상 처리되지 않습니다.  `mWidget`이 이전 `Widget`에 대한 참조를 포함하는 유일한 개체 변수인 경우 이 개체는 소멸됩니다.  여러 `Widget` 개체의 이벤트를 처리하려는 경우 `AddHandler` 문을 사용하여 각 개체의 이벤트를 개별적으로 처리합니다.  
  
> [!NOTE]
>  선언할 수 있는 `WithEvents` 변수의 수에는 제한이 없지만 `WithEvents` 변수의 배열은 지원되지 않습니다.  
  
## 참고 항목  
 [Walkthrough: Declaring and Raising Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)   
 [Events](../../../../visual-basic/programming-guide/language-features/events/events.md)