---
title: "속성 및 메서드 (Visual Basic)를 오버 로드 된 | Microsoft 문서"
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
- properties [Visual Basic], overloading
- methods [Visual Basic], overloading
- shadowing
- names, multiple procedures with same
- procedures, mulltiples with same name
- classes [Visual Basic], properties
- classes [Visual Basic], methods
- method overloading
- Overloads keyword, overloaded members
ms.assetid: b686fb97-e7d7-4001-afaa-6650cba08f0d
caps.latest.revision: 12
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
ms.openlocfilehash: 6f379f04ca9b75161baf2bf2c33e87f05a9edf97
ms.lasthandoff: 03/13/2017

---
# <a name="overloaded-properties-and-methods-visual-basic"></a>오버로드된 속성 및 메서드(Visual Basic)
오버 로딩은 둘 이상의 프로시저, 인스턴스 생성자 또는 속성 이름은 같지만 다른 형식의 인수를 사용 하 여 클래스에 생성 합니다.  
  
## <a name="overloading-usage"></a>오버 로드 사용  
 오버 로드 개체 모델에 다른 데이터 형식에서 작동 하는 프로시저에 대 한 동일한 이름을 사용 하도록 요구할 때 특히 유용 합니다. 예를 들어, 여러 다른 데이터 형식을 표시할 수 있는 클래스를 가지기 `Display` 프로시저를 다음과 같이 합니다.  
  
 [!code-vb[VbVbalrOOP #&64;](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_1.vb)]  
  
 오버 로드 하지 않고 해야 각 프로시저에 대 한 고유 이름을 만들기 위해 다음과 같이 동일한 작업을 그럴 경우에:  
  
 [!code-vb[VbVbalrOOP #&65;](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_2.vb)]  
  
 오버 로드 하면 다양 한 데이터 형식 사용할 수 있는 제공 하기 때문에 속성이 나 메서드를 사용 하 여 쉽게 있습니다. 예를 들어, 오버 로드 된 `Display` 다음 줄의 코드를 사용 하 여 호출할 수 이전에 앞에서 설명한 메서드:  
  
 [!code-vb[VbVbalrOOP #&66;](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_3.vb)]  
  
 런타임 시 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 올바른 프로시저 매개 변수의 데이터 형식에 따라 호출을 지정 합니다.  
  
## <a name="overloading-rules"></a>오버 로드 규칙  
 두 개 이상의 속성 또는 동일한 이름 가진 메서드를 추가 하 여 클래스에 대 한 오버 로드 된 멤버를 만듭니다. 파생된 멤버 오버 로드를 제외 하 고 각 멤버는 다른 매개 변수 목록을 있어야 하 고 속성이 나 프로시저를 오버 로드할 때 다음 항목을 별도 기능으로 사용할 수 없습니다.  
  
-   한정자와 같은 `ByVal` 또는 `ByRef`, 멤버 또는 멤버의 매개 변수를 적용 합니다.  
  
-   매개 변수 이름  
  
-   프로시저의 반환 형식  
  
 `Overloads` 키워드는 오버 로드 하는 경우 선택 사항 이지만 멤버를 사용 하는 경우 오버 로드는 `Overloads` 키워드를 다음 같은 이름 가진 다른 모든 오버 로드 된 멤버 해야이 키워드를 지정 합니다.  
  
 파생된 클래스에서 상속된 된 멤버를 동일한 매개 변수 및 매개 변수 형식, 즉, 멤버를 오버 로드할 수 있습니다 *이름 및 서명을 숨길*합니다. 하는 경우는 `Overloads` 이름 및 시그니처로 숨김에 멤버의 경우 파생된 클래스의 구현 대신 사용 됩니다 기본 클래스에서 구현 하 고 해당 멤버에 대 한 다른 모든 오버 로드는 파생된 클래스의 인스턴스를 사용할 수 있습니다 때 키워드를 사용 합니다.  
  
 하는 경우는 `Overloads` 키워드를 생략 하면 동일한 매개 변수 및 매개 변수 형식, 멤버와 상속된 된 멤버를 오버 로드할 때 다음는 오버 로딩 이라고 *이름 숨김은*합니다. 상속 된 멤버의 구현을 대체 이름 숨김은 하 고 다른 모든 오버 로드는 파생된 클래스 및 관련 계승자의 인스턴스를 사용할 수 없는입니다.  
  
 `Overloads` 및 `Shadows` 한정자 동일한 속성 또는 메서드를 함께 사용할 수 없습니다.  
  
### <a name="example"></a>예제  
 다음 예제에서는 오버 로드 된 메서드 중 하나를 허용 하는 한 `String` 또는 `Decimal` 달러 금액 및 반환 판매세가 포함 된 문자열 표현입니다.  
  
##### <a name="to-use-this-example-to-create-an-overloaded-method"></a>이 예제를 사용 하려면이 오버 로드 된 메서드를 만들려면  
  
1.  라는 클래스를 추가 하 고 새 프로젝트를 열고 `TaxClass`합니다.  
  
2.  `TaxClass` 클래스에 다음 코드를 추가합니다.  
  
     [!code-vb[VbVbalrOOP #&67;](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_4.vb)]  
  
3.  다음 절차를 폼에 추가 합니다.  
  
     [!code-vb[VbVbalrOOP #&68;](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_5.vb)]  
  
4.  폼 및 호출에 단추 추가 `ShowTax` 에서 프로시저는 `Button1_Click` 단추의 이벤트입니다.  
  
5.  프로젝트를 실행 하 고 테스트는 오버 로드 된 폼에서 단추를 클릭 `ShowTax` 프로시저입니다.  
  
 런타임 시 컴파일러는 사용 중인 매개 변수와 일치 하는 적절 한 오버 로드 된 함수를 선택 합니다. 단추를 클릭할 경우의 오버 로드 된 메서드는 먼저는 `Price` 매개 변수를 문자열 및 메시지를 "가격은 문자열입니다. 세금은 $5.12"표시 됩니다. `TaxAmount`호출 되는 `Decimal` 값, 두 번째 시간 및 메시지, "가격을&10; 진수로. 세금은 $5.12"표시 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [개체 및 클래스](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Visual Basic의 숨김 기능](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)   
 [Sub 문](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [상속 기본 사항](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)   
 [그림자](../../../../visual-basic/language-reference/modifiers/shadows.md)   
 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)   
 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)   
 [오버 로드](../../../../visual-basic/language-reference/modifiers/overloads.md)   
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
