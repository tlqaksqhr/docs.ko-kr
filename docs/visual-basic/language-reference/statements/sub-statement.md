---
title: "Sub 문(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Sub
helpviewer_keywords:
- Public keyword [Visual Basic], Sub statements
- procedures [Visual Basic], creating
- declaring procedures [Visual Basic], Sub statement
- arguments [Visual Basic], Sub procedures
- As keyword [Visual Basic], Sub statements
- Optional keyword [Visual Basic], Sub statements
- declarations [Visual Basic], procedures
- Sub keyword [Visual Basic]
- Handles keyword [Visual Basic], Sub statements
- Protected Friend keyword [Visual Basic]
- ParamArray keyword [Visual Basic], Sub statements
- Implements keyword [Visual Basic], Sub statements
- Sub statement [Visual Basic]
- subroutines
- ByRef keyword [Visual Basic], Sub statements
- Sub procedures [Visual Basic], Sub statement
- recursive procedures
- Private keyword [Visual Basic], Sub statements
- Friend keyword [Visual Basic], Sub statements
- Exit statement [Visual Basic], Sub statements
- procedures [Visual Basic], Sub
- End keyword [Visual Basic], Sub statements
- ByVal keyword [Visual Basic], Sub statements
- Visual Basic code, Sub procedures
ms.assetid: e347d700-d06c-405b-b302-e9b1edb57dfc
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0a2d0d5ffdca857a3a5ca58cd38b0930f254526f
ms.sourcegitcommit: 8ed4ebc15b5ef89d06a7507dc9d5e306e30accf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/14/2017
---
# <a name="sub-statement-visual-basic"></a>Sub 문(Visual Basic)
선언 이름과 매개 변수를 정의 하는 코드는 `Sub` 프로시저입니다.  
  
## <a name="syntax"></a>구문  
  
```  
[ <attributelist> ] [ Partial ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async ]  
Sub name [ (Of typeparamlist) ] [ (parameterlist) ] [ Implements implementslist | Handles eventlist ]  
    [ statements ]  
    [ Exit Sub ]  
    [ statements ]  
End Sub  
```  
  
## <a name="parts"></a>요소  
  
-   `attributelist`  
  
     선택 사항입니다. 참조 [특성 목록](attribute-list.md)합니다.  
  
-   `Partial`  
  
     선택 사항입니다. 부분 메서드의 정의 나타냅니다. 참조 [부분 메서드](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)합니다.  
  
