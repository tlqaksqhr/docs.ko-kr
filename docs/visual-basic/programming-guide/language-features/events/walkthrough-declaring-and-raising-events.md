---
title: (Visual Basic) 이벤트 선언 및 발생
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], events
- events [Visual Basic], walkthroughs
- declaring events [Visual Basic], walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events [Visual Basic], walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
ms.openlocfilehash: 67bbf7bc95a0fe1ee8e9c2a6cf07d850d30bb028
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a>연습: 이벤트 선언 및 발생(Visual Basic)
이 연습에서는 선언 하 고 라는 클래스에 이벤트를 발생 하는 방법을 보여 줍니다. `Widget`합니다. 항목을 참고할 하려는 단계를 완료 한 후 [연습: 이벤트 처리](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), 이벤트를 사용 하는 방법을 보여 주는 `Widget` 응용 프로그램에서 상태 정보를 제공 하는 개체입니다.  
  
## <a name="the-widget-class"></a>위젯 클래스  
 있는 것으로 가정는 `Widget` 클래스입니다. 프로그램 `Widget` 클래스에는 실행 하는 데 시간이 오래 걸릴 수 있습니다 하는 메서드를 일종의 완료 표시기 나타내려고 되도록 응용 프로그램 및입니다.  
  
 만들 수는 물론,는 `Widget` 개체 완료율 대화 상자를 표시 한 다음 할 수 있지만 수 이후에를 사용 하는 모든 프로젝트에서이 대화 상자는 `Widget` 클래스입니다. 사용자 인터페이스 개체 핸들을 사용 하는 응용 프로그램을 사용 하는 개체를 디자인 하는 좋은 원칙 것-경우에 개체의 전체 목적은 양식 또는 대화 상자를 관리 합니다.  
  
 목적은 `Widget` 추가 하는 것 이므로, 다른 작업을 수행 하는 것을 `PercentDone` 이벤트 및 호출 하는 프로시저를 통해 `Widget`의 메서드는 처리할 업데이트 이벤트와 표시 상태입니다. `PercentDone` 이벤트 작업을 취소 하기 위한 메커니즘을 제공할 수도 수 있습니다.  
  
#### <a name="to-build-the-code-example-for-this-topic"></a>이 항목에 대 한 코드 예제를 빌드합니다.  
  
1.  새 Visual Basic Windows 응용 프로그램 프로젝트를 열고 라는 양식을 만드는 `Form1`합니다.  
  
2.  두 개의 단추와 적절 한 레이블을 추가 `Form1`합니다.  
  
3.  다음 표에 나와 있는 것처럼 개체의 이름을 지정합니다.  
  
    |개체|속성|설정|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|시작 태스크|  
    |`Button2`|`Text`|취소|  
    |`Label`|`(Name)`, `Text`|lblPercentDone, 0|  
  
4.  에 **프로젝트** 메뉴 선택 **클래스 추가** 라는 클래스를 추가 하려면 `Widget.vb` 프로젝트에 있습니다.  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a>위젯 클래스에 대 한 이벤트를 선언 하려면  
  
-   사용 하 여는 `Event` 에서 이벤트를 선언 하는 키워드는 `Widget` 클래스입니다. 이벤트를 가질 수 있는 참고 `ByVal` 및 `ByRef` 인수,으로 `Widget`의 `PercentDone` 이벤트:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_1.vb)]  
  
 호출 하는 개체를 받으면는 `PercentDone` 이벤트는 `Percent` 인수 완료 된 작업의 백분율을 포함 합니다. `Cancel` 인수로 설정할 수 있습니다 `True` 이벤트를 발생 시킨 메서드를 취소할 합니다.  
  
> [!NOTE]
>  다음과 같은 예외가 프로시저 인수를 같은 방식으로 이벤트 인수를 선언할 수 있습니다: 이벤트 가질 수 없습니다 `Optional` 또는 `ParamArray` 이벤트 및 인수, 반환 값이 없습니다.  
  
 `PercentDone` 이벤트에 의해 발생 되는 `LongTask` 의 메서드는 `Widget` 클래스입니다. `LongTask` 두 개의 인수: 작업 및 하기 전에 최소 시간 간격에는 시간 메서드가 가로채어 `LongTask` 일시 중지를 발생 시키는 `PercentDone` 이벤트입니다.  
  
#### <a name="to-raise-the-percentdone-event"></a>PercentDone 이벤트 발생  
  
1.  에 대 한 액세스를 간소화 하기 위해는 `Timer` 이 클래스에서 사용 하는 속성에 추가 `Imports` 클래스 모듈의 선언 섹션의 맨 위에 문을 위에 `Class Widget` 문.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_2.vb)]  
  
2.  `Widget` 클래스에 다음 코드를 추가합니다.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_3.vb)]  
  
 응용 프로그램 호출 하는 경우는 `LongTask` 메서드는 `Widget` 발생 시키는 클래스는 `PercentDone` 이벤트 모든 `MinimumInterval` 초입니다. 이 이벤트는 반환 될 때 `LongTask` 확인 하는 `Cancel` 인수를 설정한 `True`합니다.  
  
 몇 가지 사항을 고려해 야 여기 합니다. 간단히 하기 위해는 `LongTask` 프로시저 미리 알고 있는 작업 소요 될 것으로 가정 합니다. 이 경우 거의 없습니다. 작업 짝수 크기의 청크로 나누는 것이 어려울 수 있습니다 및 종종 가장 중요 한 사용자에 게는 단순히 이유가 항목 표시 해지기 전에 경과 되는 시간입니다.  
  
 이 샘플의 다른 문제가 발생할 수 있습니다. `Timer` 자정 바로 전에 시작 된 경우 응용 프로그램 중지 따라서; 속성 자정부터 경과한 시간 (초) 수를 반환 합니다. 보다 신중 시간을 측정 하는 이러한 고려 경계 조건을 거 나 피하도록, 같은 속성을 사용 하 여 `Now`합니다.  
  
 이제는 `Widget` 클래스에서 이벤트를 발생 수를 이동할 수 있습니다 다음 연습 합니다. [연습: 이벤트 처리](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) 사용 하는 방법을 보여 줍니다. `WithEvents` 와 이벤트 처리기를 연결 하는 `PercentDone` 이벤트입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>  
 <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>  
 [연습: 이벤트 처리](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)  
 [이벤트](../../../../visual-basic/programming-guide/language-features/events/index.md)
