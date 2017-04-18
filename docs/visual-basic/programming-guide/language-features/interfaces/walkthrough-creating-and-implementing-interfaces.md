---
title: "인터페이스 (Visual Basic) 만들기 및 구현 | Microsoft 문서"
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
- interfaces, walkthroughs
- interfaces, testing
- interface implementation, walkthrough
- interfaces, creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
caps.latest.revision: 22
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
ms.openlocfilehash: 076bc8d33e97286c31f27a2016e39a25e9cec22c
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a>연습: 인터페이스 만들기 및 구현(Visual Basic)
인터페이스는 속성, 메서드 및 이벤트의 특징을 설명 하지만 구조체나 클래스는 구현 세부 정보입니다.  
  
 이 연습에는 선언 및 인터페이스를 구현 하는 방법을 보여 줍니다.  
  
> [!NOTE]
>  이 연습에서는 사용자 인터페이스를 만드는 방법에 대 한 정보를 제공 하지 않습니다.  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-define-an-interface"></a>인터페이스를 정의 하려면  
  
1.  새 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Windows 응용 프로그램 프로젝트입니다.  
  
2.  새 모듈을 클릭 하 여 프로젝트에 추가 **모듈 추가** 에 **프로젝트** 메뉴.  
  
3.  새 모듈의 이름을 `Module1.vb` 클릭 **추가**합니다. 새 모듈에 대 한 코드가 표시 됩니다.  
  
4.  라는 인터페이스를 정의 `TestInterface` 내 `Module1` 입력 하 여 `Interface TestInterface` 간에 `Module` 및 `End Module` 문의 한 다음 ENTER 키입니다. **코드 편집기** 들여쓰기는 `Interface` 키워드를 추가 하 고는 `End Interface` 코드 블록을 형성 하는 문입니다.  
  
5.  속성, 메서드 및 인터페이스에 대 한 이벤트 사이 다음 코드를 배치 하 여 정의 된 `Interface` 및 `End Interface` 문:  
  
     [!code-vb[VbVbalrOOP #&98;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_1.vb)]  
  
## <a name="implementation"></a>구현  
 인터페이스 멤버를 선언 하는 데 구문은 다른 클래스 멤버를 선언 하는 데 사용 되는 구문에서 볼 수 있습니다. 이러한 차이 반영 인터페이스 구현 코드를 포함할 수 없습니다.  
  
#### <a name="to-implement-the-interface"></a>인터페이스를 구현 하려면  
  
1.  라는 클래스를 추가 `ImplementationClass` 다음 문을 추가 하 여 `Module1`뒤의 `End Interface` 문의 하기 전에 `End Module` 문의 한 다음 ENTER 키:  
  
     [!code-vb[VbVbalrOOP #&99;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_2.vb)]  
  
     통합된 개발 환경 내에서 작업 하는 경우는 **코드 편집기** 에서 짝 `End Class` ENTER 키를 누르면 문입니다.  
  
2.  다음 코드를 추가 `Implements` 문을 `ImplementationClass`를 구현 하는 인터페이스는 클래스의 이름을:  
  
     [!code-vb[VbVbalrOOP #&100;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_3.vb)]  
  
     클래스 또는 구조를 맨 위에 있는 다른 항목과 별도로 나열 하는 경우는 `Implements` 클래스 또는 구조체는 인터페이스를 구현 하는 문은 나타냅니다.  
  
     통합된 개발 환경 내에서 작업 하는 경우는 **코드 편집기** 구현에 필요한 클래스 멤버 `TestInterface` 때 ENTER 키를 누릅니다 하 고 다음 단계를 건너뛸 수 있습니다.  
  
3.  인터페이스의 모든 멤버를 구현 해야 통합된 개발 환경 내에서 작동 하지 않는 경우 `MyInterface`합니다. 다음 코드를 추가 `ImplementationClass` 구현 하려면 `Event1`, `Method1`, 및 `Prop1`:  
  
     [!code-vb[VbVbalrOOP #&101;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_4.vb)]  
  
     `Implements` 문을 인터페이스 및 인터페이스 멤버 구현 되는 이름을 지정 합니다.  
  
4.  정의 완료 `Prop1` 속성 값을 저장 하는 클래스에는 개인 필드를 추가 하 여:  
  
     [!code-vb[VbVbalrOOP #&102;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_5.vb)]  
  
     값을 반환 된 `pval` 속성에서 get 접근자입니다.  
  
     [!code-vb[VbVbalrOOP #&103;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_6.vb)]  
  
     값을 설정할 `pval` 속성 집합 접근자입니다.  
  
     [!code-vb[VbVbalrOOP #&104;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_7.vb)]  
  
5.  정의 완료 `Method1` 다음 코드를 추가 합니다.  
  
     [!code-vb[VbVbalrOOP #&105;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_8.vb)]  
  
#### <a name="to-test-the-implementation-of-the-interface"></a>인터페이스의 구현을 테스트 하려면  
  
1.  프로젝트의 시작 폼을 마우스 오른쪽 단추로 클릭는 **솔루션 탐색기**를 클릭 하 고 **코드 보기**합니다. 편집기 시작 폼에 대 한 클래스를 표시합니다. 기본적으로 시작 폼 이라고 `Form1`합니다.  
  
2.  다음 코드를 추가 `testInstance` 필드는 `Form1` 클래스:  
  
     [!code-vb[VbVbalrOOP #&120;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_9.vb)]  
  
     선언 하 여 `testInstance` 으로 `WithEvents`, `Form1` 클래스는 해당 이벤트를 처리할 수 있습니다.  
  
3.  다음 이벤트 처리기를 추가 `Form1` 에 의해 발생 하는 이벤트를 처리 하는 클래스 `testInstance`:  
  
     [!code-vb[VbVbalrOOP #&106;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_10.vb)]  
  
4.  라는 서브루틴 추가 `Test` 에 `Form1` 클래스 구현 클래스를 테스트 하려면:  
  
     [!code-vb[VbVbalrOOP #&107;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_11.vb)]  
  
     `Test` 프로시저 구현 하는 클래스의 인스턴스를 만들고 `MyInterface`, 해당 인스턴스를 할당는 `testInstance` 필드, 속성을 설정 하 고 인터페이스를 통해 메서드를 실행 합니다.  
  
5.  호출 하는 코드를 추가 `Test` 에서 프로시저는 `Form1 Load` 시작 폼의 프로시저:  
  
     [!code-vb[VbVbalrOOP #&108;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_12.vb)]  
  
6.  실행 된 `Test` f5 키를 눌러 프로시저입니다. 메시지 "Prop1으로 설정 된 9" 표시 됩니다. "Method1에 대 한 X 매개 변수는 5입니다"가 표시 되는 메시지 확인을 클릭 합니다. 확인을 클릭 하 고 "이벤트 처리기는 이벤트를 발생 하는 데 사용" 메시지가 표시 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [Implements 문](../../../../visual-basic/language-reference/statements/implements-statement.md)   
 [인터페이스](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)   
 [Interface 문](../../../../visual-basic/language-reference/statements/interface-statement.md)   
 [Event 문](../../../../visual-basic/language-reference/statements/event-statement.md)

