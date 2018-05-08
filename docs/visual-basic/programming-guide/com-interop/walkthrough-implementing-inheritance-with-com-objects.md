---
title: '연습: COM 개체를 사용한 상속 구현(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], COM reusability
- base classes [Visual Basic], COM reusability
- inheritance [Visual Basic], walkthroughs
- derived classes [Visual Basic], COM reusability
ms.assetid: f8e7263a-de13-48d1-b67c-ca1adf3544d9
ms.openlocfilehash: a1c1b7c247d3277c6614a4774395650c4c069c2f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-implementing-inheritance-with-com-objects-visual-basic"></a>연습: COM 개체를 사용한 상속 구현(Visual Basic)
Visual Basic 클래스를 파생 시켜 `Public` 도 이전 버전의 Visual Basic에 생성 된 COM 개체의 클래스. 속성 및 COM 개체에서 상속 된 클래스의 메서드를 재정의 하거나 속성와 마찬가지로 오버 로드 및 다른 기본 클래스의 메서드를 재정의 하거나 오버 로드 합니다. COM 개체에서 상속 다시 컴파일하지 않을 기존 클래스 라이브러리에 있는 경우에 유용 합니다.  
  
 다음 절차에는 클래스를 포함 하는 COM 개체를 만들려면 Visual Basic 6.0을 사용 하 여 다음 기본 클래스로 사용 하 여 하는 방법을 보여 줍니다.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-build-the-com-object-that-is-used-in-this-walkthrough"></a>이 연습에 사용 되는 COM 개체를 만들려면  
  
1.  Visual Basic 6.0에서 새로운 ActiveX DLL 프로젝트를 엽니다. 라는 프로젝트가 `Project1` 만들어집니다. 여기에 라는 클래스가 `Class1`합니다.  
  
2.  에 **프로젝트 탐색기**를 마우스 오른쪽 단추로 클릭 **Project1**, 클릭 하 고 **Project1 속성**합니다. **프로젝트 속성** 대화 상자가 표시 됩니다.  
  
3.  에 **일반** 탭은 **프로젝트 속성** 대화 상자에서 프로젝트 이름을 입력 하 여 변경 `ComObject1` 에 **프로젝트 이름을** 필드입니다.  
  
4.  에 **프로젝트 탐색기**를 마우스 오른쪽 단추로 클릭 `Class1`, 클릭 하 고 **속성**합니다. **속성** 클래스 창에 표시 됩니다.  
  
5.  변경 된 `Name` 속성을 `MathFunctions`합니다.  
  
6.  에 **프로젝트 탐색기**를 마우스 오른쪽 단추로 클릭 `MathFunctions`, 클릭 하 고 **코드 보기**합니다. **코드 편집기** 표시 됩니다.  
  
7.  속성 값을 보유 하는 로컬 변수를 추가 합니다.  
  
    ```  
    ' Local variable to hold property value  
    Private mvarProp1 As Integer  
    ```  
  
8.  속성 추가 `Let` 속성과 `Get` 속성 프로시저:  
  
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
  
9. 함수를 추가 합니다.  
  
    ```  
    Function AddNumbers(   
       ByVal SomeNumber As Integer,   
       ByVal AnotherNumber As Integer) As Integer  
  
       AddNumbers = SomeNumber + AnotherNumber  
    End Function  
    ```  
  
10. 만들기 및 COM 개체를 클릭 하 여 등록 **확인 ComObject1.dll** 에 **파일** 메뉴.  
  
    > [!NOTE]
    >  클래스를 COM 개체로 Visual Basic을 사용 하 여 만든를 노출할 수도 있지만 실제 COM 개체 아니며이 연습에서 사용할 수 없습니다. 자세한 내용은 참조 [.NET Framework 응용 프로그램의 COM 상호 운용성](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)합니다.  
  
## <a name="interop-assemblies"></a>Interop 어셈블리  
 다음 절차에서는 관리 되지 않는 코드 (예: COM 개체) 및 Visual Studio를 사용 하 여 관리 코드 간 브리지 역할을 하는 interop 어셈블리를 만들게 됩니다. Interop 어셈블리를 Visual Basic 만듭니다이 COM 개체와 같은 작업의 세부 사항을 처리 *interop 마샬링*, 프로세스 매개 변수 및 반환 값에 해당 하는 데이터를 이동 하는 동안 형식 및 COM 개체입니다. Visual Basic 응용 프로그램에 대 한 참조는 interop 어셈블리를 실제 COM 개체를 가리킵니다.  
  
#### <a name="to-use-a-com-object-with-visual-basic-2005-and-later-versions"></a>Visual Basic 2005 및 이후 버전으로 COM 개체를 사용 하려면  
  
