---
title: "이벤트 처리 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- event handling [Visual Basic], walkthroughs
- walkthroughs [Visual Basic], event handling
- variables [Visual Basic], WithEvents
- events [Visual Basic], walkthroughs
- WithEvents keyword [Visual Basic], walkthroughs
- event handlers [Visual Basic], walkthroughs
ms.assetid: f145b3fc-5ae0-4509-a2aa-1ff6934706bd
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e4e31937d67d2140865a9626f79fbddc16796709
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-handling-events-visual-basic"></a>연습: 이벤트 처리(Visual Basic)
이벤트로 작업 하는 방법을 보여 주는 두 항목 중 두 번째 숫자입니다. 첫 번째 항목 [연습: 이벤트 선언 및 발생](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)를 선언 하는 방법을 보여 줍니다. 이 섹션에서는 발생할 때 이벤트를 처리 하는 방법을 보여 주는 폼과 다음 연습에서 클래스를 사용 합니다.  
  
 `Widget` 클래스 예제에는 일반적인 이벤트 처리 문을 사용 합니다. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]이벤트를 사용한 작업에 대 한 기타 기술을 제공 합니다. 연습으로 사용 하도록이 예제를 수정할 수 있습니다는 `AddHandler` 및 `Handles` 문.  
  
### <a name="to-handle-the-percentdone-event-of-the-widget-class"></a>위젯 클래스의 PercentDone 이벤트를 처리 하려면  
  
1.  에 다음 코드를 넣을 `Form1`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#4](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_1.vb)]  
  
     `WithEvents` 키워드를 지정 하는 변수 `mWidget` 개체의 이벤트를 처리 하는 데 사용 됩니다. 개체가 만들어집니다 클래스의 이름을 제공 하 여 개체의 종류를 지정 합니다.  
  
     변수 `mWidget` 에 선언 된 `Form1` 때문에 `WithEvents` 변수 클래스 수준 이어야 합니다. 에 배치 되는 클래스의 유형에 관계 없이 유용 합니다.  
  
     변수 `mblnCancel` 취소 하는 데 사용 되는 `LongTask` 메서드.  
  
## <a name="writing-code-to-handle-an-event"></a>이벤트를 처리 하는 코드 작성  
 사용 하는 변수를 선언 하는 즉시 `WithEvents`, 클래스의 왼쪽된 드롭다운 목록에서 변수 이름이 나타납니다 **코드 편집기**합니다. 선택 하는 경우 `mWidget`, `Widget` 클래스의 이벤트 오른쪽 드롭다운 목록에 표시 합니다. 이벤트를 선택 하면 해당 이벤트 프로시저가 접두사와 함께 표시 됩니다. `mWidget` 과 밑줄이 합니다. 와 연결 된 모든 이벤트 프로시저는 `WithEvents` 변수에는 접두사로 변수 이름이 제공 됩니다.  
  
#### <a name="to-handle-an-event"></a>이벤트를 처리 하도록  
  
1.  선택 `mWidget` 왼쪽 드롭다운 목록에서 **코드 편집기**합니다.  
  
2.  선택 된 `PercentDone` 오른쪽 드롭다운 목록에서 이벤트 발생 합니다. **코드 편집기** 열립니다는 `mWidget_PercentDone` 이벤트 프로시저입니다.  
  
    > [!NOTE]
    >  **코드 편집기** 는 유용 하지만 새 이벤트 처리기를 삽입 하는 데 필요 하지 않습니다. 이 연습에서는 것이 이벤트 처리기 코드에 직접 복사 하는 보다 쉽습니다.  
  
3.  다음 코드를 `mWidget_PercentDone` 이벤트 처리기에 추가합니다.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#5](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_2.vb)]  
  
     때마다는 `PercentDone` 이벤트가 발생 하면 이벤트 프로시저 표시에서 완료율은 `Label` 제어 합니다. `DoEvents` 메서드를 사용 하면 다시 그릴 수 레이블을 또한에 게 사용자를 클릭 하 고는 **취소** 단추입니다.  
  
4.  다음 코드에 대 한 추가 `Button2_Click` 이벤트 처리기.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#6](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_3.vb)]  
  
 클릭 하면는 **취소** 동안 단추 `LongTask` 실행 되는 `Button2_Click` 이벤트가 실행 될으로 `DoEvents` 문을 적용 되려면 이벤트 처리를 허용 합니다. 클래스 수준 변수 `mblnCancel` 로 설정 된 `True`, 및 `mWidget_PercentDone` 테스트 한 설정 하는 다음 이벤트는 `ByRef Cancel` 인수 `True`합니다.  
  
## <a name="connecting-a-withevents-variable-to-an-object"></a>WithEvents 변수 개체에 연결  
 `Form1`처리 하도록 설정 된 `Widget` 개체의 이벤트입니다. 이제 남은 것 찾으려고는 `Widget` 어딘가에 합니다.  
  
 변수를 선언 하는 경우 `WithEvents` 디자인 타임에 없는 개체는 이와 연관 됩니다. A `WithEvents` 변수는 다른 개체 변수 처럼 합니다. 개체를 만들고 사용 하 여에 대 한 참조를 할당 해야는 `WithEvents` 변수입니다.  
  
#### <a name="to-create-an-object-and-assign-a-reference-to-it"></a>개체를 생성 하 고 참조를 할당 하려면  
  
1.  선택 **(Form1 이벤트)** 왼쪽 드롭다운 목록에서 **코드 편집기**합니다.  
  
