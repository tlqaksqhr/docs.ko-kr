---
title: "Objects and Classes in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "classes [Visual Basic]"
  - "objects [Visual Basic]"
ms.assetid: c68c5752-1006-46e1-975a-6717b62a42fc
caps.latest.revision: 26
caps.handback.revision: 26
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Objects and Classes in Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

*개체*는 하나의 단위로 취급할 수 있는 코드 및 데이터의 조합입니다.  개체는 컨트롤이나 폼과 같이 응용 프로그램의 부분이 될 수 있습니다.  또한 응용 프로그램 전체가 하나의 개체로 될 수 있습니다.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]으로 응용 프로그램을 만들 때에는 개체를 빈번히 사용합니다.  컨트롤, 폼 및 데이터 액세스 개체 등과 같이 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서 제공하는 개체를 사용할 수 있습니다.  또한 다른 응용 프로그램의 개체를 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 응용 프로그램 내에서 사용할 수도 있습니다.  심지어는 직접 고유한 개체를 만들고 해당 개체에 대해 추가 속성 및 메서드를 정의할 수도 있습니다.  개체는 프로그램에 대한 조립식 빌드 블록처럼 작동합니다. 즉, 개체를 사용하면 코드 부분을 작성하여 계속해서 다시 사용할 수 있습니다.  
  
 이 항목에서는 개체에 대해 자세히 설명합니다.  
  
## 개체 및 클래스  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]의 각 개체는 *클래스*에서 정의합니다.  클래스는 개체의 변수, 속성, 프로시저 및 이벤트를 설명합니다.  개체는 클래스의 인스턴스입니다. 따라서 일단 클래스를 정의한 후에는 필요한 만큼 개체를 만들 수 있습니다.  
  
 개체와 해당 클래스 간 관계를 이해하려면 쿠키 커터와 쿠키를 생각합니다.  쿠키 커터는 클래스에 해당합니다.  쿠키 커터는 크기 및 모양과 같은 각 쿠키의 특징을 정의합니다.  클래스는 개체를 만드는 데 사용됩니다.  또한 개체는 쿠키에 해당합니다.  
  
 멤버에 액세스하려면 먼저 개체를 만들어야 합니다.  
  
#### 클래스에서 개체를 만들려면  
  
1.  개체를 만들 클래스를 결정합니다.  
  
2.  [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md)을 사용하여 클래스 인스턴스를 할당할 수 있는 변수를 만듭니다.  이 변수는 원하는 클래스와 같은 형식이어야 합니다.  
  
    ```  
  
    Dim nextCustomer As customer   
    ```  
  
3.  [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) 키워드를 추가하여 변수를 해당 클래스의 새 인스턴스로 초기화합니다.  
  
    ```  
    Dim nextCustomer As New customer  
    ```  
  
4.  이제 이 개체 변수를 통해 클래스의 멤버에 액세스할 수 있습니다.  
  
    ```  
  
    nextCustomer.accountNumber = lastAccountNumber + 1  
    ```  
  
> [!NOTE]
>  가능하면 변수 형식은 해당 변수에 할당할 클래스의 형식으로 선언해야 합니다.  이러한 방식을 *초기 바인딩*이라고 합니다.  컴파일 타임에 클래스 형식을 모르면 변수를 [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)으로 선언하여 *런타임에 바인딩*을 호출할 수 있습니다.  그러나 런타임에 바인딩을 사용하면 성능이 저하되고 런타임 개체의 멤버에 대한 액세스가 제한될 수 있습니다.  자세한 내용은 [Object Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)을 참조하십시오.  
  
### 여러 인스턴스  
 클래스에서 새로 만들어진 개체는 대개 서로 동일합니다.  그러나 개체가 개별적인 개체로 존재하는 동안에는 해당 변수 및 속성를 다른 인스턴스와 독립적으로 변경할 수 있습니다.  예를 들어, 폼에 세 개의 확인란을 추가하면 각 확인란 개체는 <xref:System.Windows.Forms.CheckBox> 클래스의 인스턴스가 됩니다.  각 <xref:System.Windows.Forms.CheckBox> 개체는 클래스에서 정의하는 특징 및 기능\(속성, 변수, 프로시저 및 이벤트\)의 공통 집합을 공유합니다.  그러나 각 개체는 고유한 이름을 가지며 개별적으로 활성화되고 비활성화될 수 있습니다. 또한 폼에서 서로 다른 위치에 있을 수도 있습니다.  
  
