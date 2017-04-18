---
title: "RaiseEvent 문 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.RaiseEventMethod
- vb.RaiseEvent
- RaiseEvent
dev_langs:
- VB
helpviewer_keywords:
- raising events, RaiseEvent statement
- RaiseEvent statement
- event handlers, connecting events to
ms.assetid: f82e380a-1e6b-4047-bea8-c853f4d2c742
caps.latest.revision: 19
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
ms.openlocfilehash: 059b1347c4a35b896f5aa19cadb28fbceb8b25c9
ms.lasthandoff: 03/13/2017

---
# <a name="raiseevent-statement"></a>RaiseEvent 문
트리거는 이벤트 클래스, 폼 또는 문서 내에서 모듈 수준에서 선언 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
RaiseEvent eventname[( argumentlist )]  
```  
  
## <a name="parts"></a>요소  
 `eventname`  
 필수 요소. 트리거할 이벤트의 이름입니다.  
  
 `argumentlist`  
 선택적 요소. 변수, 배열, 또는 식의 쉼표로 구분 된 목록입니다. `argumentlist` 인수를 괄호로 묶어야 합니다. 인수가 있을 경우 괄호를 생략 해야 합니다.  
  
## <a name="remarks"></a>주의  
 필수 `eventname` 모듈 내에서 선언 하는 이벤트의 이름입니다. Visual Basic의 변수 명명 규칙을 따릅니다.  
  
 이 이벤트는 발생 한 모듈 내에서 선언 되지 않은, 오류가 발생 합니다. 다음 코드에서는 이벤트 선언 및 이벤트가 발생 하는 프로시저를 보여 줍니다.  
  
 [!code-vb[VbVbalrEvents #&37;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_1.vb)]  
  
 사용할 수 없습니다 `RaiseEvent` 모듈에 명시적으로 선언 되지 않은 이벤트를 발생 합니다. 예를 들어 모든 폼 상속을 <xref:System.Windows.Forms.Control.Click>에서 이벤트 <xref:System.Windows.Forms.Form?displayProperty=fullName>를 사용 하 여 높일 수 없습니다 `RaiseEvent` 파생된 된 폼에서.</xref:System.Windows.Forms.Form?displayProperty=fullName> </xref:System.Windows.Forms.Control.Click> 선언 하는 경우는 `Click` 이벤트 폼 자체의 폼 모듈에 숨겨집니다 <xref:System.Windows.Forms.Control.Click>이벤트.</xref:System.Windows.Forms.Control.Click> 폼의를 여전히 호출할 수 있습니다 <xref:System.Windows.Forms.Control.Click>를 호출 하 여 이벤트는 <xref:System.Windows.Forms.Control.OnClick%2A>메서드.</xref:System.Windows.Forms.Control.OnClick%2A> </xref:System.Windows.Forms.Control.Click>  
  
 기본적으로 Visual Basic에서 정의 된 이벤트의 이벤트 처리기는 연결이 설정 된 순서 대로 발생 합니다. 이벤트를 가질 수 있으므로 `ByRef` 매개 변수를 나중에 연결 하는 프로세스는 이전 이벤트 처리기에 의해 변경 된 매개 변수를 받을 수 있습니다. 이벤트 처리기가 실행 된 후 컨트롤 이벤트를 발생 시킨 서브루틴으로 반환 됩니다.  
  
> [!NOTE]
>  공유 되지 않는 이벤트 선언 된 클래스의 생성자 내에서 발생 하지 해야 합니다. 이러한 이벤트를 런타임 오류 발생 지는 않지만 연결 된 이벤트 처리기에서 포착 하지 못할 수 있습니다. 사용 된 `Shared` 한정자를 생성자에서 이벤트를 발생 하는 경우 공유 이벤트를 만듭니다.  
  
> [!NOTE]
>  사용자 지정 이벤트를 정의 하 여 이벤트의 기본 동작을 변경할 수 있습니다. 사용자 지정 이벤트는 `RaiseEvent` 문은 이벤트의 호출 `RaiseEvent` 접근자입니다. 사용자 지정 이벤트에 대 한 자세한 내용은 참조 하십시오. [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 이벤트를 사용하여 10초부터 0초까지 카운트 다운합니다. 코드에 나와 있는 이벤트 관련 메서드, 속성 및 포함 하 여 문 중 일부는 `RaiseEvent` 문입니다.  
  
 이벤트를 발생시키는 클래스는 이벤트 소스이고 이벤트를 처리하는 메서드는 이벤트 처리기입니다. 이벤트 소스는 생성되는 이벤트에 대해 여러 개의 처리기를 사용할 수 있습니다. 클래스에서 이벤트를 발생시키면 해당 이벤트는 개체의 해당 인스턴스에 대해 이벤트를 처리하도록 선택한 모든 클래스에서 발생됩니다.  
  
 또한 이 예제에서는 단추(`Button1`)와 텍스트 상자(`TextBox1`)가 있는 폼(`Form1`)을 사용합니다. 단추를 클릭하면 첫 번째 텍스트 상자에 10초부터 0초까지의 카운트 다운이 표시됩니다. 전체 시간(10초)이 경과되면 첫 번째 텍스트 상자에 "Done"이 표시됩니다.  
  
 `Form1`에 대한 코드는 폼의 초기 상태 및 최종 상태를 지정합니다. 또한 이벤트가 발생될 때 실행될 코드도 포함됩니다.  
  
 이 예제를 사용 하려면 새 Windows 응용 프로그램 프로젝트를 열고 라는 단추를 추가 `Button1` 및 라는 텍스트 상자가 `TextBox1` 라는 기본 폼에 `Form1`합니다. 그런 다음 폼을 마우스 오른쪽 단추로 클릭 하 고 클릭 **코드 보기** 코드 편집기를 엽니다.  
  
 추가 `WithEvents` 의 선언 섹션에는 변수는 `Form1` 클래스입니다.  
  
 [!code-vb[VbVbalrEvents #&14;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_2.vb)]  
  
## <a name="example"></a>예제  
 `Form1`에 대한 코드에 다음 코드를 추가합니다. 교체와 같은 존재할 수 있는 모든 중복 프로시저 `Form_Load`, 또는 `Button_Click`합니다.  
  
 [!code-vb[VbVbalrEvents #&15;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_3.vb)]  
  
 앞의 예제를 실행 하 고 저장 단추를 클릭 하는 F5 키를 눌러 **시작**합니다. 첫 번째 텍스트 상자에서 초를 카운트 다운하기 시작합니다. 전체 시간(10초)이 경과되면 첫 번째 텍스트 상자에 "Done"이 표시됩니다.  
  
> [!NOTE]
>  `My.Application.DoEvents` 메서드 이벤트를 처리 하지 동일한 방식으로 폼 마찬가지로 합니다. 사용할 수를 직접 이벤트를 처리 하기 위해 다중 스레딩을 합니다. 자세한 내용은 참조 [스레딩](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [이벤트](../../../visual-basic/programming-guide/language-features/events/index.md)   
 [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)   
 [AddHandler 문](../../../visual-basic/language-reference/statements/addhandler-statement.md)   
 [RemoveHandler 문](../../../visual-basic/language-reference/statements/removehandler-statement.md)   
 [핸들](../../../visual-basic/language-reference/statements/handles-clause.md)