1.  새 Visual Basic Windows 응용 프로그램 프로젝트를 엽니다.  
  
2.  **프로젝트** 메뉴에서 **참조 추가**를 클릭합니다.  
  
     **참조 추가** 대화 상자가 표시됩니다.  
  
3.  에 **COM** 탭을 두 번 클릭 `ComObject1` 에 **구성 요소 이름** 나열 하 고 클릭 **확인**합니다.  
  
4.  **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.  
  
     **새 항목 추가** 대화 상자가 표시됩니다.  
  
5.  에 **템플릿** 창에서 클릭 **클래스**합니다.  
  
     기본 파일 이름은 `Class1.vb`에 표시는 **이름** 필드입니다. 이 필드를 MathClass.vb으로 클릭 변경 **추가**합니다. 라는 클래스를 만들고이 `MathClass`, 해당 코드가 표시 됩니다.  
  
6.  맨 위에 다음 코드를 추가 `MathClass` COM 클래스에서 상속 하도록 합니다.  
  
     [!code-vb[VbVbalrInterop#31](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_1.vb)]  
  
7.  다음 코드를 추가 하 여 기본 클래스의 공용 메서드를 오버 로드 `MathClass`:  
  
     [!code-vb[VbVbalrInterop#32](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_2.vb)]  
  
8.  다음 코드를 추가 하 여 상속 된 클래스를 확장 `MathClass`:  
  
     [!code-vb[VbVbalrInterop#33](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_3.vb)]  
  
 새 클래스는 COM 개체에서 기본 클래스의 속성을 상속 하 고 메서드를 오버 로드와 클래스를 확장 하는 새 메서드를 정의 합니다.  
  
#### <a name="to-test-the-inherited-class"></a>상속 된 클래스를 테스트 하려면  
  
1.  시작 폼에 단추를 추가 하 고 해당 코드를 보려면 두 번 클릭 합니다.  
  
2.  단추의 `Click` 이벤트 처리기 프로시저의 인스턴스를 만들려면 다음 코드를 추가 `MathClass` 오버 로드 된 메서드를 호출 합니다.  
  
     [!code-vb[VbVbalrInterop#34](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_4.vb)]  
  
3.  F5 키를 눌러 프로젝트를 실행 합니다.  
  
 폼에 단추를 클릭할 때는 `AddNumbers` 메서드를 먼저 호출한 `Short` 데이터 번호를 입력 한 Visual Basic 기본 클래스에서 적절 한 방법을 선택 합니다. 두 번째 호출으로 `AddNumbers` 에서 메서드를 오버 로드로 향하는 `MathClass`합니다. 세 번째 호출은 호출에서 `SubtractNumbers` 메서드를 클래스를 확장 합니다. 기본 클래스에서 속성을 설정 하 고 값이 표시 됩니다.  
  
## <a name="next-steps"></a>다음 단계  
 알 수 있습니다 하는 오버 로드 된 `AddNumbers` 함수를 동일한 데이터 형식이 COM 개체의 기본 클래스에서 상속 하는 방법으로 나타납니다. 인수 및 기본 클래스 메서드의 매개 변수는 Visual Basic 6.0에서 16 비트 정수로 정의 되지만 16 비트 정수 형식으로 노출 되어 때문에 이것이 `Short` 이후 버전의 Visual Basic에서 합니다. 새 함수는 32 비트 정수를 사용 하며 기본 클래스 함수를 오버 로드 합니다.  
  
 COM 개체를 사용할 때 크기 및 데이터 유형의 매개 변수를 확인 하는 있는지 확인 합니다. 예를 들어 Visual Basic 6.0 컬렉션 개체를 인수로 허용 하는 COM 개체를 사용 하는 경우에 이후 버전의 Visual Basic에서 컬렉션을 제공할 수 없습니다.  
  
 속성 및 COM 클래스에서 상속 된 메서드를 재정의할 수 있습니다는 로컬 속성 또는 속성을 대체 하는 메서드 또는 기본 COM 클래스에서 상속 된 메서드를 선언할 수를 의미 합니다. 상속 된 COM 속성을 재정의 하기 위한 규칙은 다른 속성 및 메서드는 다음과 같은 예외가 재정의 대 한 규칙과 유사 합니다.  
  
-   속성이 나 COM 클래스에서 상속 된 메서드를 재정의 하는 경우 다른 상속 된 속성 및 메서드를 재정의 해야 합니다.  
  
-   사용 하는 속성 `ByRef` 매개 변수를 재정의할 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [.NET Framework 응용 프로그램의 COM 상호 운용성](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)  
 [Inherits 문](../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [Short 데이터 형식](../../../visual-basic/language-reference/data-types/short-data-type.md)