## 개체 멤버  
 개체는 클래스의 *인스턴스*를 나타내는 응용 프로그램 요소이고  필드, 속성, 메서드 및 이벤트는 개체의 빌딩 블록이며 *멤버*를 구성합니다.  
  
### 멤버 액세스  
 개체 이름, 마침표\(`.`\) 및 멤버 이름 순으로 지정하여 개체의 멤버에 액세스합니다.  다음 예제에서는 <xref:System.Windows.Forms.Label> 개체의 <xref:System.Windows.Forms.Control.Text%2A> 속성을 설정합니다.  
  
```  
warningLabel.Text = "Data not saved"  
```  
  
#### IntelliSense 멤버 목록  
 멤버 목록 옵션을 호출\(예: 멤버 액세스 연산자로 마침표\(`.`\) 입력\)하면 IntelliSense에서 클래스 멤버 목록을 표시합니다.  해당 클래스의 인스턴스로 선언된 변수 이름 다음에 마침표를 입력하면 IntelliSense에서는 모든 인스턴스 멤버를 나열하고 공유 멤버는 나열하지 않습니다.  클래스 이름 다음에 마침표를 입력하면 IntelliSense에서는 모든 공유 멤버를 나열하고 인스턴스 멤버는 나열하지 않습니다.  자세한 내용은 [IntelliSense 사용](/visual-studio/ide/using-intellisense)을 참조하십시오.  
  
### 필드 및 속성  
 *필드* 및 *속성*은 개체에 저장된 정보를 나타냅니다.  이 값을 검색하고 설정하려면 프로시저의 지역 변수를 검색하고 설정할 때와 동일한 방법으로 대입문을 사용합니다.  다음 예제에서는 <xref:System.Windows.Forms.Label> 개체의 <xref:System.Windows.Forms.Control.Width%2A> 속성을 검색하고 <xref:System.Windows.Forms.Control.ForeColor%2A> 속성을 설정합니다.  
  
```  
Dim warningWidth As Integer = warningLabel.Width  
warningLabel.ForeColor = System.Drawing.Color.Red  
```  
  
 필드를 *멤버 변수*라고도 합니다.  
  
 다음 경우에 속성 프로시저를 사용합니다.  
  
-   값이 설정되고 검색되는 시기와 방법을 제어해야 하는 경우  
  
-   속성에 유효성을 검사해야 하는 잘 정의된 값 집합이 들어 있는 경우  
  
-   `IsVisible` 속성처럼 값을 설정했을 때 개체의 상태가 크게 변경되는 경우  
  
-   속성을 설정했을 때 다른 내부 변수나 다른 속성의 값으로 변경되는 경우  
  
-   속성을 설정하거나 검색하기 전에 일련의 작업 단계를 수행해야 하는 경우  
  
 다음 경우에 필드를 사용합니다.  
  
-   값이 자체적으로 유효성을 검사하는 형식인 경우.  예를 들어, `Boolean` 변수에 `True` 또는 `False` 이외의 값이 할당되면 오류가 발생하거나 자동 데이터 변환이 수행됩니다.  
  
-   데이터 형식에서 지원하는 범위의 값이 유효한 경우.  `Single` 또는 `Double` 형식의 여러 속성에도 적용됩니다.  
  
-   속성이 `String` 데이터 형식이고 문자열의 크기나 값에 대해 제약 조건이 없는 경우  
  
-   자세한 내용은 [Property 프로시저](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)를 참조하십시오.  
  
### 메서드  
 *메서드*는 개체에서 수행할 수 있는 작업입니다.  예를 들어, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Add%2A>는 콤보 상자에 새 항목을 추가하는 <xref:System.Windows.Forms.ComboBox> 개체의 메서드입니다.  
  
 다음 예제에서는 <xref:System.Windows.Forms.Timer> 개체의 <xref:System.Windows.Forms.Timer.Start%2A> 메서드를 보여 줍니다.  
  
```  
Dim safetyTimer As New System.Windows.Forms.Timer  
safetyTimer.Start()  
```  
  
 메서드는 단순히 개체에 의해 노출되는 *프로시저*입니다.  
  
 자세한 내용은 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)을 참조하십시오.  
  
