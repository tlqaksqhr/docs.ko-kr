---
title: 최종 &lt;키워드&gt; 문 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.EndDefinition
helpviewer_keywords:
- End keyword [Visual Basic]
ms.assetid: 42d6e088-ab0f-4cda-88e8-fdce3e5fcf4f
ms.openlocfilehash: 8137434bfd8c26144d78b1761b784cdba4894eaf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605266"
---
# <a name="end-ltkeywordgt-statement-visual-basic"></a>최종 &lt;키워드&gt; 문 (Visual Basic)
추가 키워드 뒤에 나올, 해당 키워드 뒤에 문 블록의 정의 종료 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
End AddHandler  
End Class   
End Enum   
End Event   
End Function   
End Get   
End If   
End Interface   
End Module   
End Namespace   
End Operator   
End Property   
End RaiseEvent  
End RemoveHandler  
End Select   
End Set   
End Structure   
End Sub   
End SyncLock   
End Try   
End While   
End With  
```  
  
## <a name="parts"></a>요소  
 `End`  
 필수. 프로그래밍 요소의 정의 종료 합니다.  
  
 `AddHandler`  
 종료 하는 데 필요한 프로그램 `AddHandler` 접근자는 일치 하는 시작 `AddHandler` 문을 사용자 지정에서 [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)합니다.  
  
 `Class`  
 일치 하는 시작 되었습니다. 클래스 정의 종료 하는 데 필요한 [Class 문](../../../visual-basic/language-reference/statements/class-statement.md)합니다.  
  
 `Enum`  
 일치 하는 시작 된 열거형 정의 종료 하는 데 필요한 [Enum 문](../../../visual-basic/language-reference/statements/enum-statement.md)합니다.  
  
 `Event`  
 종료 하는 데 필요한는 `Custom` 는 일치 하는 시작 된 이벤트 정의 [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)합니다.  
  
 `Function`  
 종료 하는 데 필요한는 `Function` 는 일치 하는 시작 된 프로시저 정의 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)합니다. 실행 발생 한 경우는 `End``Function` 문, 컨트롤이 호출 코드에 반환 합니다.  
  
 `Get`  
 종료 하는 데 필요한는 `Property` 는 일치 하는 시작 된 프로시저 정의 [Get 문을](../../../visual-basic/language-reference/statements/get-statement.md)합니다. 실행 발생 한 경우는 `End``Get` 속성의 값을 요청 하는 문으로 문에 제어가 반환 합니다.  
  
 `If`  
 종료 하는 데 필요한 프로그램 `If`... `Then`... `Else` 블록으로 일치 하는 시작 된 정의 `If` 문. 참조 [경우... 다음 중... Else 문](../../../visual-basic/language-reference/statements/if-then-else-statement.md)합니다.  
  
 `Interface`  
 일치 하는 시작 된 인터페이스 정의 종료 하는 데 필요한 [Interface 문](../../../visual-basic/language-reference/statements/interface-statement.md)합니다.  
  
 `Module`  
 일치 하는 시작 된 모듈 정의 종료 하는 데 필요한 [Module 문](../../../visual-basic/language-reference/statements/module-statement.md)합니다.  
  
 `Namespace`  
 일치 하는 시작 된 네임 스페이스 정의 종료 하는 데 필요한 [Namespace 문](../../../visual-basic/language-reference/statements/namespace-statement.md)합니다.  
  
 `Operator`  
 일치 하는 시작 된 연산자 정의 종료 하는 데 필요한 [Operator 문](../../../visual-basic/language-reference/statements/operator-statement.md)합니다.  
  
 `Property`  
 일치 하는 시작 된 속성 정의 종료 하는 데 필요한 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)합니다.  
  
 `RaiseEvent`  
 종료 하는 데 필요한는 `RaiseEvent` 접근자는 일치 하는 시작 `RaiseEvent` 문을 사용자 지정에서 [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)합니다.  
  
 `RemoveHandler`  
 종료 하는 데 필요한는 `RemoveHandler` 접근자는 일치 하는 시작 `RemoveHandler` 문을 사용자 지정에서 [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)합니다.  
  
 `Select`  
 종료 하는 데 필요한는 `Select`... `Case` 블록으로 일치 하는 시작 된 정의 `Select` 문. 참조 [선택... Case 문](../../../visual-basic/language-reference/statements/select-case-statement.md)합니다.  
  
 `Set`  
 종료 하는 데 필요한는 `Property` 는 일치 하는 시작 된 프로시저 정의 [Set 문을](../../../visual-basic/language-reference/statements/set-statement.md)합니다. 실행 발생 한 경우는 `End``Set` 속성의 값을 설정 하는 문으로 문에 제어가 반환 합니다.  
  
 `Structure`  
 일치 하는 시작 된 구조 정의 종료 하는 데 필요한 [Structure 문을](../../../visual-basic/language-reference/statements/structure-statement.md)합니다.  
  
 `Sub`  
 종료 하는 데 필요한는 `Sub` 는 일치 하는 시작 된 프로시저 정의 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)합니다. 실행 발생 한 경우는 `End``Sub` 문, 컨트롤이 호출 코드에 반환 합니다.  
  
 `SyncLock`  
 종료 하는 데 필요한는 `SyncLock` 블록으로 일치 하는 시작 된 정의 `SyncLock` 문. 참조 [SyncLock 문](../../../visual-basic/language-reference/statements/synclock-statement.md)합니다.  
  
 `Try`  
 종료 하는 데 필요한는 `Try`... `Catch`... `Finally` 블록으로 일치 하는 시작 된 정의 `Try` 문. 참조 [시도 중... Catch 하는 중... Finally 문](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)합니다.  
  
 `While`  
 종료 하는 데 필요한는 `While` 는 일치 하는 시작 된 정의 루프 `While` 문. 참조 [동안... While 문 종료](../../../visual-basic/language-reference/statements/while-end-while-statement.md)합니다.  
  
 `With`  
 종료 하는 데 필요한는 `With` 블록으로 일치 하는 시작 된 정의 `With` 문. 참조 [와... 문을 사용 하 여 종료](../../../visual-basic/language-reference/statements/with-end-with-statement.md)합니다.  
  
## <a name="remarks"></a>설명  
 [End 문](../../../visual-basic/language-reference/statements/end-statement.md), 추가 키워드, 실행을 즉시 종료 합니다.  
  
 앞에 숫자 기호 (`#`), `End` 키워드는 해당 지시문에 의해 도입 된 전처리 블록을 종료 합니다.  
  
 `#End`  
 필수. 전처리 블록의 정의 종료 합니다.  
  
 `#ExternalSource`  
 일치 하는 시작 된 외부 소스 블록을 종료 하는 데 필요한 [#ExternalSource 지시문](../../../visual-basic/language-reference/directives/externalsource-directive.md)합니다.  
  
 `#If`  
 일치 하는 시작 된 조건부 컴파일 블록을 종료 하는 데 필요한 `#If` 지시문입니다. 참조 [#If... Then... #Else 지시문](../../../visual-basic/language-reference/directives/if-then-else-directives.md)합니다.  
  
 `#Region`  
 일치 하는 시작 된 소스 영역 블록을 종료 하는 데 필요한 [#Region 지시문](../../../visual-basic/language-reference/directives/region-directive.md)합니다.  
  
## <a name="smart-device-developer-notes"></a>스마트 장치 개발자 노트  
 `End` 추가 키워드 문이 지원 되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [End 문](../../../visual-basic/language-reference/statements/end-statement.md)
