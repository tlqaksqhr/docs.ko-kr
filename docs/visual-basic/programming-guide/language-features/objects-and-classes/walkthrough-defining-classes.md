---
title: 정의 하는 클래스가 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- execution [Visual Basic], ending
- objects [Visual Basic], initializing
- Initialize event [Visual Basic]
- files [Visual Basic], closing
- programs [Visual Basic], quitting
- code, exiting
- objects [Visual Basic], creating
- program termination
- classes [Visual Basic], walkthroughs
- class modules, walkthroughs
- Terminate event [Visual Basic]
- execution [Visual Basic], stopping
ms.assetid: 07018828-2d49-4cf5-a44b-19fb15d9efea
ms.openlocfilehash: aac30a8b0272ae6c141138a91585953237ab8098
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-defining-classes-visual-basic"></a>연습: 클래스 정의(Visual Basic)

이 연습에서는 다음 개체를 만드는 데 사용할 수 있는 클래스를 정의 하는 방법을 보여 줍니다. 또한 새 클래스에 속성 및 메서드를 추가 하는 방법을 보여 주고 개체를 초기화 하는 방법을 보여 줍니다.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-a-class"></a>클래스를 정의 하려면
  
1.  클릭 하 여 프로젝트를 만들 **새 프로젝트** 에 **파일** 메뉴. **새 프로젝트** 대화 상자가 나타납니다.  
  
2.  새 프로젝트를 표시 하는 Visual Basic 프로젝트 템플릿 목록에서 Windows 응용 프로그램을 선택 합니다.  
  
3.  새 클래스를 클릭 하 여 프로젝트에 추가 **클래스 추가** 에 **프로젝트** 메뉴. **새 항목 추가** 대화 상자가 나타납니다.  
  
4.  선택 된 **클래스** 템플릿.  
  
5.  클래스의 새 이름을 `UserNameInfo.vb`, 클릭 하 고 **추가** 새 클래스에 대 한 코드를 표시 합니다.  
  
     [!code-vb[VbVbalrOOP#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#5)]
  
    > [!NOTE]
    >  Visual Basic을 사용할 수 있습니다 **코드 편집기** 시작 폼에 입력 하 여 클래스를 추가 하는 `Class` 키워드 다음 새 클래스의 이름을 입력 합니다. **코드 편집기** 해당 제공 `End Class` 문이 있습니다.  
  
6.  사이 다음 코드를 추가 하 여 클래스에 대 한 전용 필드를 정의 고 `Class` 및 `End Class` 문:  
  
     [!code-vb[VbVbalrOOP#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#7)]
  
     로 필드를 선언 `Private` 의미는 클래스 내 에서만 사용할 수 있습니다. 있습니다 수 필드에서 사용할 수 있도록 클래스 외부와 같은 액세스 한정자를 사용 하 여 `Public` 많은 액세스 권한을 제공 하는 합니다. 자세한 내용은 참조 [액세스 수준을 Visual Basic의](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.  
  
7.  다음 코드를 추가 하 여 클래스에 대 한 속성을 정의 합니다.  
  
     [!code-vb[VbVbalrOOP#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#8)]
  
8.  다음 코드를 추가 하 여 클래스에 대 한 메서드를 정의 합니다.  
  
     [!code-vb[VbVbalrOOP#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#9)]
  
9. 프로시저를 추가 하 여 새 클래스에 대 한 매개 변수가 있는 생성자를 정의 `Sub New`:  
  
     [!code-vb[VbVbalrOOP#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#10)]
  
     `Sub New` 생성자는이 클래스에 기반 하는 개체를 만들 때 자동으로 호출 됩니다. 이 생성자는 사용자 이름을 사용 하는 필드의 값을 설정 합니다.  
  
## <a name="to-create-a-button-to-test-the-class"></a>클래스를 테스트 하려면 단추를 만들려면
  
1.  시작 폼에서 해당 이름을 마우스 오른쪽 단추로 클릭 하 여 디자인 모드로 변경 **솔루션 탐색기** 클릭 한 다음 **뷰 디자이너**합니다. 기본적으로 Windows 응용 프로그램 프로젝트에 대 한 시작 폼 Form1.vb 라고 합니다. 기본 폼이 나타납니다.  
  
2.  기본 폼에 단추를 추가 하 고 두 번 클릭에 대 한 코드를 표시는 `Button1_Click` 이벤트 처리기입니다. 테스트 프로시저를 호출 하려면 다음 코드를 추가 합니다.  
  
     [!code-vb[VbVbalrOOP#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#12)]
  
## <a name="to-run-your-application"></a>응용 프로그램을 실행하려면
  
1.  F5 키를 눌러 응용 프로그램을 실행 합니다. 테스트 프로시저를 호출 하려면 폼에서 단추를 클릭 합니다. 원래 했다는 메시지가 표시 `UserName` "MOORE, BOBBY" 이므로 프로시저 호출의 `Capitalize` 개체의 메서드.  
  
2.  클릭 **확인** 메시지 상자를 닫습니다. `Button1 Click` 의 값을 변경 하는 프로시저는 `UserName` 속성 내용을 입력 하는 메시지의 새 값을 표시 하 고 `UserName` "Worden Joe"는 합니다.  
  
## <a name="see-also"></a>참고자료

[개체 지향 프로그래밍(Visual Basic)](../../concepts/object-oriented-programming.md)  
[개체 및 클래스](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)