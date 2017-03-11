---
title: "선언된 요소 참조(Visual Basic) | Microsoft Docs"
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
  - "선언 요소"
  - "선언 된 요소 참조"
  - "정규화된 이름"
ms.assetid: d6301709-f4cc-4b7a-b8ba-80898f14ab46
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# 선언된 요소 참조(Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

코드에서 선언 된 요소를 참조 하는 경우는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 컴파일러에서 참조를 해당 이름의 적절 한 선언에 있는 이름과 일치 합니다. 둘 이상의 요소가 동일한 이름으로 선언 되는 경우이 참조 하는 요소 제어할 수 있습니다 *조건에 맞는* 이름입니다.  
  
 컴파일러는 이름 선언에 대 한 이름 참조를 찾으려고 시도 *가장 좁은 범위*합니다. 즉, 코드 참조를 만들기 시작 하 고 요소를 포함 하는 연속적인 수준의 바깥쪽으로 진행 합니다.  
  
 다음 예제에서는 이름이 같은 두 변수에 대 한 참조를 보여 줍니다. 이 예제에서는 두 개의 변수를 선언한, 각각의 명명 된 `totalCount`, 서로 다른 수준의 모듈의 범위에서 `container`합니다. 때 프로시저 `showCount` 표시 `totalCount` 한정자 없이 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 내 로컬 선언 즉 가장 좁은 범위에서 선언에 대 한 참조를 확인 하는 컴파일러 `showCount`합니다. 모듈인 `totalCount` 포함 하는 모듈와 `container`, 컴파일러는 더 넓은 범위에서 선언에 대 한 참조를 확인 합니다.  
  
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
 이 검색 프로세스를 재정의 하 고 해야 더 넓은 범위에 선언 된 이름을 지정 하려는 경우 *한정* 더 넓은 범위의 포함 하는 요소 이름입니다. 일부 경우에 포함 하는 요소를 정해야 할 수 있습니다.  
  
 하면 이름이 한정 앞에 대상 요소 정의 된 위치를 식별 하는 정보 소스 문의 합니다. 이 정보 라고는 *한정 문자열*합니다. 하나를 포함 하거나 자세한 네임 스페이스 및 모듈의 경우, 클래스 또는 구조체입니다.  
  
 정규화 문자열 모듈, 클래스 또는 구조체를 포함 하는 대상 요소에 명확 하 게 지정 해야 합니다. 컨테이너 수에 다른 포함 하는 요소의 네임 스페이스에 일반적으로에 있을 수 있습니다. 정규화 문자열에 여러 요소를 포함 하를 포함 해야 합니다.  
  
#### <a name="to-access-a-declared-element-by-qualifying-its-name"></a>해당 이름을 정규화 하 여 선언 된 요소에 액세스 하려면  
  
1.  요소는 정의 된 위치를 결정 합니다. 여기에 네임 스페이스 또는 네임 스페이스의 계층 구조가 포함 될 수 있습니다. 가장 낮은 수준의 네임 스페이스 내에서 요소는 모듈, 클래스 또는 구조체에 포함 되어야 합니다.  
  
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
  
2.  대상 요소의 위치에 따라 한정 경로 확인 합니다. 최상위 수준 네임 스페이스, 가장 낮은 수준의 네임 스페이스를 진행 시작한 모듈, 클래스 또는 구조체를 포함 하는 대상 요소 끝나야 합니다. 경로 있는 각 요소에는 뒤에 오는 요소가 있어야 합니다.  
  
     `outerSpace` → `innerSpace` → `holdsTotals` → `totals`  
  
3.  대상 요소에 대 한 한정 문자열을 준비 합니다. 에 마침표 (`.`) 경로 있는 모든 요소 뒤 합니다. 응용 프로그램에서 한정 문자열의 모든 요소에 액세스할 수 있어야 합니다.  
  
    ```vb  
    outerSpace.innerSpace.holdsTotals.totals.  
    ```  
  
4.  식 또는 일반적인 방법으로 대상 요소를 참조 하는 대입문을 작성 합니다.  
  
    ```vb  
    grandTotal = 9000  
    ```  
  
