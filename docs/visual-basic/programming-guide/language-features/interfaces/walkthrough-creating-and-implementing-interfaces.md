---
title: 인터페이스 (Visual Basic) 만들기 및 구현
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [Visual Basic], walkthroughs
- interfaces [Visual Basic], testing
- interface implementation [Visual Basic], walkthrough
- interfaces [Visual Basic], creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
ms.openlocfilehash: af9305deb60637b642d091501e743f2c7a57ccad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33653613"
---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a>연습: 인터페이스 만들기 및 구현(Visual Basic)

인터페이스 속성, 메서드 및 이벤트의 특성을 설명 하지만 구조체나 클래스 구현 세부 사항을 합니다.  
  
 이 연습에는 선언 및 인터페이스를 구현 하는 방법을 보여 줍니다.  
  
> [!NOTE]
>  이 연습에서는 사용자 인터페이스를 만드는 방법에 대 한 정보를 제공 하지 않습니다.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-an-interface"></a>인터페이스를 정의 하려면
  
1.  새 Visual Basic Windows 응용 프로그램 프로젝트를 엽니다.  
  
2.  새 모듈을 클릭 하 여 프로젝트에 추가할 **모듈 추가** 에 **프로젝트** 메뉴.  
  
3.  새 모듈의 이름을 `Module1.vb` 클릭 **추가**합니다. 새 모듈에 대 한 코드가 표시 됩니다.  
  
4.  라는 인터페이스를 정의 `TestInterface` 내 `Module1` 입력 하 여 `Interface TestInterface` 사이 `Module` 및 `End Module` 문, 한 다음 ENTER 키입니다. **코드 편집기** 들여쓰기는 `Interface` 키워드 추가 `End Interface` 코드 블록을 형성 하는 문입니다.  
  
5.  사이 다음 코드를 배치 하 여 속성, 메서드 및 인터페이스에 대 한 이벤트 정의 `Interface` 및 `End Interface` 문:  
  
     [!code-vb[VbVbalrOOP#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#98)]
  
## <a name="implementation"></a>구현

 인터페이스 멤버를 선언 하는 데 사용 하는 구문을 클래스 멤버를 선언 하는 데 사용 되는 구문에서 다른 임을 알 수 있습니다. 이러한 차이 인터페이스 구현 코드가 포함 될 수 없음을 의미 합니다.  
  
### <a name="to-implement-the-interface"></a>인터페이스를 구현 하려면
  
1.  라는 클래스를 추가 `ImplementationClass` 다음 문을 추가 하 여 `Module1`이후에 `End Interface` 문의 하기 전에 `End Module` 문, 한 다음 ENTER 키:  
  
     [!code-vb[VbVbalrOOP#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#99)]
  
     통합된 개발 환경에서 작업 하는 경우는 **코드 편집기** 에서 짝 `End Class` ENTER 키를 누르면 문.  
  
2.  다음 추가 `Implements` 문을 `ImplementationClass`를 구현 하는 인터페이스 클래스의 이름을:  
  
     [!code-vb[VbVbalrOOP#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#100)]
  
     클래스 또는 구조의 맨 위에 있는 다른 항목과 별도로 나열 하는 경우는 `Implements` 문은 구조체 또는 클래스 인터페이스를 구현 함을 나타냅니다.  
  
     통합된 개발 환경에서 작업 하는 경우는 **코드 편집기** 클래스 멤버에 필요한 구현 `TestInterface` 때 ENTER 키를 누릅니다 하 고 다음 단계를 건너뛸 수 있습니다.  
  
3.  인터페이스의 모든 멤버를 구현 해야 통합된 개발 환경 내에서 작동 하지 않는 경우 `MyInterface`합니다. 다음 코드를 추가 `ImplementationClass` 구현 하려면 `Event1`, `Method1`, 및 `Prop1`:  
  
     [!code-vb[VbVbalrOOP#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#101)]
  
     `Implements` 문은 인터페이스와 구현 되는 인터페이스 멤버를 명명 합니다.  
  
4.  정의 완료 `Prop1` 속성 값을 저장 하는 클래스에 전용 필드를 추가 하 여:  
  
     [!code-vb[VbVbalrOOP#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#102)]
  
     값을 반환 된 `pval` 속성에서 get 접근자입니다.  
  
     [!code-vb[VbVbalrOOP#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#103)]
  
     값을 설정할 `pval` 속성에 set 접근자입니다.  
  
     [!code-vb[VbVbalrOOP#104](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#104)]
  
5.  정의 완료 `Method1` 다음 코드를 추가 하 여 합니다.  
  
     [!code-vb[VbVbalrOOP#105](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#105)]
  
### <a name="to-test-the-implementation-of-the-interface"></a>인터페이스의 구현을 테스트 하려면
  
1.  프로젝트에 대 한 시작 폼을 마우스 오른쪽 단추로 클릭는 **솔루션 탐색기**를 클릭 하 고 **코드 보기**합니다. 편집기 시작 폼에 대 한 클래스를 표시합니다. 기본적으로 시작 폼 이름은 `Form1`합니다.  
  
2.  다음 추가 `testInstance` 필드는 `Form1` 클래스:  
  
     [!code-vb[VbVbalrOOP#120](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#120)]
  
     선언 하 여 `testInstance` 으로 `WithEvents`, `Form1` 클래스에는 해당 이벤트를 처리할 수 있습니다.  
  
3.  다음 이벤트 처리기를 추가 `Form1` 에 의해 발생 하는 이벤트를 처리 하는 클래스 `testInstance`:  
  
     [!code-vb[VbVbalrOOP#106](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#106)]
  
4.  라는 서브루틴 추가 `Test` 에 `Form1` 클래스 구현 클래스를 테스트 하려면:  
  
     [!code-vb[VbVbalrOOP#107](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#107)]
  
     `Test` 프로시저 구현 하는 클래스의 인스턴스를 만들고 `MyInterface`, 할당 하도록 해당 인스턴스는 `testInstance` 필드 속성을 설정 및 인터페이스를 통해 메서드를 실행 합니다.  
  
5.  호출 하는 코드를 추가 `Test` 에서 프로시저는 `Form1 Load` 시작 폼의 프로시저:  
  
     [!code-vb[VbVbalrOOP#108](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#108)]
  
6.  실행 된 `Test` f5 키를 눌러 프로시저입니다. 메시지 "Prop1으로 설정 된 9" 표시 됩니다. "Method1에 대 한 X 매개 변수는 5입니다"가 표시 되는 메시지 확인을 클릭 합니다. 확인을 클릭 하 고 "이벤트 처리기는 이벤트를 발생 하는 데 사용" 메시지 표시 됩니다.  
  
## <a name="see-also"></a>참고자료

 [Implements 문](../../../../visual-basic/language-reference/statements/implements-statement.md)  
 [인터페이스](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)  
 [Interface 문](../../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Event 문](../../../../visual-basic/language-reference/statements/event-statement.md)  