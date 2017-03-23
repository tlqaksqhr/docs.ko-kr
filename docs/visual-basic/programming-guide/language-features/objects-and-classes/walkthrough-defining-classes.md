---
title: "클래스 정의 (Visual Basic) | Microsoft 문서"
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
- execution, ending
- objects [Visual Basic], initializing
- Initialize event
- files, closing
- programs, quitting
- code, exiting
- objects [Visual Basic], creating
- program termination
- classes [Visual Basic], walkthroughs
- class modules, walkthroughs
- Terminate event
- execution, stopping
ms.assetid: 07018828-2d49-4cf5-a44b-19fb15d9efea
caps.latest.revision: 21
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
ms.openlocfilehash: aeaa5c2bb85c1a642da15c6a29546cf065380e27
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-defining-classes-visual-basic"></a>연습: 클래스 정의(Visual Basic)
이 연습에서는 다음 개체를 만드는 데 사용할 수 있는 클래스를 정의 하는 방법을 보여 줍니다. 또한 새 클래스에 속성 및 메서드를 추가 하는 방법을 보여 주고 개체를 초기화 하는 방법을 보여 줍니다.  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-define-a-class"></a>클래스를 정의 하려면  
  
1.  클릭 하 여 프로젝트를 만드는 **새 프로젝트** 에 **파일** 메뉴. **새 프로젝트** 대화 상자가 나타납니다.  
  
2.  Windows 응용 프로그램의 목록에서 선택 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 프로젝트 새 프로젝트를 표시 하는 템플릿이 포함 되어 있습니다.  
  
3.  새 클래스를 클릭 하 여 프로젝트에 추가 **클래스 추가** 에 **프로젝트** 메뉴. **새 항목 추가** 대화 상자가 나타납니다.  
  
4.  선택 된 **클래스** 템플릿.  
  
5.  새 클래스 이름을 `UserNameInfo.vb`를 클릭 하 고 **추가** 새 클래스에 대 한 코드를 표시 합니다.  
  
     [!code-vb[VbVbalrOOP #&5;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_1.vb)]  
  
    > [!NOTE]
    >  사용할 수는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] **코드 편집기** 시작 폼에 입력 하 여 클래스를 추가 하는 `Class` 키워드 새 클래스의 이름이 차례로 나옵니다. **코드 편집기** 해당 제공 `End Class` 문이 있습니다.  
  
6.  사이 다음 코드를 추가 하 여 클래스에 대 한 전용 필드 정의 `Class` 및 `End Class` 문:  
  
     [!code-vb[VbVbalrOOP #&7;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_2.vb)]  
  
     로 필드를 선언 `Private` 클래스 내 에서만 사용할 수 있습니다. 가능 필드는 클래스 외부에서 사용할 수와 같은 액세스 한정자를 사용 하 여 `Public` 동일한 액세스를 제공 하는 합니다. 자세한 내용은 참조 [Visual Basic의 액세스 수준을](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.  
  
7.  다음 코드를 추가 하 여 클래스에 대 한 속성을 정의 합니다.  
  
     [!code-vb[VbVbalrOOP #&8;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_3.vb)]  
  
8.  다음 코드를 추가 하 여 클래스에 대 한 메서드를 정의 합니다.  
  
     [!code-vb[VbVbalrOOP #&9;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_4.vb)]  
  
9. 프로시저를 추가 하 여 새 클래스에 대 한 매개 변수가 있는 생성자를 정의 `Sub New`:  
  
     [!code-vb[VbVbalrOOP #&10;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_5.vb)]  
  
     `Sub New` 생성자는이 클래스를 기반으로 하는 개체를 만들 때 자동으로 호출 됩니다. 이 생성자는 사용자 이름을 사용 하는 필드의 값을 설정 합니다.  
  
### <a name="to-create-a-button-to-test-the-class"></a>클래스를 테스트 하려면 단추를 만들려면  
  
1.  시작 폼에서 해당 이름을 마우스 오른쪽 단추로 클릭 하 여 디자인 모드로 변경 **솔루션 탐색기** 클릭 한 다음 **뷰 디자이너**합니다. 기본적으로 Windows 응용 프로그램 프로젝트에 대 한 시작 폼 Form1.vb 이라고 합니다. 기본 폼이 나타납니다.  
  
2.  기본 폼에 단추를 추가 하 고 두 번 클릭 하 여 코드를 표시 하는 `Button1_Click` 이벤트 처리기입니다. 테스트 프로시저를 호출 하려면 다음 코드를 추가 합니다.  
  
     [!code-vb[VbVbalrOOP #&12;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_6.vb)]  
  
### <a name="to-run-your-application"></a>응용 프로그램을 실행하려면  
  
1.  F5 키를 눌러 응용 프로그램을 실행 합니다. 테스트 프로시저를 호출 하려면 폼의 단추를 클릭 합니다. 원래 했다는 메시지가 표시 `UserName` 프로시저가 호출 되므로 "MOORE, BOBBY"는 `Capitalize` 개체의 메서드.  
  
2.  클릭 **확인** 메시지 상자를 닫습니다. `Button1 Click` 의 값을 변경 하는 절차는 `UserName` 속성의 새 값이 했다는 메시지가 표시 됩니다 `UserName` "Worden, Joe"는 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [개체 지향 프로그래밍](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)   
 [개체 및 클래스](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)

