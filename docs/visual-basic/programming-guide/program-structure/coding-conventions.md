---
title: Visual Basic 코딩 규칙
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- examples [Visual Basic], coding conventions
- Visual Basic code, conventions
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
ms.openlocfilehash: b686747b46529b53b0802a7deb38b5b4949f4d5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="visual-basic-coding-conventions"></a>Visual Basic 코딩 규칙
Microsoft 예제 및이 항목의 지침에 따라 설명서를 개발 합니다. 동일한 코딩 규칙을 따르는 경우는 다음과 같은 이점을 얻을 수 있습니다 수 있습니다.  
  
-   코드는 판독기 레이아웃이 아닌 내용에 집중할 수 있도록 일관 된 모양을 갖습니다.  
  
-   읽는 사람이 이해 코드 보다 신속 하 게 이전 경험을 기반으로 예상할 수 때문에 있습니다.  
  
-   복사, 변경 및 코드를 더 쉽게 유지 관리할 수 있습니다.  
  
-   Visual basic 코드 "모범 사례" 보여 주는 확인할 수 있습니다.  
  
## <a name="naming-conventions"></a>명명 규칙  
  
-   이름 지정 지침에 대 한 정보를 참조 하십시오. [명명 지침](../../../standard/design-guidelines/naming-guidelines.md) 항목입니다.  
  
-   변수 이름의 일부로 "내" 또는 "my"를 사용 하지 마십시오. 이 연습와 혼동는 `My` 개체입니다.  
  
-   지침에 맞게 자동으로 생성 된 코드에서 개체의 이름을 변경할 필요가 없습니다.  
  
## <a name="layout-conventions"></a>레이아웃 규칙  
  
-   공백, 탭을 삽입 하 고 4 공간 들여쓰기와 스마트 들여쓰기를 사용 합니다.  
  
