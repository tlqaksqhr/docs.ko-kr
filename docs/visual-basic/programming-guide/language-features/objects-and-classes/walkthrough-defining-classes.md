---
title: "Walkthrough: Defining Classes (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "execution, ending"
  - "objects [Visual Basic], initializing"
  - "Initialize event"
  - "files, closing"
  - "programs, quitting"
  - "code, exiting"
  - "objects [Visual Basic], creating"
  - "program termination"
  - "classes [Visual Basic], walkthroughs"
  - "class modules, walkthroughs"
  - "Terminate event"
  - "execution, stopping"
ms.assetid: 07018828-2d49-4cf5-a44b-19fb15d9efea
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# Walkthrough: Defining Classes (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 연습에서는 클래스를 정의한 다음 해당 클래스에서 개체를 만드는 방법을 보여 줍니다.  새 클래스에 속성 및 메서드를 추가하는 방법과 개체를 초기화하는 방법도 보여 줍니다.  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
### 클래스를 정의하려면  
  
1.  **파일** 메뉴에서 **새 프로젝트**를 클릭하여 프로젝트를 만듭니다.  **새 프로젝트** 대화 상자가 나타납니다.  
  
2.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 프로젝트 템플릿 목록에서 Windows 응용 프로그램을 선택하여 새 프로젝트를 표시합니다.  
  
3.  **프로젝트** 메뉴의 **클래스 추가**를 클릭하여 프로젝트에 새 클래스를 추가합니다.  **새 항목 추가** 대화 상자가 나타납니다.  
  
4.  **클래스** 템플릿을 선택합니다.  
  
5.  새 클래스의 이름을 `UserNameInfo.vb`로 지정한 다음 **추가**를 클릭하여 새 클래스에 대한 코드를 표시합니다.  
  
     [!code-vb[VbVbalrOOP#5](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#5)]  
  
    > [!NOTE]
    >  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] **코드 편집기**에서 새 클래스 이름 다음에 `Class` 키워드를 입력하여 시작 폼에 클래스를 추가할 수 있습니다.  **코드 편집기**에서 작업하면 해당 `End Class` 문이 자동으로 제공됩니다.  
  
6.  `Class` 문과 `End Class` 문 사이에 다음 코드를 추가하여 클래스에 대한 전용 필드를 정의합니다.  
  
     [!code-vb[VbVbalrOOP#7](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#7)]  
  
     필드를 `Private`로 선언하면 해당 필드는 클래스 내에서만 사용될 수 있습니다.  `Public`과 같이 보다 많은 액세스를 제공하는 액세스 한정자를 사용하면 클래스 외부에서 필드를 사용할 수 있도록 할 수 있습니다.  자세한 내용은 [Access Levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)을 참조하십시오.  
  
7.  다음 코드를 추가하여 클래스의 속성을 정의합니다.  
  
     [!code-vb[VbVbalrOOP#8](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#8)]  
  
8.  다음 코드를 추가하여 클래스의 메서드를 정의합니다.  
  
     [!code-vb[VbVbalrOOP#9](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#9)]  
  
9. `Sub New` 프로시저를 추가하여 새 클래스에 대한 매개 변수가 있는 생성자를 정의합니다.  
  
     [!code-vb[VbVbalrOOP#10](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#10)]  
  
     `Sub New` 생성자는 이 클래스를 기반으로 개체가 만들어질 때 자동으로 호출됩니다.  이 생성자는 사용자 이름을 사용하는 필드의 값을 설정합니다.  
  
### 클래스를 테스트할 단추를 만들려면  
  
1.  **솔루션 탐색기**에서 시작 폼 이름을 마우스 오른쪽 단추로 클릭하고 **디자이너 보기**를 클릭하여 디자인 모드로 변경합니다.  기본적으로 Windows 응용 프로그램 프로젝트용 시작 폼의 이름은 Form1.vb입니다.  기본 폼이 나타납니다.  
  
2.  기본 폼에 단추를 추가하고 두 번 클릭하여 `Button1_Click` 이벤트 처리기의 코드를 표시합니다.  다음 코드를 추가하여 테스트 프로시저를 호출합니다.  
  
     [!code-vb[VbVbalrOOP#12](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#12)]  
  
### 응용 프로그램을 실행하려면  
  
1.  F5 키를 눌러 응용 프로그램을 실행하면  폼의 단추를 클릭하여 테스트 프로시저를 호출합니다.  프로시저에서 개체의 `Capitalize` 메서드를 호출했기 때문에 원본 `UserName`이 "MOORE, BOBBY"라는 메시지가 표시됩니다.  
  
2.  **확인**을 클릭하여 메시지 상자를 닫습니다.  `Button1 Click` 프로시저는 `UserName` 속성 값을 변경하고 `UserName`의 새 값이 "Worden, Joe"라는 메시지를 표시합니다.  
  
## 참고 항목  
 [개체 지향 프로그래밍](../Topic/Object-Oriented%20Programming%20\(C%23%20and%20Visual%20Basic\).md)   
 [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)