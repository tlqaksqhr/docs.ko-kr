---
title: "Walkthrough: Creating and Implementing Interfaces (Visual Basic) | Microsoft Docs"
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
  - "interfaces, walkthroughs"
  - "interfaces, testing"
  - "interface implementation, walkthrough"
  - "interfaces, creating"
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Walkthrough: Creating and Implementing Interfaces (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

인터페이스는 속성, 메서드 및 이벤트의 특징을 설명하지만 구현에 대한 세부적인 사항은 구조체나 클래스에서 처리합니다.  
  
 이 연습에서는 인터페이스를 선언 및 구현하는 방법을 보여 줍니다.  
  
> [!NOTE]
>  이 연습에서는 사용자 인터페이스를 만드는 방법에 대 한 정보를 제공 하지 않습니다.  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
### 인터페이스를 정의하려면  
  
1.  새 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] Windows 응용 프로그램 프로젝트를 엽니다.  
  
2.  **프로젝트** 메뉴에서 **모듈 추가**를 클릭하여 새 모듈을 프로젝트에 추가합니다.  
  
3.  새 모듈의 이름을 `Module1.vb`로 지정하고 **추가**를 클릭합니다.  그러면 새 모듈에 대한 코드가 표시됩니다.  
  
4.  `Module` 및 `End Module` 문 사이에 `Interface TestInterface`를 입력한 다음 Enter 키를 눌러 `Module1` 내에 `TestInterface`라는 인터페이스를 정의합니다.  **코드 편집기**가 `Interface` 키워드를 들여 쓰고 `End Interface` 문을 추가하여 코드 블록을 구성합니다.  
  
5.  `Interface` 및 `End Interface` 문 사이에 다음 코드를 삽입하여 인터페이스에 대한 속성, 메서드 및 이벤트를 정의합니다.  
  
     [!code-vb[VbVbalrOOP#98](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#98)]  
  
## 구현  
 여기서 인터페이스 멤버를 선언하는 데 사용된 구문은 클래스 멤버를 선언하는 데 사용되는 구문과 다릅니다.  이러한 차이는 인터페이스는 구현 코드를 포함할 수 없기 때문에 생기는 것입니다.  
  
#### 인터페이스를 구현하려면  
  
1.  `End Interface` 및 `End Module` 문 사이에 다음 문을 추가한 다음 Enter 키를 눌러 이름이 `ImplementationClass`인 클래스를 `Module1`에 추가합니다.  
  
     [!code-vb[VbVbalrOOP#99](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#99)]  
  
     통합 개발 환경에서 작업하는 경우, Enter 키를 누르면 **코드 편집기**에서 짝이 되는 `End Class` 문이 삽입됩니다.  
  
2.  다음 `Implements` 문을 `ImplementationClass`에 추가하여 해당 클래스가 구현하는 인터페이스의 이름을 지정합니다.  
  
     [!code-vb[VbVbalrOOP#100](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#100)]  
  
     `Implements` 문이 클래스나 구조체의 맨 위에 다른 항목들과 별도로 나열되면 해당 클래스나 구조체가 인터페이스를 구현한다는 것을 뜻합니다.  
  
     통합 개발 환경에서 작업하는 경우, Enter 키를 누르면 `TestInterface`에 필요한 클래스 멤버가 **코드 편집기**에서 구현되므로 다음 단계로 건너뛸 수 있습니다.  
  
3.  통합 개발 환경에서 작업하는 경우가 아니라면 `MyInterface` 인터페이스의 모든 멤버를 직접 구현해야 합니다.  `ImplementationClass`에 다음 코드를 추가하여 `Event1`, `Method1` 및 `Prop1`을 구현합니다.  
  
     [!code-vb[VbVbalrOOP#101](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#101)]  
  
     `Implements` 문에는 인터페이스 이름과 구현될 인터페이스 멤버의 이름이 지정됩니다.  
  
4.  속성 값이 저장된 클래스에 전용 필드를 추가하여 `Prop1`의 정의를 완료합니다.  
  
     [!code-vb[VbVbalrOOP#102](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#102)]  
  
     property get 접근자로부터 `pval`의 값을 반환합니다.  
  
     [!code-vb[VbVbalrOOP#103](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#103)]  
  
     property set 접근자에서 `pval`의 값을 설정합니다.  
  
     [!code-vb[VbVbalrOOP#104](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#104)]  
  
5.  다음 코드를 추가하여 `Method1`의 정의를 완료합니다.  
  
     [!code-vb[VbVbalrOOP#105](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#105)]  
  
#### 인터페이스의 구현을 테스트하려면  
  
1.  **솔루션 탐색기**에서 사용자 프로젝트에 대한 시작 폼을 마우스 오른쪽 단추로 클릭한 다음 **코드 보기**를 클릭합니다.  편집기가 시작 폼에 대한 클래스를 표시합니다.  기본적으로 시작 폼의 이름은 `Form1`입니다.  
  
2.  `Form1` 클래스에 다음 `testInstance` 필드를 추가합니다.  
  
     [!code-vb[VbVbalrOOP#120](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#120)]  
  
     `testInstance`를 `WithEvents`로 선언하면 `Form1` 클래스에서 해당 이벤트를 처리할 수 있습니다.  
  
3.  다음 이벤트 처리기를 `Form1` 클래스에 추가하여 `testInstance`로 인해 발생하는 이벤트를 처리합니다.  
  
     [!code-vb[VbVbalrOOP#106](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#106)]  
  
4.  `Test`라는 서브루틴을 `Form1` 클래스에 추가하여 구현 클래스를 테스트합니다.  
  
     [!code-vb[VbVbalrOOP#107](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#107)]  
  
     `Test` 프로시저는 `MyInterface`를 구현하는 클래스의 인스턴스를 만들고, 이 인스턴스를 `testInstance` 필드에 할당하고, 속성을 설정하고, 인터페이스를 통해 메서드를 실행합니다.  
  
5.  시작 폼의 `Form1 Load` 프로시저에서 `Test` 프로시저를 호출하는 코드를 추가합니다.  
  
     [!code-vb[VbVbalrOOP#108](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#108)]  
  
6.  F5 키를 눌러 `Test` 프로시저를 실행합니다.  메시지 "Prop1 was set to 9"이 표시됩니다.  확인을 클릭하면 메시지 "The X parameter for Method1 is 5"가 표시되고,  다시 확인을 클릭하면 "The event handler caught the event" 메시지가 표시됩니다.  
  
## 참고 항목  
 [Implements Statement](../../../../visual-basic/language-reference/statements/implements-statement.md)   
 [Interfaces](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)   
 [Interface Statement](../../../../visual-basic/language-reference/statements/interface-statement.md)   
 [Event Statement](../../../../visual-basic/language-reference/statements/event-statement.md)