### 이벤트  
 이벤트는 마우스 클릭 또는 키 누르기 등 개체에서 인식하고 코드를 작성하여 응답할 수 있는 작업입니다.  이벤트는 사용자 동작 또는 프로그램 코드의 결과로 발생하거나 시스템에 의해 발생될 수 있습니다.  이벤트에 대한 신호를 보내는 코드를 가리켜 이벤트를 *발생시킨다*고 하고, 이 신호에 응답하는 코드를 가리켜 이벤트를 *처리한다*고 합니다.  
  
 또한 개체에 의해 발생되어 다른 개체에서 처리하는 사용자 지정 이벤트를 개발할 수도 있습니다.  자세한 내용은 [Events](../../../../visual-basic/programming-guide/language-features/events/events.md)를 참조하십시오.  
  
### 인스턴스 멤버 및 공유 멤버  
 클래스에서 개체를 만들면 만들어진 개체는 해당 클래스의 인스턴스가 됩니다.  [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) 키워드로 선언되지 않은 멤버는 해당 특정 인스턴스에 속하는 *인스턴스 멤버*입니다.  한 인스턴스의 인스턴스 멤버는 동일한 클래스에 있는 다른 인스턴스의 동일한 멤버로부터 독립적입니다.  예를 들어, 인스턴스 멤버 변수는 인스턴스마다 다른 값을 가질 수 있습니다.  
  
 `Shared` 키워드로 선언된 멤버는 클래스의 특정 인스턴스가 아니라 클래스 전체에 속하는 *공유 멤버*입니다.  공유 멤버는 사용자가 만든 클래스 인스턴스의 수에 관계없이\(인스턴스를 만들지 않은 경우도 포함\) 하나만 존재합니다.  예를 들어, 공유 멤버 변수에는 값이 하나만 있으며 해당 클래스에 액세스할 수 있는 모든 코드에서 이 값을 사용할 수 있습니다.  
  
#### 비공유 멤버에 액세스  
  
###### 개체의 비공유 멤버에 액세스하려면  
  
1.  개체가 해당 클래스에서 만들어졌고 개체 변수에 할당되었는지 확인합니다.  
  
    ```  
    Dim secondForm As New System.Windows.Forms.Form  
    ```  
  
2.  멤버에 액세스하는 문에서 개체 변수 이름 뒤에 *멤버 액세스 연산자*\(`.`\)와 멤버 이름을 차례로 붙입니다.  
  
    ```  
    secondForm.Show()  
    ```  
  
#### 공유 멤버에 액세스  
  
###### 개체의 공유 멤버에 액세스하려면  
  
-   클래스 이름 뒤에 *멤버 액세스 연산자*\(`.`\)와 멤버 이름을 차례로 붙입니다.  개체의 `Shared` 멤버에 액세스하려면 항상 클래스 이름을 직접 사용해야 합니다.  
  
    ```  
    MsgBox("This computer is called " & Environment.MachineName)  
    ```  
  
-   클래스에서 이미 개체를 만든 경우 개체의 변수를 통해 `Shared` 멤버에 액세스할 수도 있습니다.  
  
### 클래스와 모듈의 차이점  
 클래스와 모듈의 주요 차이점은 클래스는 개체로 인스턴스화될 수 있지만 표준 모듈은 개체로 인스턴스화될 수 없다는 것입니다.  표준 모듈의 데이터 복사본은 하나만 존재할 수 있으므로 프로그램의 한 부분에서 표준 모듈의 공용 변수를 변경하면 프로그램의 다른 부분에서도 해당 변수를 읽을 때 동일한 값을 얻습니다.  반면 개체 데이터는 인스턴스화된 각 개체마다 별도로 존재합니다.  뿐만 아니라 표준 모듈과 달리 클래스는 인터페이스를 구현할 수 있습니다.  
  
> [!NOTE]
>  `Shared` 한정자를 클래스 멤버에 적용하면 클래스의 특정 인스턴스 대신 클래스 자체와 연결됩니다.  멤버는 모듈 멤버를 액세스하는 방법과 같은 방법으로 클래스 이름을 사용하여 직접 액세스합니다.  
  
 또한 클래스와 모듈은 해당 멤버에 대해 다른 범위를 사용합니다.  한 클래스 내에 정의된 멤버는 해당 클래스의 특정 인스턴스 내에서 범위가 지정되며 해당 개체의 수명이 지속되는 동안에만 존재합니다.  클래스 외부에서 클래스 멤버에 액세스하려면 *Object*.*Member* 형식의 정규화된 이름을 사용해야 합니다.  
  
 그러나 모듈 내에서 선언된 멤버는 기본적으로 공개적으로 액세스할 수 있으며 해당 모듈에 액세스할 수 있는 모든 코드로 액세스할 수 있습니다.  따라서 표준 모듈의 변수는 해당 프로젝트의 어디에서나 볼 수 있으며 프로그램의 수명이 지속되는 동안 존재하므로 전역 변수에 해당합니다.  
  
