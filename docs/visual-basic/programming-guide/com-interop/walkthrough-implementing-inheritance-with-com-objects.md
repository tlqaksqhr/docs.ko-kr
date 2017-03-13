---
title: "Walkthrough: Implementing Inheritance with COM Objects (Visual Basic) | Microsoft Docs"
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
  - "inheritance, COM reusability"
  - "base classes, COM reusability"
  - "inheritance, walkthroughs"
  - "derived classes, COM reusability"
ms.assetid: f8e7263a-de13-48d1-b67c-ca1adf3544d9
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Walkthrough: Implementing Inheritance with COM Objects (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이전 버전의 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서 만든 개체를 포함하여 COM 개체의 `Public` 클래스에서 Visual Basic 클래스를 파생할 수 있습니다.  COM 개체에서 상속된 클래스의 속성 및 메서드는 다른 기본 클래스의 속성 및 메서드를 재정의하거나 오버로드할 때와 같은 방법으로 재정의하거나 오버로드할 수 있습니다.  COM 개체로부터의 상속은 재컴파일하지 않으려는 기존의 클래스 라이브러리가 있는 경우에 유용합니다.  
  
 다음 프로시저에서는 Visual Basic 6.0을 사용하여 클래스가 포함된 COM 개체를 만든 다음 기본 클래스로 사용하는 방법을 보여 줍니다.  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
### 이 연습에 사용된 COM 개체를 만들려면  
  
1.  Visual Basic 6.0에서 새 ActiveX DLL 프로젝트를 엽니다.  이름이 `Project1`인 프로젝트가 만들어집니다.  여기에는 이름이 `Class1`인 클래스가 있습니다.  
  
2.  **프로젝트 탐색기**에서 **Project1**을 마우스 오른쪽 단추로 클릭하고 **Project1 속성**을 클릭합니다.  **프로젝트 속성** 대화 상자가 표시됩니다.  
  
3.  **프로젝트 속성** 대화 상자의 **일반** 탭에서 **프로젝트 이름** 필드에 `ComObject1`을 입력하여 프로젝트 이름을 변경합니다.  
  
4.  **프로젝트 탐색기**에서 `Class1`을 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다.  클래스에 대한 **속성** 창이 표시됩니다.  
  
5.  `Name` 속성을 `MathFunctions`로 변경합니다.  
  
6.  **프로젝트 탐색기**에서 `MathFunctions`를 마우스 오른쪽 단추로 클릭한 다음 **코드 보기**를 클릭합니다.  **코드 편집기**가 표시됩니다.  
  
7.  속성 값을 저장할 지역 변수를 추가합니다.  
  
    ```  
    ' Local variable to hold property value  
    Private mvarProp1 As Integer  
    ```  
  
8.  Property `Let`과 Property `Get` 속성 프로시저를 추가합니다.  
  
    ```  
    Public Property Let Prop1(ByVal vData As Integer)  
       'Used when assigning a value to the property.  
       mvarProp1 = vData  
    End Property  
    Public Property Get Prop1() As Integer  
       'Used when retrieving a property's value.  
       Prop1 = mvarProp1  
    End Property  
    ```  
  
9. 함수를 추가합니다.  
  
    ```  
    Function AddNumbers(   
       ByVal SomeNumber As Integer,   
       ByVal AnotherNumber As Integer) As Integer  
  
       AddNumbers = SomeNumber + AnotherNumber  
    End Function  
    ```  
  
10. **파일** 메뉴에서 **ComObject1.dll 만들기**를 클릭하여 COM 개체를 만들고 등록합니다.  
  
    > [!NOTE]
    >  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서 만든 클래스를 COM 개체로 노출할 수도 있지만 그러한 개체는 실제 COM 개체가 아니므로 이 연습에서 사용할 수 없습니다.  자세한 내용은 [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)을 참조하십시오.  
  
## Interop 어셈블리  
 다음 프로시저에서는 비관리 코드\(예: COM 개체\)와 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)]에서 사용하는 관리 코드 사이의 다리 역할을 하는 interop 어셈블리를 만듭니다.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]이 만드는 interop 어셈블리는 COM 개체에 대한 많은 작업을 처리합니다. 예를 들어 매개 변수 및 반환 값이 COM 개체 간에 이동할 때 해당하는 데이터 형식으로 변환하는 *interop 마샬링* 프로세스가 있습니다.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 응용 프로그램에서 참조는 실제 COM 개체가 아닌 interop 어셈블리를 가리킵니다.  
  
