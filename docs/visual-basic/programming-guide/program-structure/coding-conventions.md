---
title: "Visual Basic 코딩 규칙 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- coding conventions, Visual Basic
- examples [Visual Basic], coding conventions
- Visual Basic code, conventions
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
caps.latest.revision: 48
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 5712f14d53b86552a0b82af38ecf579577ef3fa1
ms.lasthandoff: 03/13/2017

---
# <a name="visual-basic-coding-conventions"></a>Visual Basic 코딩 규칙
Microsoft 예제 및이 항목의 지침에 따라 설명서를 개발 합니다. 동일한 코딩 규칙을 따르는 경우에 다음과 같은 이점을 얻을 수 있습니다.  
  
-   코드는 판독기 레이아웃이 아닌 내용에 집중할 수 있도록 일관 된 모양을 갖습니다.  
  
-   판독기 코드를 이해 더 신속 하 게 이전 경험을 기반으로 예상할 수 수 있기 때문에 있습니다.  
  
-   복사, 변경 및 코드를 더 쉽게 유지 관리할 수 있습니다.  
  
-   Visual basic 코드 "모범 사례" 보여 주는 확인할 수 있습니다.  
  
## <a name="naming-conventions"></a>명명 규칙  
  
-   이름 지정 지침에 대 한 정보를 참조 하십시오. [명명 지침](http://msdn.microsoft.com/library/fc076d66-9b5f-42d3-aa65-61d970c794a3) 항목입니다.  
  
-   변수 이름의 일부로 "내" 또는 "my"를 사용 하지 마십시오. 이 사례와 혼동의 `My` 개체입니다.  
  
-   지침에 맞게 자동으로 생성 된 코드에서 개체의 이름을 변경할 필요가 없습니다.  
  
## <a name="layout-conventions"></a>레이아웃 규칙  
  
-   공백, 탭을 삽입 하 고&4; 공간 들여쓰기와 스마트 들여쓰기를 사용 하 여 키를 누릅니다.  
  
-   사용 하 여 **(다시 포맷)의 코드를 나열 하는 상당히** 코드 편집기에서 코드를 다시 포맷 하 합니다. 자세한 내용은 참조 [옵션, 텍스트 편집기, 기본 (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/options-text-editor-basic-visual-basic)합니다.  
  
-   줄당 하나의 문을 사용 합니다. Visual Basic 줄 구분 기호 문자 (:)을 사용 하지 마십시오.  
  
-   언어에서 허용 하는 경우 항상 암시적 줄 연속 문자를 기준으로 명시적 줄 연속 문자 "_"을 사용 하지 마십시오.  
  
-   하나의 선언을 한 줄을 사용 합니다.  
  
-   경우 **(다시 포맷)의 코드를 나열 하는 상당히** 하지 형식 연속 줄 수동으로 자동으로 들여쓰기 연속 된 줄을 탭 정지 하나입니다. 그러나 항상 왼쪽 맞춤 목록에서 항목입니다.  
  
    ```  
    a As Integer,  
    b As Integer  
    ```  
  
-   메서드 및 속성 정의 사이 하나 이상의 빈 줄을 추가 합니다.  
  
## <a name="commenting-conventions"></a>주석 규칙  
  
-   코드 줄의 끝에 대신 별도 줄에 설명을 입력 합니다.  
  
-   마침표로 종료 주석 텍스트 및 주석 텍스트는 대문자로 시작 합니다.  
  
-   주석 구분 기호 (')와 주석 텍스트 사이 공백을 하나 삽입 합니다.  
  
     [!code-vb[VbVbalrGuidelines #&2;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_1.vb)]  
  
-   에 서식이 지정 된 별표 블록으로 묶습니다 하지 마십시오.  
  
## <a name="program-structure"></a>프로그램 구조  
  
-   사용 하는 경우는 `Main` 새 콘솔 응용 프로그램에 대 한 기본 구조를 사용 하 고 사용 하는 메서드를 `My` 명령줄 인수에 대 한 합니다.  
  
     [!code-vb[VbVbalrGuidelines #&3;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_2.vb)]  
  
## <a name="language-guidelines"></a>언어 지침  
  
### <a name="string-data-type"></a>String 데이터 형식  
  
-   문자열을 연결 하려면 앰퍼샌드 (&)를 사용 합니다.  
  
     [!code-vb[VbVbalrGuidelines #&4;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_3.vb)]  
  
-   문자열을 루프를 추가 하려면 사용 된 <xref:System.Text.StringBuilder>개체.</xref:System.Text.StringBuilder>  
  
     [!code-vb[VbVbalrGuidelines #&5;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_4.vb)]  
  
### <a name="relaxed-delegates-in-event-handlers"></a>완화 된 대리자 이벤트 처리기에  
 이벤트 처리기에 (개체와 EventArgs) 인수를 명시적으로 적합 하지 않습니다. 이벤트 (예를 들어 보낸 사람 e EventArgs 개체로)에 전달 되는 이벤트 인수를 사용 하지 않는 경우에 완화 된 대리자를 사용 하 고 코드에서 이벤트 인수를:  
  
 [!code-vb[VbVbalrGuidelines #&7;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_5.vb)]  
  
### <a name="unsigned-data-type"></a>부호 없는 데이터 형식  
  
-   사용 하 여 `Integer` 는 필요한 제외 하 고 부호 없는 형식 대신 합니다.  
  
### <a name="arrays"></a>배열  
  
-   선언 줄에서 배열을 초기화할 때는 간단한 구문을 사용 합니다. 예를 들어 다음 구문을 사용 합니다.  
  
     [!code-vb[VbVbalrGuidelines #&8;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_6.vb)]  
  
     다음 구문을 사용 하지 마십시오.  
  
     [!code-vb[VbVbalrGuidelines #&9;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_7.vb)]  
  
-   변수 아니라 형식에 배열 지정자를 넣습니다. 예를 들어 다음 구문을 사용 합니다.  
  
     [!code-vb[VbVbalrGuidelines #&11;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_8.vb)]  
  
     다음 구문을 사용 하지 않습니다.  
  
     [!code-vb[VbVbalrGuidelines #&10;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_9.vb)]  
  
-   선언 하 고 기본 데이터 형식의 배열을 초기화할 때 {} 구문을 사용 합니다. 예를 들어 다음 구문을 사용 합니다.  
  
     [!code-vb[VbVbalrGuidelines #&12;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_10.vb)]  
  
     다음 구문을 사용 하지 않습니다.  
  
     [!code-vb[VbVbalrGuidelines #&13;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_11.vb)]  
  
### <a name="use-the-with-keyword"></a>사용 하는 With 키워드  
 사용 하 여 일련의 하나 이상의 개체에 대 한 호출을 수행 하면 고려는 `With` 키워드:  
  
 [!code-vb[VbVbalrGuidelines #&15;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_12.vb)]  
  
### <a name="use-the-trycatch-and-using-statements-when-you-use-exception-handling"></a>Try를 사용 하 여... Catch 및 예외 처리를 사용 하는 때를 사용 하 여 문  
 사용 하지 않는 `On Error Goto`합니다.  
  
### <a name="use-the-isnot-keyword"></a>IsNot 키워드를 사용 하 여  
 사용 하 여 `IsNot` 키워드 대신 `Not...Is Nothing`합니다.  
  
### <a name="new-keyword"></a>New 키워드  
  
-   간단한 인스턴스를 사용 합니다. 예를 들어 다음 구문을 사용 합니다.  
  
     [!code-vb[VbVbalrGuidelines #&21;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_13.vb)]  
  
     앞의 줄이 하는 것과 같습니다.  
  
     [!code-vb[VbVbalrGuidelines #&22;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_14.vb)]  
  
-   매개 변수가 없는 생성자 대신 새 개체에 대 한 개체 이니셜라이저를 사용 합니다.  
  
     [!code-vb[VbVbalrGuidelines&23;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_15.vb)]  
  
### <a name="event-handling"></a>이벤트 처리  
  
-   사용 하 여 `Handles` 대신 `AddHandler`:  
  
     [!code-vb[VbVbalrGuidelines #&24;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_16.vb)]  
  
-   사용 하 여 `AddressOf`, 대리자를 명시적으로 인스턴스화합니다 않습니다.  
  
     [!code-vb[VbVbalrGuidelines #&25;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_17.vb)]  
  
-   이벤트를 정의 하는 경우 간단한 구문을 사용 하 고 대리자를 정의 하 여 컴파일러가 합니다.  
  
     [!code-vb[VbVbalrGuidelines #&26;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_18.vb)]  
  
-   이벤트 인지 여부를 확인 하지 않는 `Nothing` (null)를 호출 하기 전에 `RaiseEvent` 메서드. `RaiseEvent`에 대 한 검사 `Nothing` 전에 이벤트를 발생 시킵니다.  
  
### <a name="using-shared-members"></a>공유 멤버를 사용 하 여  
 호출 `Shared` 클래스 이름에서가 아니라 인스턴스 변수를 사용 하 여 멤버입니다.  
  
### <a name="use-xml-literals"></a>XML 리터럴을 사용 하십시오.  
 XML 리터럴 XML (예를 들어, 로드, 쿼리 및 변환)를 사용 하 여 작업할 때 발생 하는 가장 일반적인 작업을 간소화 합니다. XML을 개발할 때 다음이 지침을 따르십시오.  
  
-   XML 리터럴을 사용 하 여 XML 문서 및 XML Api를 직접 호출 하는 대신 조각을 만듭니다.  
  
-   XML 리터럴에 대 한 성능 최적화를 활용 하기 위해 파일 또는 프로젝트 수준에서 XML 네임 스페이스를 가져옵니다.  
  
-   XML 축 속성을 사용 하 여 특성과 해당 요소는 XML 문서에 액세스할 수 있습니다.  
  
-   포함된 식을 사용 하 여 값을 포함 하 고와 같은 API 호출을 사용 하는 대신 기존 값에서 XML을 만들 수는 `Add` 메서드:  
  
     [!code-vb[VbVbalrGuidelines #&27;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_19.vb)]  
  
### <a name="linq-queries"></a>LINQ 쿼리  
  
-   쿼리 변수에 의미 있는 이름을 사용 합니다.  
  
     [!code-vb[VbVbalrGuidelines #&28;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_20.vb)]  
  
-   익명 형식의 속성 이름이 소문자를 올바르게 표시 파스칼식 대를 사용 하 여 확인할 수 있도록 쿼리에서 요소에 대 한 이름 대/소문자 구분:  
  
     [!code-vb[VbVbalrGuidelines #&29;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_21.vb)]  
  
-   결과의 속성 이름이 모호하면 속성 이름을 바꿉니다. 예를 들어 쿼리에서 고객 이름 및 주문 ID를 반환 바꾸라는 그대로 유지 하는 대신 `Name` 및 `ID` 결과에서:  
  
     [!code-vb[VbVbalrGuidelines #&30;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_22.vb)]  
  
-   쿼리 변수 및 범위 변수 선언에 형식 유추를 사용 합니다.  
  
     [!code-vb[VbVbalrGuidelines #&31;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_23.vb)]  
  
-   아래의 쿼리 절을 정렬 된 `From` 문:  
  
     [!code-vb[VbVbalrGuidelines #&32;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_24.vb)]  
  
-   사용 하 여 `Where` 다른 앞 절 쿼리 절 나중 쿼리 절이 필터링된 된 데이터 집합에서 실행 되도록 합니다.  
  
     [!code-vb[VbVbalrGuidelines #&33;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_25.vb)]  
  
-   사용 하 여는 `Join` 절을 사용 하는 대신 조인 작업을 명시적으로 정의 된 `Where` 암시적으로 조인 작업을 정의 하는 절:  
  
     [!code-vb[VbVbalrGuidelines #&34;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_26.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [보안 코딩 지침](http://msdn.microsoft.com/library/4f882d94-262b-4494-b0a6-ba9ba1f5f177)