-   사용 하 여 **(다시 포맷)의 코드를 나열 하는 매우** 코드 편집기에서 코드의 서식을 다시 지정 합니다. 자세한 내용은 참조 [옵션, 텍스트 편집기, 기본 (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic)합니다.  
  
-   줄 당 하나의 문을 사용 합니다. Visual Basic 줄 구분 기호 문자 (:)를 사용 하지 마십시오.  
  
-   언어에서 허용 하는 경우 암시적 줄 연속 문자를 위해 명시적 줄 연속 문자 "_"를 사용 하지 마십시오.  
  
-   줄 마다 선언은 하나씩만 사용 합니다.  
  
-   경우 **(다시 포맷)의 코드를 나열 하는 매우** 하지 않는 형식 연속 줄 자동으로, 수동으로 들여쓰기 연속 된 줄을 탭 정지 하나 있습니다. 그러나 항상 왼쪽 맞춤 목록의 항목입니다.  
  
    ```  
    a As Integer,  
    b As Integer  
    ```  
  
-   메서드 및 속성 정의 사이 하나 이상의 빈 줄을 추가 합니다.  
  
## <a name="commenting-conventions"></a>주석 규칙  
  
-   코드 줄의 끝에 대신 별도 줄에 설명을 입력 합니다.  
  
-   마침표로 종료 주석 텍스트 및 주석 텍스트는 대문자로 시작 합니다.  
  
-   주석 구분 기호 (') 및 메모 텍스트 사이 공백을 하나 삽입 합니다.  
  
     [!code-vb[VbVbalrGuidelines#2](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_1.vb)]  
  
-   에 서식이 지정 된 별표 블록으로를 둘러싸고지 않습니다.  
  
## <a name="program-structure"></a>프로그램 구조  
  
-   사용 하는 경우는 `Main` 새 콘솔 응용 프로그램에 대 한 기본 구조를 사용 하 고 사용 하는 메서드를 `My` 명령줄 인수에 대 한 합니다.  
  
     [!code-vb[VbVbalrGuidelines#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_2.vb)]  
  
## <a name="language-guidelines"></a>언어 지침  
  
### <a name="string-data-type"></a>String 데이터 형식  
  
-   문자열을 연결 하려면 앰퍼샌드를 사용 (&).  
  
     [!code-vb[VbVbalrGuidelines#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_3.vb)]  
  
-   루프에 문자열에 추가 하려면 사용 하 여는 <xref:System.Text.StringBuilder> 개체입니다.  
  
     [!code-vb[VbVbalrGuidelines#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_4.vb)]  
  
### <a name="relaxed-delegates-in-event-handlers"></a>완화 된 대리자 이벤트 처리기  
 이벤트 처리기에 (개체 및 EventArgs) 인수를 명시적으로 적합 하지 않습니다. 이벤트 (예를 들어 보낸 사람 개체로, EventArgs e)에 전달 되는 이벤트 인수를 사용 하지 않는 경우에 완화 된 대리자를 사용 하 고 코드에서 이벤트 인수를:  
  
 [!code-vb[VbVbalrGuidelines#7](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_5.vb)]  
  
### <a name="unsigned-data-type"></a>부호 없는 데이터 형식  
  
-   사용 하 여 `Integer` 는 필요한 제외 하 고 부호 없는 형식 대신 합니다.  
  
### <a name="arrays"></a>배열  
  
-   선언 줄에서 배열을 초기화할 때 간단한 구문을 사용 합니다. 예를 들어 다음 구문을 사용 합니다.  
  
     [!code-vb[VbVbalrGuidelines#8](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_6.vb)]  
  
     다음 구문을 사용 하지 마십시오.  
  
     [!code-vb[VbVbalrGuidelines#9](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_7.vb)]  
  
-   변수가 아니라 형식에 배열 지정자를 넣습니다. 예를 들어 다음 구문을 사용 합니다.  
  
     [!code-vb[VbVbalrGuidelines#11](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_8.vb)]  
  
     다음 구문을 사용 하지 마십시오.  
  
     [!code-vb[VbVbalrGuidelines#10](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_9.vb)]  
  
-   선언 하 고 기본 데이터 형식의 배열을 초기화할 때 {} 구문을 사용 합니다. 예를 들어 다음 구문을 사용 합니다.  
  
     [!code-vb[VbVbalrGuidelines#12](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_10.vb)]  
  
     다음 구문을 사용 하지 마십시오.  
  
     [!code-vb[VbVbalrGuidelines#13](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_11.vb)]  
  
### <a name="use-the-with-keyword"></a>사용 하는 키워드와 함께  
 사용 하는 일련의 하나 이상의 개체에 대 한 호출을 수행 하면 고려는 `With` 키워드:  
  
 [!code-vb[VbVbalrGuidelines#15](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_12.vb)]  
  
### <a name="use-the-trycatch-and-using-statements-when-you-use-exception-handling"></a>Try 사용 함 Catch 및 문을 사용 하 여 예외 처리를 사용 하는 경우  
 사용 하지 마십시오 `On Error Goto`합니다.  
  
### <a name="use-the-isnot-keyword"></a>IsNot 키워드를 사용 하 여  
 사용 하 여 `IsNot` 키워드 대신 `Not...Is Nothing`합니다.  
  
### <a name="new-keyword"></a>New 키워드  
  
-   간단한 인스턴스를 사용 합니다. 예를 들어 다음 구문을 사용 합니다.  
  
     [!code-vb[VbVbalrGuidelines#21](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_13.vb)]  
  
     앞의 줄이 같습니다.  
  
     [!code-vb[VbVbalrGuidelines#22](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_14.vb)]  
  
-   매개 변수가 없는 생성자 대신 새 개체에 대 한 개체 이니셜라이저를 사용 합니다.  
  
     [!code-vb[VbVbalrGuidelines#23](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_15.vb)]  
  
### <a name="event-handling"></a>이벤트 처리  
  
-   사용 하 여 `Handles` 대신 `AddHandler`:  
  
     [!code-vb[VbVbalrGuidelines#24](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_16.vb)]  
  
-   사용 하 여 `AddressOf`, 대리자를 명시적으로 인스턴스화합니다 않습니다:  
  
     [!code-vb[VbVbalrGuidelines#25](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_17.vb)]  
  
-   이벤트를 정의 하는 경우 간단한 구문을 사용 하 고 고 컴파일러에서 대리자를 정의 합니다.  
  
     [!code-vb[VbVbalrGuidelines#26](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_18.vb)]  
  
-   이벤트 인지를 확인 하지 않습니다 `Nothing` (null)를 호출 하기 전에 `RaiseEvent` 메서드. `RaiseEvent` 에 대 한 확인 `Nothing` 전에 이벤트를 발생 시킵니다.  
  
### <a name="using-shared-members"></a>공유 멤버 사용  
 호출 `Shared` 클래스 이름에서가 아니라 인스턴스 변수를 사용 하 여 멤버입니다.  
  
### <a name="use-xml-literals"></a>XML 리터럴을 사용 하십시오.  
 XML 리터럴의 XML (예를 들어, 로드, 쿼리 및 변환)를 사용 하 여 작업할 때 발생할 수 있는 가장 일반적인 작업을 간소화 합니다. XML로 개발 하는 경우 다음이 지침을 따르십시오.  
  
-   XML 리터럴을 사용 하 여 XML 문서 및 XML Api를 직접 호출 하는 대신 조각을 만듭니다.  
  
-   XML 리터럴에 대 한 성능 최적화를 활용 하도록 파일 또는 프로젝트 수준에서 XML 네임 스페이스를 가져옵니다.  
  
-   XML 축 속성을 사용 하 여 특성과 해당 요소는 XML 문서에 액세스할 수 있습니다.  
  
-   포함된 식을 사용 하 여 값을 포함 하 고와 같은 API 호출을 사용 하는 대신 기존 값에서 XML을 만들 수는 `Add` 메서드:  
  
     [!code-vb[VbVbalrGuidelines#27](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_19.vb)]  
  
### <a name="linq-queries"></a>LINQ 쿼리  
  
-   쿼리 변수에 대 한 의미 있는 이름을 사용 합니다.  
  
     [!code-vb[VbVbalrGuidelines#28](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_20.vb)]  
  
-   익명 형식의 속성 이름이 올바르게 대문자로 표시 되도록 파스칼식을 사용 하 여 쿼리에서 요소에 대 한 이름을 제공 대/소문자 구분:  
  
     [!code-vb[VbVbalrGuidelines#29](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_21.vb)]  
  
-   결과의 속성 이름이 모호하면 속성 이름을 바꿉니다. 예를 들어 쿼리에서 고객 이름 및 주문 ID를 반환 하는 경우 이름을 그대로 두는 대신 `Name` 및 `ID` 결과에서:  
  
     [!code-vb[VbVbalrGuidelines#30](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_22.vb)]  
  
-   쿼리 변수 및 범위 변수 선언에서 형식 유추를 사용 합니다.  
  
     [!code-vb[VbVbalrGuidelines#31](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_23.vb)]  
  
-   아래의 쿼리 절을 정렬 된 `From` 문:  
  
     [!code-vb[VbVbalrGuidelines#32](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_24.vb)]  
  
-   사용 하 여 `Where` 뒷부분의 쿼리 절 데이터의 필터링 된 집합에서 사용할 수 있도록 다른 앞에 절 쿼리 절:  
  
     [!code-vb[VbVbalrGuidelines#33](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_25.vb)]  
  
-   사용 하 여는 `Join` 절을 사용 하는 대신 조인 작업을 명시적으로 정의 된 `Where` 암시적으로 조인 작업을 정의 하는 절:  
  
     [!code-vb[VbVbalrGuidelines#34](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_26.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [보안 코딩 지침](../../../standard/security/secure-coding-guidelines.md)
