---
title: 선언된 요소 참조(Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declared elements [Visual Basic]
- references [Visual Basic], declared elements
- qualified names [Visual Basic]
ms.assetid: d6301709-f4cc-4b7a-b8ba-80898f14ab46
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 86d25d42688cffbf4076c4fb42eccc3b917d1dc1
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="references-to-declared-elements-visual-basic"></a>선언된 요소 참조(Visual Basic)
코드에서 선언 된 요소를 참조 하는 경우 Visual Basic 컴파일러에서 참조를 해당 이름의 적절 한 선언에 있는 이름과 일치 합니다. 이름이 같은 둘 이상의 요소가 선언 된 경우 요소를 참조할 수는 제어할 수 있습니다 *조건에 맞는* 이름입니다.  
  
 컴파일러는 이름 선언에 대 한 이름 참조를 일치 시 키 려 고 *가장 좁은 범위*합니다. 즉 못하여 참조가 코드로 시작 하 고 다음 요소가 포함 된 수준을 통해 바깥쪽으로 작동 합니다.  
  
 다음 예제에서는 이름이 같은 두 변수에 대 한 참조를 보여 줍니다. 이 예제에서는 두 개의 변수 선언, 각각의 명명 `totalCount`, 서로 다른 수준의 모듈의 범위 내에서 `container`합니다. 때 프로시저 `showCount` 표시 `totalCount` Visual Basic 컴파일러 한정자 없이 로컬 선언 내부 즉 가장 좁은 범위에서 선언에 대 한 참조를 확인 `showCount`합니다. 모듈인 `totalCount` 포함 하는 모듈와 `container`, 컴파일러는 광범위 한 범위에서 선언에 대 한 참조를 확인 합니다.  
  
```vb  
' Assume these two modules are both in the same assembly.  
Module container  
    Public totalCount As Integer = 1  
    Public Sub showCount()  
        Dim totalCount As Integer = 6000  
        ' The following statement displays the local totalCount (6000).  
        MsgBox("Unqualified totalCount is " & CStr(totalCount))  
        ' The following statement displays the module's totalCount (1).  
        MsgBox("container.totalCount is " & CStr(container.totalCount))  
    End Sub  
End Module  
Module callingModule  
    Public Sub displayCount()  
        container.showCount()  
        ' The following statement displays the containing module's totalCount (1).  
        MsgBox("container.totalCount is " & CStr(container.totalCount))  
    End Sub  
End Module  
```  
  
## <a name="qualifying-an-element-name"></a>요소 이름 한정  
 이 검색 프로세스를 무시 하 고 수행 해야 더 넓은 범위에 선언 된 이름을 지정 하려는 경우 *한정* 포함 하는 요소로 더 넓은 범위의 이름입니다. 경우에 따라 포함 하는 요소를 정해야 할 수 있습니다.  
  
 하면 이름이 한정 앞에 대상 요소가 정의 되어 식별 하는 정보가 소스 문의 합니다. 이 정보 라고는 *한정 문자열*합니다. 하나를 포함 하거나 더 많은 네임 스페이스 및 모듈의 경우, 클래스 또는 구조체.  
  
 한정 문자열 모듈, 클래스 또는 대상 요소가 포함 된 구조체에 명확 하 게 지정 해야 합니다. 컨테이너는 다시 다른 포함 하는 요소, 일반적으로 네임 스페이스에에서 위치할 수 있습니다. 한정 문자열에 여러 포함 된 요소를 포함 해야 합니다.  
  
#### <a name="to-access-a-declared-element-by-qualifying-its-name"></a>해당 이름을 정규화 하 여 선언 된 요소에 액세스 하려면  
  
1.  요소가 정의 된 위치를 결정 합니다. 여기에 네임 스페이스 또는 네임 스페이스의 계층 구조가 포함 될 수 있습니다. 가장 낮은 수준의 네임 스페이스 내에서 요소는 모듈, 클래스 또는 구조체에 포함 되어야 합니다.  
  
    ```vb  
    ' Assume the following hierarchy exists outside your code.  
    Namespace outerSpace  
        Namespace innerSpace  
            Module holdsTotals  
                Public Structure totals  
                    Public thisTotal As Integer  
                    Public Shared grandTotal As Long  
                End Structure  
            End Module  
        End Namespace  
    End Namespace  
    ```  
  
2.  대상 요소의 위치에 따라 한정 경로 확인 합니다. 최상위 네임 스페이스를 가진 시작한 가장 낮은 수준의 네임 스페이스에 계속 모듈, 클래스 또는 구조체를 포함 하는 대상 요소 끝나야 합니다. 경로 있는 각 요소에는 뒤에 오는 요소가 있어야 합니다.  
  
     `outerSpace` → `innerSpace` → `holdsTotals` → `totals`  
  
3.  대상 요소에 대 한 한정 문자열을 준비 합니다. 에 마침표 (`.`) 경로 있는 모든 요소 뒤 합니다. 응용 프로그램에서 한정 문자열의 모든 요소에 액세스할 수 있어야 합니다.  
  
    ```vb  
    outerSpace.innerSpace.holdsTotals.totals.  
    ```  
  
4.  식 또는 대입문이 일반적인 방법으로 참조 하는 대상 요소를 작성 합니다.  
  
    ```vb  
    grandTotal = 9000  
    ```  
  
5.  대상 요소 이름을 한정 문자열 앞에 둡니다. 이름은 마침표 다음에 나와야 (`.`) 모듈, 클래스 또는 구조는 요소가 포함 된 다음에 오는 합니다.  
  
    ```vb  
    ' Assume the following module is part of your code.  
    Module accessGrandTotal  
        Public Sub setGrandTotal()  
            outerSpace.innerSpace.holdsTotals.totals.grandTotal = 9000  
        End Sub  
    End Module  
    ```  
  
6.  컴파일러를 대상 요소 참조 일치 시킬 수는 명확 하 고 명확한 선언의 찾을 한정 문자열을 사용 합니다.  
  
 또한 응용 프로그램에 동일한 이름을 가진 둘 이상의 프로그래밍 요소에 액세스 하는 경우 이름 참조를 정규화 해야 합니다. 예를 들어는 <xref:System.Windows.Forms> 및 <xref:System.Web.UI.WebControls> 두 네임 스페이스를 포함 한 `Label` 클래스 (<xref:System.Windows.Forms.Label?displayProperty=nameWithType> 및 <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>). 응용 프로그램 모두를 사용 하거나 자체 정의 하는 경우 `Label` 클래스를 서로 다른 구별 해야 `Label` 개체입니다. 변수 선언에 네임 스페이스 또는 가져오기 별칭을 포함 합니다. 다음 예제에서는 가져오기 별칭을 사용 합니다.  
  
```vb  
' The following statement must precede all your declarations.  
Imports win = System.Windows.Forms, web = System.Web.UI.WebControls  
' The following statement references the Windows.Forms.Label class.  
Dim winLabel As New win.Label()  
```  
  
## <a name="members-of-other-containing-elements"></a>포함 된 요소의 다른 멤버  
 다른 클래스 또는 구조체의 공유 되지 않는 멤버를 사용 하면 먼저 변수 또는 구조체 또는 클래스의 인스턴스를 가리키는 식을 사용 하 여 멤버 이름을 정규화 해야 합니다. 다음 예에서 `demoClass` 라는 클래스의 인스턴스가 `class1`합니다.  
  
```vb  
Dim demoClass As class1 = New class1()  
demoClass.someSub[(argumentlist)]  
```  
  
 클래스 이름 자체는 되지 않은 멤버를 한 정하는 데 사용할 수 없습니다 [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)합니다. 개체 변수에 인스턴스를 먼저 만들어야 (이 경우 `demoClass`) 변수 이름으로 참조 해야 합니다.  
  
 클래스 또는 구조체에는 `Shared` 멤버 클래스 또는 구조체 이름 또는 변수 또는 인스턴스를 가리키는 식과 해당 멤버를 한정할 수 있습니다.  
  
 모듈에는 별도 모든 인스턴스가 하 고 모든 해당 멤버는 `Shared` 기본적으로 합니다. 따라서 모듈 이름으로 모듈 멤버를 한정할 수 있습니다.  
  
 다음 예제에서는 모듈 멤버 프로시저에 대 한 정규화 된 참조를 보여 줍니다. 이 예제에서는 두 개의 선언 `Sub` 이라는 프로시저 `perform`, 서로 다른 모듈에 프로젝트입니다. 각 모듈 자체 내에서 한정 하지 않고 지정할 수 있지만 다른 곳에서 참조 하는 경우 한정 되어야 합니다. 마지막에 참조 `module3` 사용할 수 없는 `perform`, 컴파일러에서 해당 참조를 확인할 수 없습니다.  
  
```vb  
' Assume these three modules are all in the same assembly.  
Module module1  
    Public Sub perform()  
        MsgBox("module1.perform() now returning")  
    End Sub  
End Module  
Module module2  
    Public Sub perform()  
        MsgBox("module2.perform() now returning")  
    End Sub  
    Public Sub doSomething()  
        ' The following statement calls perform in module2, the active module.  
        perform()  
        ' The following statement calls perform in module1.  
        module1.perform()  
    End Sub  
End Module  
Module module3  
    Public Sub callPerform()  
        ' The following statement calls perform in module1.  
        module1.perform()  
        ' The following statement makes an unresolvable name reference  
        ' and therefore generates a COMPILER ERROR.  
        perform() ' INVALID statement  
    End Sub  
End Module  
```  
  
## <a name="references-to-projects"></a>프로젝트에 대 한 참조  
 사용 하도록 [공용](../../../../visual-basic/language-reference/modifiers/public.md) 다른 프로젝트에 정의 된 요소를 먼저 설정 해야는 *참조* 해당 프로젝트의 어셈블리 또는 형식 라이브러리에 있습니다. 참조를 설정 하려면 클릭 **참조 추가** 에 **프로젝트** 메뉴를 사용 하거나 사용 하 여는 [/reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) 명령줄 컴파일러 옵션입니다.  
  
 예를 들어의 XML 개체 모델을 사용할 수 있습니다는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]합니다. 대 한 참조를 설정 하는 경우는 <xref:System.Xml> 네임 스페이스를 선언 하 고 사용할 수의 해당 클래스와 같은 <xref:System.Xml.XmlDocument>합니다. 다음 예제에서는 <xref:System.Xml.XmlDocument>합니다.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As System.Xml.XmlDocument  
