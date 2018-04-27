---
title: 오버 로드 된 속성 및 메서드 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- properties [Visual Basic], overloading
- methods [Visual Basic], overloading
- shadowing
- names [Visual Basic], multiple procedures with same
- procedures [Visual Basic], mulltiples with same name
- classes [Visual Basic], properties
- classes [Visual Basic], methods
- method overloading
- Overloads keyword [Visual Basic], overloaded members
ms.assetid: b686fb97-e7d7-4001-afaa-6650cba08f0d
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 96d5ef2462f5312baa5269865977596035a254d5
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="overloaded-properties-and-methods-visual-basic"></a>오버 로드 된 속성 및 메서드 (Visual Basic)

오버 로드은 둘 이상의 인스턴스 생성자의에서 프로시저 또는 속성 이름은 같지만 서로 다른 인수 형식을 사용 하는 클래스를 만드는 것입니다.  
  
## <a name="overloading-usage"></a>오버 로드 사용

 오버 로드 개체 모델이 다른 데이터 형식에서 작동 하는 프로시저에 대 한 동일한 이름을 사용 하도록 요구할 때 특히 유용 합니다. 예를 들어 여러 다른 데이터 형식을 표시할 수 있는 클래스를 가지기 `Display` 는 다음과 같은 프로시저:  
  
 [!code-vb[VbVbalrOOP#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#64)]
  
 하지 않으면 오버 로드 해야 각 프로시저에 대 한 고유 이름을 만들려면 다음 예와 같이 동일한 작업을 수행 하는 경우에:  
  
 [!code-vb[VbVbalrOOP#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#65)]
  
 오버 로드 하면 보다 쉽게 사용할 수 있는 데이터 형식의 선택 항목을 제공 하기 때문에 속성이 나 메서드를 사용 합니다. 예를 들어 오버 로드 된 `Display` 다음 줄의 코드를 사용 하 여 호출할 수 이전에 앞에서 설명한 메서드:  
  
 [!code-vb[VbVbalrOOP#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#66)]
  
 Visual Basic 런타임 시 지정한 매개 변수의 데이터 형식을 기반으로 올바른 프로시저를 호출 합니다.  
  
## <a name="overloading-rules"></a>규칙 오버 로드

 둘 이상의 속성이 나 같은 이름의 메서드를 추가 하 여 클래스에 대 한 오버 로드 된 멤버를 만듭니다. 오버 로드 된 파생된 멤버를 제외 하 고 각 멤버는 다른 매개 변수 목록을 있어야 하 고 속성 또는 프로시저를 오버 로드할 때 다음 항목을 별도 기능으로 사용할 수 없습니다.  
  
-   한정자를 같은 `ByVal` 또는 `ByRef`, 멤버 또는 멤버의 매개 변수를 적용 합니다.  
  
-   매개 변수 이름  
  
-   프로시저의 반환 형식  
  
 `Overloads` 키워드는 오버 로드 하는 경우 선택 사항 이지만 구성원 사용 하 여 오버 로드 된 있는 경우는 `Overloads` 키워드를 다음 동일한 이름 가진 다른 모든 오버 로드 된 멤버 해야이 키워드를 지정 합니다.  
  
 파생된 클래스에서 상속된 된 멤버를 동일한 매개 변수 및 매개 변수 형식, 즉, 멤버를 오버 로드할 수 있습니다 *이름 및 서명을 갖는*합니다. 경우는 `Overloads` 이름 및 서명을 갖는, 멤버의 파생된 클래스의 구현 대신 사용할 기본 클래스에서 구현 하 고 해당 멤버에 대 한 다른 모든 오버 로드의 인스턴스를 사용할 수 있습니다 때 키워드가 사용 되는 파생된 클래스입니다.  
  
 경우는 `Overloads` 동일한 매개 변수 및 매개 변수 형식, 멤버와 상속된 된 멤버를 오버 로드할 때 키워드를 생략 한 후 호출 되는 오버 로딩 *이름 숨김은*합니다. 멤버의 상속 된 구현을 대체 이름 숨김은 하 고 다른 모든 오버 로드와 관련 계승자 파생된 클래스의 인스턴스를 사용할 수 없는입니다.  
  
 `Overloads` 및 `Shadows` 한정자 동일한 속성 또는 메서드를 함께 사용할 수 없습니다.  
  
### <a name="example"></a>예제

 다음 예제에서는 중 하나를 허용 하는 오버 로드 된 메서드는 `String` 또는 `Decimal` 달러 금액 및 반환 세율이 포함 하는 문자열 표현입니다.  
  
#### <a name="to-use-this-example-to-create-an-overloaded-method"></a>오버 로드 된 메서드를 만들려면이 예제를 사용 하려면
  
1.  새 프로젝트를 열고 라는 클래스를 추가 `TaxClass`합니다.  
  
2.  `TaxClass` 클래스에 다음 코드를 추가합니다.  
  
     [!code-vb[VbVbalrOOP#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#67)]
  
3.  다음 절차를 폼에 추가 합니다.  
  
     [!code-vb[VbVbalrOOP#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#68)]
  
4.  단추를 폼과 호출 추가 `ShowTax` 에서 프로시저는 `Button1_Click` 단추의 이벤트가 합니다.  
  
5.  프로젝트를 실행 하 고 오버 로드 된 테스트 하려면 폼에서 단추 클릭 `ShowTax` 프로시저입니다.  
  
 컴파일러는 실행 시 사용 되는 매개 변수와 일치 하는 적절 한 오버 로드 된 함수를 선택 합니다. 오버 로드 된 메서드를 먼저 호출한 단추를 클릭할 때 한 `Price` 문자열이 고 "가격은 문자열입니다 메시지를 매개 변수. 세금은 $5.12"표시 됩니다. `TaxAmount` 로 호출 되는 `Decimal` 값, 두 번째 시간 및 메시지, "가격을 10 진수로. 세금은 $5.12"표시 됩니다.  
  
## <a name="see-also"></a>참고자료

 [개체 및 클래스](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [Visual Basic의 숨김 기능](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [Sub 문](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [상속 기본 사항](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)  
 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)  
 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)  
 [오버로드](../../../../visual-basic/language-reference/modifiers/overloads.md)  
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