## 클래스 및 개체 다시 사용  
 개체를 사용하면 변수 및 프로시저를 선언한 다음 필요할 때마다 다시 사용할 수 있습니다.  예를 들어, 맞춤법 검사기를 응용 프로그램에 추가하려는 경우 맞춤법 검사 기능을 제공하기 위한 모든 변수 및 지원 함수를 정의할 수 있습니다.  맞춤법 검사기를 하나의 클래스로 만들 경우에는 컴파일링된 어셈블리에 참조를 추가하여 다른 응용 프로그램에서도 해당 맞춤법 검사기를 다시 사용할 수 있습니다.  뿐만 아니라 다른 사람이 이미 개발한 맞춤법 검사기 클래스를 사용하여 작업 시간을 줄일 수도 있습니다.  
  
 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)]에서는 사용할 수 있는 여러 가지 구성 요소의 예를 제공합니다.  다음 예제에서는 <xref:System> 네임스페이스에 있는 <xref:System.TimeZone> 클래스를 사용합니다.  <xref:System.TimeZone>에는 현재 컴퓨터 시스템의 시간대에 대한 정보를 검색하는 데 사용할 수 있는 멤버가 있습니다.  
  
```  
Public Sub examineTimeZone()  
    Dim tz As System.TimeZone = System.TimeZone.CurrentTimeZone  
    Dim s As String = "Current time zone is "  
    s &= CStr(tz.GetUtcOffset(Now).Hours) & " hours and "  
    s &= CStr(tz.GetUtcOffset(Now).Minutes) & " minutes "  
    s &= "different from UTC (coordinated universal time)"  
    s &= vbCrLf & "and is currently "  
    If tz.IsDaylightSavingTime(Now) = False Then s &= "not "  
    s &= "on ""summer time""."  
    MsgBox(s)  
End Sub  
```  
  
 앞의 예제에서 첫 번째 [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md)은 <xref:System.TimeZone> 형식의 개체 변수를 선언하고 이를 <xref:System.TimeZone.CurrentTimeZone%2A> 속성에서 반환된 <xref:System.TimeZone> 개체에 할당합니다.  
  
## 개체 간의 관계  
 개체는 여러 방법으로 서로 연관될 수 있습니다.  기본적인 관계 유형으로는 *계층* 관계와 *포함* 관계가 있습니다.  
  
### 계층 관계  
 클래스가 더 기본적인 클래스에서 파생된 경우 두 클래스는 *계층 관계*에 있다고 합니다.  클래스 계층 구조는 좀 더 일반적인 클래스의 하위 형식에 해당하는 항목을 설명할 때 매우 유용합니다.  
  
 다음 예제에서는 일반적인 <xref:System.Windows.Forms.Button>처럼 동작하지만 전경색과 배경색을 바꾸는 메서드를 제공하는 특수한 종류의 <xref:System.Windows.Forms.Button>을 정의하려고 한다고 가정합니다.  
  
##### 기존 클래스에서 파생되는 클래스를 정의하려면  
  
1.  [Class Statement](../../../../visual-basic/language-reference/statements/class-statement.md)을 사용하여 필요한 개체를 만드는 데 사용할 클래스를 정의합니다.  
  
     `Public Class reversibleButton`  
  
     `End Class` 문은 클래스의 마지막 코드 줄 뒤에 와야 합니다.  기본적으로 IDE\(통합 개발 환경\)에서는 `Class` 문을 입력하면 `End Class`가 자동으로 생성됩니다.  
  
2.  `Class` 문 바로 뒤에 [Inherits Statement](../../../../visual-basic/language-reference/statements/inherits-statement.md)을 추가합니다.  새 클래스가 파생되는 기본 클래스를 지정합니다.  
  
     `Inherits System.Windows.Forms.Button`  
  
     새 클래스는 기본 클래스에 정의된 모든 멤버를 상속합니다.  
  