5.  대상 요소 이름 한정 문자열 앞에 야 합니다. 이름은 마침표 바로 다음에 나와야 (`.`) 모듈, 클래스 또는 요소가 포함 된 구조를 따릅니다.  
  
    ```vb  
    ' Assume the following module is part of your code.  
    Module accessGrandTotal  
        Public Sub setGrandTotal()  
            outerSpace.innerSpace.holdsTotals.totals.grandTotal = 9000  
        End Sub  
    End Module  
    ```  
  
6.  컴파일러를 대상 요소 참조 일치 시킬 수는 명확 하 고 모호 하지 않은 선언의 찾을 한정 문자열을 사용 합니다.  
  
 응용 프로그램에 동일한 이름을 가진 둘 이상의 프로그래밍 요소에 액세스할 경우 이름 참조를 정규화 할 수도 있습니다. 예를 들어는 <xref:System.Windows.Forms> 및 <xref:System.Web.UI.WebControls> 두 네임 스페이스를 포함 한 `Label` 클래스 (<xref:System.Windows.Forms.Label?displayProperty=fullName> 및 <xref:System.Web.UI.WebControls.Label?displayProperty=fullName>). 응용 프로그램 모두를 사용 하거나 자체 정의 하는 경우 `Label` 클래스를 서로 다른 구별 해야 `Label` 개체입니다. 변수 선언에 네임 스페이스 또는 가져오기 별칭을 포함 합니다. 다음 예제에서는 가져오기 별칭을 사용 합니다.  
  
```vb  
' The following statement must precede all your declarations.  
Imports win = System.Windows.Forms, web = System.Web.UI.WebControls  
' The following statement references the Windows.Forms.Label class.  
Dim winLabel As New win.Label()  
```  
  
## <a name="members-of-other-containing-elements"></a>포함 된 요소의 다른 멤버  
 다른 클래스 또는 구조체의 공유 되지 않는 멤버를 사용 하면 먼저 변수 또는 클래스 또는 구조체의 인스턴스를 가리키는 식으로 멤버 이름을 정규화 해야 합니다. 다음 예에서 `demoClass` 라는 클래스의 인스턴스가 `class1`합니다.  
  
```vb  
Dim demoClass As class1 = New class1()  
demoClass.someSub[(argumentlist)]  
```  
  
 한정 되지 않는 멤버를 클래스 이름 자체를 사용할 수 없습니다 [공유](../../../../visual-basic/language-reference/modifiers/shared.md)합니다. 개체 변수에서 인스턴스를 먼저 만들어야 (이 경우 `demoClass`) 변수 이름으로 참조 해야 합니다.  
  
 클래스 또는 구조체에는 `Shared` 멤버 클래스 또는 구조체 이름 또는 변수 또는 인스턴스를 가리키는 식으로 해당 멤버를 한정할 수 있습니다.  
  
 모듈에는 별도 모든 인스턴스가 및 모든 해당 멤버는 `Shared` 기본적으로 합니다. 따라서 모듈 이름을 모듈 멤버를 정규화 합니다.  
  
 다음 예제에서는 모듈 멤버 프로시저에 대 한 정규화 된 참조를 보여 줍니다. 이 예제에서는 두 개의 선언한 `Sub` 이라는 프로시저 `perform`, 프로젝트에서 서로 다른 모듈에 있습니다. 각 모듈 자체 내에서 한정 하지 않고 지정할 수 있지만 다른 곳에서 참조 하는 경우에 한정 되어야 합니다. 마지막에 참조 하기 때문에 `module3` 한정 하지 않으므로 `perform`, 컴파일러는 해당 참조를 확인할 수 없습니다.  
  
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
 사용 하 여 [공용](../../../../visual-basic/language-reference/modifiers/public.md) 다른 프로젝트에 정의 된 요소를 먼저 설정 해야는 *참조* 해당 프로젝트의 어셈블리 또는 형식 라이브러리에 있습니다. 참조를 설정 하려면 클릭 **참조 추가** 에 **프로젝트** 메뉴를 사용 하거나 사용 하는 [/reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) 명령줄 컴파일러 옵션입니다.  
  
 XML 개체 모델을 사용할 수는 예를 들어는 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)]합니다. 대 한 참조를 설정 하는 경우는 <xref:System.Xml> 네임 스페이스를 선언 하 고 있습니다와 같은 해당 클래스를 사용 하 여 <xref:System.Xml.XmlDocument>합니다. 다음 예제에서는 <xref:System.Xml.XmlDocument>합니다.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As System.Xml.XmlDocument  