2.  선택 된 `Load` 오른쪽 드롭다운 목록에서 이벤트 발생 합니다. **코드 편집기** 열립니다는 `Form1_Load` 이벤트 프로시저입니다.  
  
3.  다음 코드에 대 한 추가 `Form1_Load` 이벤트 프로시저를 만드는 `Widget`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#7](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_4.vb)]  
  
 이 코드를 실행 하는 경우 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 만듭니다는 `Widget` 개체 및 해당 이벤트와 연결 된 이벤트 프로시저에 연결 `mWidget`합니다. 때부터, 때마다는 `Widget` 발생 해당 `PercentDone` 이벤트는 `mWidget_PercentDone` 이벤트 프로시저를 실행 합니다.  
  
#### <a name="to-call-the-longtask-method"></a>LongTask 메서드를 호출 하려면  
  
-   다음 코드를 `Button1_Click` 이벤트 처리기에 추가합니다.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#8](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_5.vb)]  
  
 전에 `LongTask` 메서드를 호출 완료율을 표시 해야 초기화 레이블과 클래스 수준 `Boolean` 으로 설정 되어 있어야 해당 메서드를 취소에 대 한 플래그 `False`합니다.  
  
 `LongTask`작업 기간 12.2 시간 (초)으로 호출 됩니다. `PercentDone` 이벤트가 발생 한 번 마다 1 / 3 초입니다. 이벤트가 발생할 때마다는 `mWidget_PercentDone` 이벤트 프로시저를 실행 합니다.  
  
 때 `LongTask` 완료 되 면 `mblnCancel` 있는지 테스트 `LongTask` 정상적으로 종료 하기 때문에 중지 된 경우 또는 `mblnCancel` 로 설정 된 `True`합니다. 완료율 전자의 경우에만 업데이트 됩니다.  
  
#### <a name="to-run-the-program"></a>프로그램을 실행하려면  
  
1.  F5 키를 눌러 실행된 모드에서 프로젝트를 저장 합니다.  
  
2.  클릭는 **작업 시작** 단추입니다. 될 때마다는 `PercentDone` 이벤트가 발생 하면 완료 된 작업의 백분율 레이블을 업데이트 됩니다.  
  
3.  클릭는 **취소** 단추 태스크를 중지 합니다. 모양의 **취소** 단추에는 클릭할 때 즉시 변경 되지는 않습니다. `Click` 이벤트가 발생할 수는 `My.Application.DoEvents` 문을 이벤트 처리를 허용 합니다.  
  
    > [!NOTE]
    >  `My.Application.DoEvents` 메서드 이벤트를 처리 하지 동일한 방식으로 폼 마찬가지로 합니다. 예를 들어이 연습에서는 클릭 해야는 **취소** 단추를 두 번입니다. 이벤트를 직접 처리 하기를 사용할 수 있습니다 다중 스레딩을 합니다. 자세한 내용은 참조 [스레딩](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c)합니다.  
  
 F11으로 프로그램을 실행 하 여 한 번에 한 줄을 코드를 단계별로 실행 하는 방법도 사용할 수 있습니다. 실행 중 시작 하는 방법을 볼 수 있듯이 `LongTask`, 간단 하 게 다시 진입할 `Form1` 될 때마다는 `PercentDone` 이벤트가 발생 합니다.  
  
 수행 된 작업의 코드에 다시 실행 되는 동안 if, `Form1`, `LongTask` 메서드를 다시 호출? 최악의 경우 스택 오버플로가 발생할 수 있습니다 `LongTask` 이벤트가 발생할 때마다가 호출 됩니다.  
  
 변수를 발생 시킬 수 있습니다 `mWidget` 다른 이벤트를 처리할 `Widget` 새에 대 한 참조를 할당 하 여 개체 `Widget` 를 `mWidget`합니다. 코드를 만들 수는 실제로 `Button1_Click` 단추를 클릭할 때마다이 작업을 수행 합니다.  
  
#### <a name="to-handle-events-for-a-different-widget"></a>다른 장치에 대 한 이벤트를 처리 하려면  
  
-   다음 줄의 코드를 추가 `Button1_Click` 절차 바로 앞에 행을 기록해둡니다 `mWidget.LongTask(12.2, 0.33)`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#9](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_6.vb)]  
  
 위의 코드에서는 새 `Widget` 단추를 클릭할 때마다 합니다. 즉시는 `LongTask` 메서드가 완료 되 면에 대 한 참조는 `Widget` 출시 되 면 및 `Widget` 소멸 됩니다.  
  
 A `WithEvents` 변수가 한 번에 하나의 개체 참조를 포함할 수 있으므로 다른 할당 하는 경우 `Widget` 개체를 `mWidget`, 이전 `Widget` 개체의 이벤트를 처리할 수 없습니다. 경우 `mWidget` 이전에 대 한 참조를 포함 하는 유일한 개체 변수가 `Widget`, 해당 개체가 삭제 됩니다. 여러 이벤트를 처리 하려는 경우 `Widget` 개체를 사용 하 여는 `AddHandler` 각 개체의 이벤트를 개별적으로 처리 하는 문입니다.  
  
> [!NOTE]
>  많은 선언할 수 있습니다 `WithEvents` 배열을 하지만 변수의 수, 필요한 `WithEvents` 변수는 지원 되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [연습: 이벤트 선언 및 발생](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)  
 [이벤트](../../../../visual-basic/programming-guide/language-features/events/index.md)