#### Visual Basic 2005 이상 버전에서 COM 개체를 사용하려면  
  
1.  새 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] Windows 응용 프로그램 프로젝트를 엽니다.  
  
2.  **프로젝트** 메뉴에서 **참조 추가**를 클릭합니다.  
  
     **참조 추가** 대화 상자가 표시됩니다.  
  
3.  **COM** 탭의 **구성 요소 이름** 목록에서 `ComObject1`을 두 번 클릭하고 **확인**을 클릭합니다.  
  
4.  **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.  
  
     **새 항목 추가** 대화 상자가 표시됩니다.  
  
5.  **템플릿** 창에서 **클래스**를 클릭합니다.  
  
     기본 파일 이름인 `Class1.vb`가 **이름** 필드에 나타납니다.  이 필드를 MathClass.vb로 변경하고 **추가**를 클릭합니다.  이렇게 하면 `MathClass`라는 클래스가 만들어지고 해당 코드가 표시됩니다.  
  
6.  다음 코드를 `MathClass`의 맨 위에 추가하여 COM 클래스에서 상속합니다.  
  
     [!code-vb[VbVbalrInterop#31](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_1.vb)]  
  
7.  다음 코드를 `MathClass`에 추가하여 기본 클래스의 공용 메서드를 오버로드합니다.  
  
     [!code-vb[VbVbalrInterop#32](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_2.vb)]  
  
8.  다음 코드를 `MathClass`에 추가하여 상속된 클래스를 확장합니다.  
  
     [!code-vb[VbVbalrInterop#33](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_3.vb)]  
  
 새 클래스는 COM 개체에 있는 기본 클래스의 속성을 상속하고 메서드를 오버로드한 다음 새 메서드를 정의하여 클래스를 확장합니다.  
  
#### 상속된 클래스를 테스트하려면  
  
1.  시작 폼에 단추를 하나 추가한 다음 두 번 클릭하여 해당 코드를 표시합니다.  
  
2.  단추의 `Click` 이벤트 처리기 프로시저에서 다음 코드를 추가하여 `MathClass`의 인스턴스를 만들고 오버로드된 메서드를 호출합니다.  
  
     [!code-vb[VbVbalrInterop#34](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_4.vb)]  
  
3.  F5 키를 눌러 프로젝트를 실행합니다.  
  
 폼에서 단추를 클릭하면 먼저 `Short` 데이터 형식 숫자를 사용하여 `AddNumbers` 메서드가 호출되고 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]은 기본 클래스에서 적절한 메서드를 선택합니다.  `AddNumbers`에 대한 두 번째 호출은 `MathClass`에서 오버로드 메서드로 향합니다.  세 번째 호출은 클래스를 확장하는 `SubtractNumbers` 메서드를 호출합니다.  그 결과 기본 클래스의 속성이 설정되고 해당 값이 표시됩니다.  
  
## 다음 단계  
 오버로드된 `AddNumbers` 함수는 COM 개체의 기본 클래스로부터 상속된 메서드와 데이터 형식이 같습니다.  그 이유는 기본 클래스 메서드의 인수 및 매개 변수가 Visual Basic 6.0에서는 16비트 정수로 정의되지만 이후 버전의 Visual Basic에서는 `Short` 형식의 16비트 정수로 노출되기 때문입니다.  새 함수는 32비트 정수를 사용하며 기본 클래스 함수를 오버로드합니다.  
  
 COM 개체로 작업할 때 매개 변수의 크기와 데이터 형식을 확인해야 합니다.  예를 들어, Visual Basic 6.0 컬렉션 개체를 인수로 취하는 COM 개체를 사용하는 경우 이후 버전의 Visual Basic의 컬렉션을 제공할 수 없습니다.  
  
 COM 클래스에서 상속된 속성 및 메서드를 재정의할 수 있습니다. 즉, 기본 COM 클래스에서 상속된 속성 또는 메서드 대신 사용할 지역 속성 또는 메서드를 선언할 수 있습니다.  상속된 COM 속성을 재정의하는 규칙은 다음 경우만 제외하고는 다른 속성 및 메서드를 재정의할 때의 규칙과 유사합니다.  
  
-   COM 클래스에서 상속된 속성 또는 메서드를 재정의할 때는 상속된 다른 모든 속성 및 메서드를 재정의해야 합니다.  
  
-   `ByRef` 매개 변수를 사용하는 속성은 재정의할 수 없습니다.  
  
## 참고 항목  
 [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)   
 [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md)   
 [Short Data Type](../../../visual-basic/language-reference/data-types/short-data-type.md)