```  
  
## <a name="importing-containing-elements"></a>요소를 포함 하는 가져오기  
 사용할 수는 [Imports 문 (.NET 네임 스페이스 및 형식)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) 를 *가져올* 모듈이 나 사용 하 여 원하는 클래스를 포함 하는 네임 스페이스입니다. 이 이름을 정규화 하지 않고 가져온된 네임 스페이스에 정의 된 요소를 참조할 수 있습니다. 다음 예제에서는 이전 예제를 가져오려면 다시 작성 한는 <xref:System.Xml> 네임 스페이스입니다.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As XmlDocument  
```  
  
 또한는 `Imports` 문을 정의할 수는 *가져오기 별칭* 각 가져온된 네임 스페이스에 대 한 합니다. 소스 코드가 더 간결 하 고 읽기 쉽게 크기 수 있습니다. 다음 예제에서는 사용 하 여 이전 예제를 다시 작성 `xD` 별칭으로는 <xref:System.Xml> 네임 스페이스입니다.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports xD = System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As xD.XmlDocument  
```  
  
  `Imports` 문으로 하지 요소 만들 다른 프로젝트에서 응용 프로그램에 사용할 수 있습니다. 즉, 참조 설정의 위치를 가지 지 않습니다. 방금 네임 스페이스를 가져오면 해당 네임 스페이스에 정의 된 이름을 정규화 하는 요구 사항을 제거 합니다.  
  
 사용할 수도 있습니다는 `Imports` 을 모듈, 클래스, 구조체 및 열거형을 가져오기 위한 문입니다. 다음 한정자 없이 가져온 요소의 멤버를 사용할 수 있습니다. 그러나 클래스와 클래스 또는 구조체의 인스턴스로 반환 식 또는 변수를 사용 하 여 구조의 공유 되지 않는 멤버 항상 정규화 해야 합니다.  
  
## <a name="naming-guidelines"></a>명명 지침  
 동일한 이름을 가진 두 개 이상의 프로그래밍 요소를 정의 하는 경우는 *이름 모호성* 컴파일러에서이 이름에 대 한 참조를 확인 하려고 할 때 발생할 수 있습니다. 둘 이상의 정의가 두 개는 범위 또는 정의가 없는 범위에 있으면 참조를 해결할 수 없습니다. 예를 들어이 도움말 페이지에 "정규화 된 참조 예제"를 참조 하십시오.  
  
 모든 요소에 고유한 이름을 지정 하 여 이름 모호성을 방지할 수 있습니다. 다음 네임 스페이스, 모듈 또는 클래스를 사용 하 여 이름을 한정 하지 않고도 요소에 대 한 참조를 만들 수 있습니다. 실수로 잘못 된 요소를 가리키는 가능성이 줄일 수 있습니다.  
  
## <a name="shadowing"></a>숨기기  
 동일한 이름을 공유 하는 두 가지 프로그래밍 요소를 숨길 수 중 하나, 또는 *섀도*, 다른 하나입니다. 숨겨진된 요소는 참조;에 사용할 수 없습니다. 대신 코드에서 숨겨진된 요소 이름을 사용은 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 컴파일러 숨기는 요소를 확인 합니다. 더 자세한 내용 및 예제를 참조 하십시오. [Visual Basic의 숨김 기능](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [선언된 요소 이름](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [선언된 요소의 특징](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)   
 [NIB 하는 방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [변수](../../../../visual-basic/programming-guide/language-features/variables/index.md)   
 [Imports 문 (.NET 네임 스페이스 및 형식)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [New 연산자](../../../../visual-basic/language-reference/operators/new-operator.md)   
 [공개](../../../../visual-basic/language-reference/modifiers/public.md)