```  
  
## <a name="importing-containing-elements"></a>요소를 포함 하는 가져오기  
 사용할 수는 [Imports 문 (.NET Namespace 및 형식)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) 를 *가져올* 모듈이 나 사용 하려는 클래스를 포함 하는 네임 스페이스입니다. 이 이름을 정규화 하지 않고 가져온된 네임 스페이스에 정의 된 요소를 참조할 수 있습니다. 다음 예제에서는 이전 예제를 가져오려면 다시 작성 한는 <xref:System.Xml> 네임 스페이스입니다.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As XmlDocument  
```  
  
 또한는 `Imports` 문에서 정의할 수 있습니다는 *가져오기 별칭* 각 가져온된 네임 스페이스에 대 한 합니다. 이 소스 코드를 더 짧게 만들어 더 쉽게 읽을 수 해질 수 있습니다. 다음 예제에서는 다시 사용 하도록 이전 예제의 작성 `xD` 별칭으로는 <xref:System.Xml> 네임 스페이스입니다.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports xD = System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As xD.XmlDocument  
```  
  
 `Imports` 문으로 하지 요소 만들 다른 프로젝트에서 응용 프로그램에 사용할 수 있습니다. 즉, 참조 설정의 현재 위치를 사용 하지 않습니다. 네임 스페이스를 방금 가져오면 해당 네임 스페이스에 정의 된 이름을 정규화 하는 요구 사항을 제거 합니다.  
  
 사용할 수도 있습니다는 `Imports` 모듈, 클래스, 구조체 및 열거형을 가져올 계정. 다음 한정자 없이 가져온 요소의 멤버를 사용할 수 있습니다. 그러나 비공유 멤버의 클래스와 구조체는 변수 또는 구조체 또는 클래스의 인스턴스를 가리키는 식으로 항상 정규화 해야 합니다.  
  
## <a name="naming-guidelines"></a>명명 지침  
 동일한 이름의 두 개 이상의 프로그래밍 요소를 정의 하는 경우는 *이름 모호성* 컴파일러에서이 이름에 대 한 참조를 확인 하려고 할 때 발생할 수 있습니다. 범위를 하나 정의 두 번 이상 또는 정의가 없는 범위에 포함 된 경우 참조를 확인할 수 없습니다. 예를 들어이 도움말 페이지에 "정규화 된 참조 예"를 참조 합니다.  
  
 모든 요소에 고유한 이름을 지정 하 여 이름 모호성을 방지할 수 있습니다. 다음 네임 스페이스, 모듈 또는 클래스를 사용 하 여 이름을 한정 하지 않고도 모든 요소에 대 한 참조를 만들 수 있습니다. 실수로 잘못 된 요소를 참조 하는 가능성 줄일 수도 있습니다.  
  
## <a name="shadowing"></a>섀도잉  
 두 개의 프로그래밍 요소가 동일한 이름을 공유 하는 경우 그 중 하나가 숨길 수, 또는 *그림자*, 다른 하나 있습니다. 숨겨진된는 요소는 참조;에 사용할 수 없습니다. 대신, 섀도잉 된 요소 이름을 사용 하는 코드를 Visual Basic 컴파일러 숨기는 요소 확인 합니다. 보다 자세한 내용 및 예제를 참조 하십시오. [Visual Basic의 숨김 기능](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [선언 요소 이름](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [선언 요소의 특징](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [프로젝트 및 솔루션 속성 관리](/visualstudio/ide/managing-project-and-solution-properties)  
 [변수](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [Imports 문(.NET 네임스페이스 및 형식)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [New 연산자](../../../../visual-basic/language-reference/operators/new-operator.md)  
 [공용](../../../../visual-basic/language-reference/modifiers/public.md)