3.  파생 클래스에서 제공할 추가 멤버에 대한 코드를 추가합니다.  예를 들어, `reverseColors` 메서드를 추가하면 다음과 같은 파생 클래스가 작성됩니다.  
  
    ```  
    Public Class reversibleButton  
        Inherits System.Windows.Forms.Button  
        Public Sub reverseColors()   
            Dim saveColor As System.Drawing.Color = Me.BackColor  
            Me.BackColor = Me.ForeColor  
            Me.ForeColor = saveColor  
        End Sub  
    End Class   
    ```  
  
     `reversibleButton` 클래스에서 개체를 만들면 이 개체는 `reversibleButton`에 정의된 `reverseColors` 메서드와 다른 모든 새 멤버뿐 아니라 <xref:System.Windows.Forms.Button> 클래스와 모든 멤버에도 액세스할 수 있습니다.  
  
 파생 클래스는 기반하는 클래스에서 멤버를 상속하므로 클래스 계층 구조를 점점 더 복잡하게 형성할 수 있습니다.  자세한 내용은 [Inheritance Basics](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)을 참조하십시오.  
  
#### 코드 컴파일  
 컴파일러에서는 새 클래스가 파생될 기본 클래스에 액세스할 수 있어야 합니다.  이를 위해서는 앞의 예제처럼 이름을 한정하거나 [Imports Statement \(.NET Namespace and Type\)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)에서 해당 네임스페이스를 지정해야 합니다.  클래스가 다른 프로젝트에 있으면 해당 프로젝트에 대한 참조를 추가해야 합니다.  자세한 내용은 [프로젝트의 참조 관리](/visual-studio/ide/managing-references-in-a-project)를 참조하십시오.  
  
### 포함 관계  
 개체 간에 가능한 또 다른 관계는 *포함 관계*입니다.  컨테이너 개체는 다른 개체를 논리적으로 캡슐화합니다.  예를 들어, <xref:System.OperatingSystem> 개체는 <xref:System.OperatingSystem.Version%2A> 속성을 통해 반환되는 <xref:System.Version> 개체를 논리적으로 포함합니다.  컨테이너 개체에 다른 개체가 실제로 포함되는 것은 아닙니다.  
  
#### 컬렉션  
 개체 포함의 한 가지 특별한 유형은 *컬렉션*으로 나타낼 수 있습니다.  컬렉션은 열거할 수 있는 유사한 개체의 그룹입니다.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 컬렉션의 항목 전체를 반복할 수 있는 [For Each...Next 문](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)의 특정 구문을 지원합니다.  또한 컬렉션을 사용할 경우에는 <xref:Microsoft.VisualBasic.Collection.Item%2A>을 사용하여 인덱스를 지정하거나 또는 요소를 고유한 문자열에 연결하는 방법으로 요소를 검색할 수도 있습니다.  컬렉션을 사용하면 인덱스를 사용하지 않고도 항목을 추가 또는 제거할 수 있으므로 배열보다 쉽게 사용할 수 있습니다.  이와 같이 컬렉션은 사용이 용이하므로 폼과 컨트롤을 저장하는 데에도 자주 사용됩니다.  
  
## 관련 항목  
 [Walkthrough: Defining Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/walkthrough-defining-classes.md)  
 클래스를 만드는 방법을 단계별로 설명합니다.  
  
 [Overloaded Properties and Methods](../../../../visual-basic/programming-guide/language-features/objects-and-classes/overloaded-properties-and-methods.md)  
 오버로드된 속성 및 메서드  
  
 [Inheritance Basics](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 메서드 및 속성을 재정의하는 상속 한정자인 MyClass 및 MyBase를 다룹니다.  
  
 [Object Lifetime: How Objects Are Created and Destroyed](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)  
 클래스 인스턴스의 만들기 및 삭제에 대해 설명합니다.  
  
 [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 데이터 형식에 대한 클래스 정의를 작성하지 않고 개체를 만들 수 있는 익명 형식을 만들고 사용하는 방법에 대해 설명합니다.  
  
 [Object Initializers: Named and Anonymous Types](../Topic/Object%20Initializers:%20Named%20and%20Anonymous%20Types%20\(Visual%20Basic\).md)  
 단일 식을 사용하여 명명된 형식과 익명 형식의 인스턴스를 만드는 데 사용하는 개체 이니셜라이저에 대해 설명합니다.  
  
 [방법: 익명 형식 선언에서 속성 이름 및 형식 유추](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)  
 익명 형식 선언에서 속성 이름과 형식을 유추하는 방법에 대해 설명합니다.  성공적인 유추와 실패한 유추의 예제를 제공합니다.