-   `accessmodifier`  
  
     선택 사항입니다. 다음 중 하나일 수 있습니다.  
  
    -   [공용](../modifiers/public.md)  
  
    -   [보호됨](../modifiers/protected.md)  
  
    -   [Friend](../modifiers/friend.md)  
  
    -   [전용](../modifiers/private.md)  
  
    -   `Protected Friend`  
  
     참조 [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.  
  
-   `proceduremodifiers`  
  
     선택 사항입니다. 다음 중 하나일 수 있습니다.  
  
    -   [오버로드](../modifiers/overloads.md)  
  
    -   [재정의](../modifiers/overrides.md)  
  
    -   [재정의 가능](../modifiers/overridable.md)  
  
    -   [NotOverridable](../modifiers/notoverridable.md)  
  
    -   [MustOverride](../modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     선택 사항입니다. 참조 [공유](../modifiers/shared.md)합니다.  
  
-   `Shadows`  
  
     선택 사항입니다. 참조 [그림자](../modifiers/shadows.md)합니다.  
  
-   `Async`  
  
     선택 사항입니다. 참조 [비동기](../modifiers/async.md)합니다.  
  
-   `name`  
  
     필수 요소. 프로시저의 이름입니다. 참조 [선언 된 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다. 생성자를 클래스에 대 한 프로시저를 만들려면 설정의 이름을 `Sub` 프로시저에는 `New` 키워드입니다. 자세한 내용은 참조 [개체 수명: 개체가 만들어지고 소멸 되는 하는 방법을](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)합니다.  
  
-   `typeparamlist`  
  
     선택 사항입니다. 제네릭 프로시저에 대 한 형식 매개 변수의 목록입니다. 참조 [목록을 입력](type-list.md)합니다.  
  
-   `parameterlist`  
  
     선택 사항입니다. 이 프로시저의 매개 변수를 나타내는 지역 변수 이름의 목록이 있습니다. 참조 [매개 변수 목록](parameter-list.md)합니다.  
  
-   `Implements`  
  
     선택 사항입니다. 하나 이상의이 절차를 구현 함을 나타냅니다 `Sub` 절차,이 프로시저의 포함 하는 클래스 또는 구조체에서 구현 되는 인터페이스에 정의 된 하나씩 있습니다. 참조 [문을 구현](implements-statement.md)합니다.  
  
-   `implementslist`  
  
     `Implements`가 제공된 경우 필수입니다. 구현할 `Sub` 프로시저 목록입니다.  
  
     `implementedprocedure [ , implementedprocedure ... ]`  
  
     각 `implementedprocedure`에는 다음과 같은 구문과 요소가 있습니다.  
  
     `interface.definedname`  
  
    |파트|설명|  
    |---|---|  
    |`interface`|필수 요소. 이 프로시저에 의해 구현 되는 인터페이스의 이름의 클래스 또는 구조체를 포함 합니다.|  
    |`definedname`|필수 요소. 프로시저가 `interface`에 정의되는 이름입니다.|  
  
-   `Handles`  
  
     선택 사항입니다. 이 절차에서 하나 이상의 특정 이벤트를 처리할 수 있음을 나타냅니다. 참조 [처리](handles-clause.md)합니다.  
  
-   `eventlist`  
  
     `Handles`가 제공된 경우 필수입니다. 이 프로시저에서 처리 하는 이벤트 목록입니다.  
  
     `eventspecifier [ , eventspecifier ... ]`  
  
     각 `eventspecifier`에는 다음과 같은 구문과 요소가 있습니다.  
  
     `eventvariable.event`  
  
    |파트|설명|  
    |---|---|  
    |`eventvariable`|필수 요소. 개체 변수는 이벤트를 발생 시키는 구조체 또는 클래스의 데이터 형식으로 선언 합니다.|  
    |`event`|필수 요소. 이 프로시저에서 처리 하는 이벤트의 이름입니다.|  
  
-   `statements`  
  
     선택 사항입니다. 문 블록을이 절차 내에서 실행 되도록 합니다.  
  
-   `End Sub`  
  
     이 프로시저의 정의 종료합니다.  
  
## <a name="remarks"></a>설명  
 모든 실행 코드는 프로시저 안에 있어야 합니다. 사용 하 여 한 `Sub` 호출 코드에 값을 반환 하지 않을 때 프로시저입니다. 사용 하 여 한 `Function` 프로시저는 값을 반환 하려는 경우.  
  
## <a name="defining-a-sub-procedure"></a>Sub 프로시저를 정의합니다.  
 정의할 수는 `Sub` 모듈 수준에만 프로시저입니다. Sub 프로시저에 대 한 선언 컨텍스트, 따라서 해야를 클래스, 구조체, 모듈 또는 인터페이스 및 소스 파일, 네임 스페이스, 프로시저 또는 블록으로 커야 합니다. 자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](declaration-contexts-and-default-access-levels.md)을 참조하세요.  
  
 `Sub`프로시저는 기본적으로 공용 액세스 합니다. 액세스 한정자를 사용 하 여 액세스 수준을 조정할 수 있습니다.  
  
 프로시저를 사용 하는 경우는 `Implements` 키워드를 포함 하는 클래스나 구조체 있어야는 `Implements` 바로 뒤에 오는 문을 해당 `Class` 또는 `Structure` 문. `Implements` 문을에 지정 된 각 인터페이스를 포함 해야 `implementslist`합니다. 그러나는 인터페이스를 정의 하 여 이름을 `Sub` (에서 `definedname`)이이 프로시저의 이름과 일치 하지 않아도 (에서 `name`).  
  
## <a name="returning-from-a-sub-procedure"></a>Sub 프로시저에서 반환  
 경우는 `Sub` 문을 호출한 다음 문이 실행 계속 프로시저가 호출 코드에 반환 되 면 합니다.  
  
 다음 예제에서는에서 반환 된 `Sub` 프로시저입니다.  
  
```vb  
Sub mySub(ByVal q As String)  
    Return  
End Sub   
```  
  
 `Exit Sub` 및 `Return` 문을 사용 하면 즉시 종료 한 `Sub` 프로시저입니다. 개수에 관계 없이 `Exit Sub` 및 `Return` 문은 프로시저에서 아무 곳 이나 나타날 수 있으며 함께 사용할 수 있습니다 `Exit Sub` 및 `Return` 문.  
  
## <a name="calling-a-sub-procedure"></a>Sub 프로시저를 호출합니다.  
 호출 하는 `Sub` 문에서 프로시저 이름을 사용 하 고 해당 이름에에서 해당 인수 목록 괄호로 묶어를 누른 다음으로 프로시저입니다. 인수를 제공 하지 않는 경우에 괄호를 생략할 수 있습니다. 그러나 코드는 항상 괄호를 포함 하는 경우 더 쉽게 읽을 수 있습니다.  
  
 A `Sub` 절차와 `Function` 프로시저 매개 변수를 업데이트 하 고 일련의 문 수행할 수 있습니다. 그러나 한 `Function` 프로시저 반환 값 및 `Sub` 프로시저 하지 않습니다. 따라서 사용할 수 없습니다는 `Sub` 식에는 프로시저입니다.  
  
 사용할 수는 `Call` 호출할 때 키워드는 `Sub` 프로시저만 해당 키워드는 대부분의 사용자에 권장 되지 않습니다. 자세한 내용은 참조 [Call 문을](call-statement.md)합니다.  
  
 Visual Basic에는 산술 식 내부 효율성을 높이기 위해 경우에 따라 다시 정렬 합니다. 이러한 이유로, 인수 목록에 다른 프로시저를 호출 하는 식이 포함 되어 있으면 있습니다 서는 안 식 됩니다 호출할 것으로 가정을 특정 순서로 합니다.  
  
## <a name="async-sub-procedures"></a>비동기 Sub 프로시저  
 비동기 기능을 사용 하면 명시적 콜백을 사용 하거나 수동으로 여러 함수 또는 람다 식에 코드를 분할 하지 않고도 비동기 함수를 호출할 수 있습니다.  
  
 사용 하 여 프로시저를 표시 하는 경우는 [비동기](../modifiers/async.md) 사용할 수 있습니다 한정자는 [Await](../../../visual-basic/language-reference/operators/await-operator.md) 연산자 프로시저에서 합니다. 에 도달할 때 제어는 `Await` 식에는 `Async` 프로시저 호출자에 게 제어가 반환와 프로시저에서 진행 대기 중인된 작업이 완료 될 때까지 일시 중단 합니다. 작업이 완료 될 때 실행 절차에서 다시 시작 수 있습니다.  
  
> [!NOTE]
>  `Async` 프로시저 중 하나는 첫 번째 대기 된 개체를 아직 완료 되지 않은 발견 되 면 호출자 또는의 끝에 반환 된 `Async` 프로시저에 도달 중 먼저 발생 합니다.  
  
 표시할 수도 있습니다는 [Function 문을](function-statement.md) 와 `Async` 한정자입니다. `Async` 함수 반환 형식으로 지정할 수 있습니다 <xref:System.Threading.Tasks.Task%601> 또는 <xref:System.Threading.Tasks.Task>합니다. 예로 나중에이 항목에서는 `Async` 의 반환 형식을 가진 함수를 <xref:System.Threading.Tasks.Task%601>합니다.  
  
 `Async``Sub` 프로시저에 주로 사용 됩니다 이벤트 처리기는 값을 반환할 수 없습니다. `Async``Sub` 프로시저 대기할 수 없습니다 및의 호출자는 `Async``Sub` 프로시저 예외를 catch 할 수 없습니다 하는 `Sub` 프로시저 throw 합니다.  
  
 `Async` 프로시저 모두를 선언할 수 없습니다 [ByRef](../modifiers/byref.md) 매개 변수입니다.  
  
 에 대 한 자세한 내용은 `Async` 프로시저 참조 [Async 및 Await를 사용한 비동기 프로그래밍](../../../visual-basic/programming-guide/concepts/async/index.md), [비동기 프로그램의 제어 흐름](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), 및 [비동기 반환 형식](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Sub` 을 이름, 매개 변수 및 코드의 본문을 형성 하는 정의 `Sub` 프로시저입니다.  
  
 [!code-vb[VbVbalrStatements#58](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/sub-statement_1.vb)]  
  
## <a name="example"></a>예제  
 다음 예에서 `DelayAsync` 는 `Async``Function` 의 반환 형식이 있는 <xref:System.Threading.Tasks.Task%601>합니다. `DelayAsync`에는 정수를 반환하는 `Return` 문이 포함됩니다. 따라서 함수 선언의 `DelayAsync` 의 반환 형식이 있어야 합니다. `Task(Of Integer)`합니다. 반환 형식이 이기 `Task(Of Integer)`, 평가 `Await` 에 식을 `DoSomethingAsync` 다음 문과 같이 정수를 생성 합니다.: `Dim result As Integer = Await delayTask`합니다.  
  
 `startButton_Click` 절차의 한 예로 `Async Sub` 프로시저입니다. 때문에 `DoSomethingAsync` 는 `Async` 함수, 작업에 대 한 호출에 대 한 `DoSomethingAsync` 기다려야, 다음 문과 같이: `Await DoSomethingAsync()`합니다. `startButton_Click``Sub` 프로시저 함께 정의 되어야 합니다는 `Async` 한정자 있기 때문에 `Await` 식입니다.  
  
 [!code-vb[csAsyncMethod#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/sub-statement_2.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Implements 문](implements-statement.md)  
 [Function 문](function-statement.md)  
 [매개 변수 목록](parameter-list.md)  
 [Dim 문](dim-statement.md)  
 [Call 문](call-statement.md)  
 [Of](of-clause.md)  
 [매개 변수 배열](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)  
 [방법: 제네릭 클래스 사용](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [프로시저 문제 해결](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)  
 [부분 메서드](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
