---
title: "연습: Visual Basic에서 합성 컨트롤 제작 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "복합 컨트롤, 만들기"
  - "컨트롤[Windows Forms], 복합 컨트롤"
  - "사용자 지정 컨트롤[Visual Basic]"
  - "사용자 지정 컨트롤[Windows Forms], 만들기"
  - "사용자 정의 컨트롤[Visual Basic]"
  - "사용자 정의 컨트롤[Windows Forms], Visual Basic을 사용하여 만들기"
  - "UserControl 클래스, 연습"
ms.assetid: f50e270e-4db2-409a-8319-6db6ca5c7daf
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# 연습: Visual Basic에서 합성 컨트롤 제작
복합 컨트롤을 사용하면 사용자 지정 그래픽 인터페이스를 만들고 다시 사용할 수 있습니다.  복합 컨트롤은 본질적으로 시각적 표시를 가진 구성 요소입니다.  그러므로 사용자 정의 컨트롤은 하나 이상의 Windows Form 컨트롤이나 구성 요소로 구성될 수도 있고 사용자 입력을 검증하거나 표시 속성을 수정하거나 제작자가 요구하는 다른 작업을 수행함으로써 기능을 확장할 수 있는 코드 블록으로 구성될 수도 있습니다.  복합 컨트롤은 다른 컨트롤과 마찬가지 방법으로 Windows Form에 배치될 수 있습니다.  이 연습의 첫 번째 부분에서는 `ctlClock`이라는 간단한 복합 컨트롤을 만듭니다.  이 연습의 두 번째 부분에서는 상속을 통해 `ctlClock`의 기능을 확장합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
## 프로젝트 만들기  
 새 프로젝트를 만들 때는 이름에서 루트 네임스페이스, 어셈블리 이름 및 프로젝트 이름을 설정하도록 지정하여 기본 구성 요소가 올바른 네임스페이스에 놓이도록 해야 합니다.  
  
#### ctlClockLib 컨트롤 라이브러리 및 ctlClock 컨트롤을 만들려면  
  
1.  **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭하여 **새 프로젝트** 대화 상자를 엽니다.  
  
2.  [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 프로젝트의 목록에서 **Windows 컨트롤 라이브러리** 프로젝트 템플릿을 선택하고 `이름` 상자에 **ctlClockLib**를 입력한 다음 **확인**을 클릭합니다.  
  
     기본적으로 프로젝트 이름인 `ctlClockLib`도 루트 네임스페이스에 할당됩니다.  루트 네임스페이스는 어셈블리에서 구성 요소의 이름을 한정하는 데 사용됩니다.  예를 들어, 두 어셈블리에서 `ctlClock`이라는 이름의 구성 요소가 제공되는 경우 `ctlClockLib.ctlClock.` 을 사용하여 `ctlClock` 구성 요소를 지정할 수 있습니다.  
  
3.  솔루션 탐색기에서 **UserControl1.vb**를 마우스 오른쪽 단추로 클릭하고 **이름 바꾸기**를 클릭합니다.  파일 이름을 `ctlClock.vb`로 변경합니다.  모든 참조의 이름을 코드 요소 "UserControl1"로 바꿀지 여부를 묻는 메시지가 나타나면 **예** 단추를 클릭합니다.  
  
    > [!NOTE]
    >  기본적으로 복합 컨트롤은 시스템에서 제공하는 <xref:System.Windows.Forms.UserControl> 클래스에서 상속됩니다.  <xref:System.Windows.Forms.UserControl> 클래스는 모든 복합 컨트롤에서 요구하는 기능을 제공하며 표준 메서드 및 속성을 구현합니다.  
  
4.  **파일** 메뉴에서 **모두 저장**을 클릭하여 프로젝트를 저장합니다.  
  
## 복합 컨트롤에 Windows 컨트롤 및 구성 요소 추가  
 시각적 인터페이스는 복합 컨트롤의 필수적인 부분입니다.  이 시각적 인터페이스는 디자이너 화면에 하나 이상의 Windows 컨트롤을 추가하여 구현할 수 있습니다.  아래 데모에서는 Windows 컨트롤을 복합 컨트롤에 결합한 다음 코드를 작성하여 기능을 구현합니다.  
  
#### Label 및 Timer를 복합 컨트롤에 추가하려면  
  
1.  솔루션 탐색기에서 **ctlClock.vb**를 마우스 오른쪽 단추로 클릭한 다음 **디자이너 보기**를 클릭합니다.  
  
2.  도구 상자에서 **공용 컨트롤** 노드를 확장한 다음 **Label**을 두 번 클릭합니다.  
  
     `Label1`이라는 <xref:System.Windows.Forms.Label> 컨트롤이 디자이너 화면에 있는 컨트롤에 추가됩니다.  
  
3.  디자이너에서 **Label1**을 클릭합니다.  속성 창에서 다음 속성을 설정합니다.  
  
    |Property|다음으로 변경|  
    |--------------|-------------|  
    |**Name**|`lblDisplay`|  
    |**Text**|`(공백)`|  
    |**TextAlign**|`MiddleCenter`|  
    |**Font.Size**|`14`|  
  
4.  **도구 상자**에서 **구성 요소** 노드를 확장한 다음 **Timer**를 두 번 클릭합니다.  
  
     <xref:System.Windows.Forms.Timer>는 구성 요소이므로 런타임에 시각적으로 표시되지 않습니다.  따라서 디자이너 화면에 컨트롤과 함께 나타나지 않고 구성 요소 디자이너\(디자이너 화면의 아래쪽에 있는 트레이\)에 나타납니다.  
  
5.  구성 요소 디자이너에서 **Timer1**을 클릭한 다음 <xref:System.Windows.Forms.Timer.Interval%2A> 속성은 `1000`으로, <xref:System.Windows.Forms.Timer.Enabled%2A> 속성은 `True`로 설정합니다.  
  
     <xref:System.Windows.Forms.Timer.Interval%2A> 속성은 타이머 구성 요소가 작동하는 빈도를 제어합니다.  `Timer1`이 작동할 때마다 `Timer1_Tick` 이벤트의 코드가 실행됩니다.  간격은 한 동작과 다음 동작 사이의 시간을 1\/1000초 단위로 나타냅니다.  
  
6.  구성 요소 디자이너에서 **Timer1**을 두 번 클릭한 다음 `ctlClock`의 `Timer1_Tick` 이벤트로 이동합니다.  
  
7.  코드를 다음 코드 샘플과 비슷하게 수정합니다.  액세스 한정자를 반드시 `Private`에서 `Protected`로 변경합니다.  
  
     \[Visual Basic\]  
  
    ```  
    Protected Sub Timer1_Tick(ByVal sender As Object, ByVal e As _  
        System.EventArgs) Handles Timer1.Tick  
        ' Causes the label to display the current time.    
        lblDisplay.Text = Format(Now, "hh:mm:ss")  
    End Sub  
    ```  
  
     이 코드에서는 현재 시간이 `lblDisplay`에 표시되도록 합니다.  `Timer1`의 간격이 `1000`으로 설정되었기 때문에 이 이벤트는 1000밀리초\(1초\)마다 발생하여 현재 시간을 매초 업데이트합니다.  
  
8.  메서드를 재정의 가능하도록 수정합니다.  자세한 내용은 아래의 "복합 컨트롤로부터 상속" 단원을 참조하십시오.  
  
     \[Visual Basic\]  
  
    ```  
    Protected Overridable Sub Timer1_Tick(ByVal sender As Object, ByVal _  
        e As System.EventArgs) Handles Timer1.Tick  
    ```  
  
9. **파일** 메뉴에서 **모두 저장**을 클릭하여 프로젝트를 저장합니다.  
  
## 복합 컨트롤에 속성 추가  
 이제 클럭 컨트롤에서는 자체적으로 기본적인 속성 집합을 가진 <xref:System.Windows.Forms.Label> 컨트롤과 <xref:System.Windows.Forms.Timer> 구성 요소를 캡슐화합니다.  이들 컨트롤의 개별 속성은 다른 사용자가 액세스할 수 없지만 적절한 코드 블록을 작성하여 사용자 지정 속성을 만들어 노출할 수 있습니다.  다음 절차에서는 사용자가 배경색과 텍스트 색을 변경할 수 있도록 해주는 속성을 컨트롤에 추가합니다.  
  
#### 복합 컨트롤에 속성을 추가하려면  
  
1.  솔루션 탐색기에서 **ctlClock.vb**를 마우스 오른쪽 단추로 클릭하고 **코드 보기**를 클릭합니다.  
  
     컨트롤에 대해 코드 편집기가 열립니다.  
  
2.  `Public Class ctlClock` 문을 찾아  이 문 아래에 다음 코드를 입력합니다.  
  
     \[Visual Basic\]  
  
    ```  
    Private colFColor as Color  
    Private colBColor as Color  
    ```  
  
     이들 문은 앞으로 만들 속성 값을 저장하는 데 사용할 개인 변수를 만듭니다.  
  
3.  2단계의 변수 선언 아래에 다음 코드를 삽입합니다.  
  
     \[Visual Basic\]  
  
    ```  
    ' Declares the name and type of the property.  
    Property ClockBackColor() as Color  
        ' Retrieves the value of the private variable colBColor.  
        Get  
            Return colBColor  
        End Get  
        ' Stores the selected value in the private variable colBColor, and   
        ' updates the background color of the label control lblDisplay.  
        Set(ByVal value as Color)  
            colBColor = value  
            lblDisplay.BackColor = colBColor     
        End Set  
  
    End Property  
    ' Provides a similar set of instructions for the foreground color.  
    Property ClockForeColor() as Color  
        Get  
            Return colFColor  
        End Get  
        Set(ByVal value as Color)  
            colFColor = value  
            lblDisplay.ForeColor = colFColor  
        End Set  
    End Property  
    ```  
  
     위의 코드는 두 개의 사용자 지정 속성인 `ClockForeColor` 및 `ClockBackColor`를 만들며, 이 속성은 이 컨트롤의 이후 사용자가 `Property` 문을 호출하여 사용할 수 있습니다.  `Get` 및 `Set` 문은 속성 값을 저장하고 검색할 뿐만 아니라 속성의 해당 기능을 구현하는 코드를 제공하기도 합니다.  
  
4.  **파일** 메뉴에서 **모두 저장**을 클릭하여 프로젝트를 저장합니다.  
  
## 컨트롤 테스트  
 컨트롤은 독립 실행형 프로젝트가 아니며 컨테이너에서 호스팅되어야 합니다.  컨트롤의 런타임 동작을 테스트하고 **UserControl Test Container**를 사용하여 해당 속성을 실행해 봅니다.  자세한 내용은 [방법: UserControl의 런타임 동작 테스트](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)를 참조하십시오.  
  
#### 컨트롤을 테스트하려면  
  
1.  F5 키를 눌러 프로젝트를 빌드하고 **UserControl Test Container**에서 컨트롤을 실행합니다.  
  
2.  테스트 컨테이너의 속성 표에서 `ClockBackColor` 속성을 선택하고 드롭다운 화살표를 클릭하여 색상표를 표시합니다.  
  
3.  원하는 색을 클릭하여 선택합니다.  
  
     컨트롤의 배경색이 선택한 색으로 변경됩니다.  
  
4.  비슷한 이벤트 순서를 사용하여 `ClockForeColor` 속성이 예상한 대로 작동하는지 확인합니다.  
  
5.  **닫기**를 클릭하여 **UserControl Test Container**를 닫습니다.  
  
     이 단원 및 이전 단원에서는 구성 요소 및 Windows 컨트롤을 코드와 결합하여 복합 컨트롤 형태로 사용자 지정 기능을 제공하도록 패키지로 만드는 방법을 설명했습니다.  복합 컨트롤의 속성을 노출하는 방법과 이를 완료한 후 컨트롤을 테스트하는 방법을 설명했습니다.  다음 단원에서는 `ctlClock`을 기본으로 하여 상속된 복합 컨트롤을 만드는 방법에 대해 설명합니다.  
  
## 복합 컨트롤로부터 상속  
 이전 단원에서는 Windows 컨트롤, 구성 요소 및 코드를 다시 사용할 수 있는 복합 컨트롤로 결합하는 방법을 설명했습니다.  이제 이 복합 컨트롤을 다른 컨트롤을 만들 수 있는 기본 컨트롤로 사용할 수 있습니다.  기본 클래스에서 클래스를 파생시키는 프로세스를 *상속*이라고 합니다.  이 단원에서는 `ctlAlarmClock`이라는 복합 컨트롤을 만듭니다.  이 컨트롤은 부모 컨트롤인 `ctlClock`에서 파생됩니다.  부모 메서드를 재정의하고 새 메서드 및 속성을 추가하여 `ctlClock`의 기능을 확장하는 방법을 설명합니다.  
  
 상속된 컨트롤을 만드는 첫 번째 단계는 부모로부터 파생시키는 것입니다.  이렇게 하면 부모 컨트롤의 모든 속성, 메서드 및 그래픽 특성을 갖는 새 컨트롤이 만들어지지만 이 컨트롤을 새 기능이나 수정된 기능을 추가할 기본 컨트롤로 사용할 수도 있습니다.  
  
#### 상속된 컨트롤을 만들려면  
  
1.  솔루션 탐색기에서 **ctlClockLib**를 마우스 오른쪽 단추로 클릭하고 **추가**를 가리킨 다음 **사용자 정의 컨트롤**을 클릭합니다.  
  
     **새 항목 추가** 대화 상자가 열립니다.  
  
2.  **상속된 사용자 정의 컨트롤** 템플릿을 선택합니다.  
  
3.  **이름** 상자에 `ctlAlarmClock.vb`를 입력한 다음 **추가**를 클릭합니다.  
  
     **상속 선택**대화 상자가 열립니다.  
  
4.  **구성 요소 이름** 아래에서 **ctlClock**을 두 번 클릭합니다.  
  
5.  솔루션 탐색기에서 현재 프로젝트를 찾아봅니다.  
  
    > [!NOTE]
    >  **ctlAlarmClock.vb**라는 파일이 현재 프로젝트에 추가되었습니다.  
  
### 경보 속성 추가  
 복합 컨트롤에 속성을 추가하는 것과 같은 방법으로 상속된 컨트롤에도 속성을 추가합니다.  이제 속성 선언 구문을 사용하여 컨트롤에 두 개의 속성을 추가합니다. 이 중 하나는 경보가 꺼지는 날짜와 시간 값이 저장되는 `AlarmTime`이고 다른 하나는 경보 설정 여부를 나타내는 `AlarmSet`입니다.  
  
##### 복합 컨트롤에 속성을 추가하려면  
  
1.  솔루션 탐색기에서 **ctlAlarmClock**을 마우스 오른쪽 단추로 클릭한 다음 **코드 보기**를 선택합니다.  
  
2.  `Public Class ctlAlarmClock`으로 표시되는 ctlAlarmClock 컨트롤에 대한 클래스 선언을 찾습니다.  클래스 선언에 다음 코드를 삽입합니다.  
  
     \[Visual Basic\]  
  
    ```  
    Private dteAlarmTime As Date  
    Private blnAlarmSet As Boolean  
    ' These properties will be declared as Public to allow future   
    ' developers to access them.  
    Public Property AlarmTime() As Date  
        Get  
            Return dteAlarmTime  
        End Get  
        Set(ByVal value as Date)  
            dteAlarmTime = value  
        End Set  
    End Property  
    Public Property AlarmSet() As Boolean  
        Get  
            Return blnAlarmSet  
        End Get  
        Set(ByVal value as Boolean)  
            blnAlarmSet = value  
        End Set  
    End Property  
    ```  
  
### 컨트롤의 그래픽 인터페이스에 추가  
 상속받은 컨트롤은 이 컨트롤을 상속해 준 컨트롤과 같은 시각적 인터페이스를 가집니다.  상속받은 컨트롤은 부모 컨트롤과 같은 구성 요소 컨트롤을 가지지만 이들 구성 요소 컨트롤의 속성은 명시적으로 노출되어야 사용 가능해집니다.  복합 컨트롤에 추가하는 것과 같은 방법으로 상속된 복합 컨트롤의 그래픽 인터페이스에도 추가할 수 있습니다.  경보 클럭의 시각적 인터페이스에 계속 추가하기 위해 경보 소리가 날 때마다 깜박이는 Label 컨트롤을 추가할 것입니다.  
  
##### Label 컨트롤을 추가하려면  
  
1.  솔루션 탐색기에서 **ctlAlarmClock**을 마우스 오른쪽 단추로 클릭한 다음 **디자이너 보기**를 클릭합니다.  
  
     주 창에 `ctlAlarmClock`에 대한 디자이너가 열립니다.  
  
2.  `lblDisplay`\(컨트롤이 표시된 부분\)를 클릭하여 속성 창을 살펴봅니다.  
  
    > [!NOTE]
    >  모든 속성이 표시될 때는 흐리게 표시됩니다.  즉, 이러한 속성은 `lblDisplay`의 기본 속성이기 때문에 속성 창에서 수정하거나 액세스할 수 없습니다.  기본적으로 복합 컨트롤에 들어 있는 컨트롤은 `Private`이며 그 속성에는 어떠한 방법으로도 액세스할 수 없습니다.  
  
    > [!NOTE]
    >  복합 컨트롤의 이후 사용자가 내부 컨트롤에 액세스할 수 있도록 하려면 해당 컨트롤을 `Public` 또는 `Protected`로 선언하십시오.  이렇게 하면 복합 컨트롤에 포함된 컨트롤의 속성을 적절한 코드를 사용하여 설정하거나 수정할 수 있습니다.  
  
3.  복합 컨트롤에 <xref:System.Windows.Forms.Label> 컨트롤을 추가합니다.  
  
4.  마우스를 사용하여 <xref:System.Windows.Forms.Label> 컨트롤을 표시 상자 바로 아래로 끌어 옵니다.  속성 창에서 다음 속성을 설정합니다.  
  
    |Property|설정|  
    |--------------|--------|  
    |**Name**|`lblAlarm`|  
    |**Text**|Alarm\!|  
    |**TextAlign**|`MiddleCenter`|  
    |**Visible**|`False`|  
  
### 경보 기능 추가  
 이전 절차에서 복합 컨트롤에서 경보 기능을 활성화하는 속성 및 컨트롤을 추가했습니다.  이 절차에서는 현재 시간과 경보 시간을 비교하여 시간이 같을 경우 경보 소리와 경보 깜박임을 생성하는 코드를 추가합니다.  `ctlClock`의 `Timer1_Tick` 메서드를 재정의하고 코드를 추가하면 `ctlClock`의 기본 기능은 유지한 채 `ctlAlarmClock`의 기능을 확장할 수 있습니다.  
  
##### ctlClock의 Timer1\_Tick 메서드를 재정의하려면  
  
1.  솔루션 탐색기에서 **ctlAlarmClock.vb**를 마우스 오른쪽 단추로 클릭한 다음 **코드 보기**를 클릭합니다.  
  
2.  `Private blnAlarmSet As Boolean` 문을 찾아  이 문 바로 아래에 다음 문을 추가합니다.  
  
     \[Visual Basic\]  
  
    ```  
    Dim blnColorTicker as Boolean  
    ```  
  
3.  페이지 아래쪽에서 `End Class` 문을 찾아  `End Class` 문 바로 앞에 다음 코드를 추가합니다.  
  
     \[Visual Basic\]  
  
    ```  
    Protected Overrides Sub Timer1_Tick(ByVal sender As Object, ByVal e _  
        As System.EventArgs)  
        ' Calls the Timer1_Tick method of ctlClock.  
        MyBase.Timer1_Tick(sender, e)  
        ' Checks to see if the Alarm is set.  
        If AlarmSet = False Then  
            Exit Sub  
        End If  
        ' If the date, hour, and minute of the alarm time are the same as  
        ' now, flash and beep an alarm.   
        If AlarmTime.Date = Now.Date And AlarmTime.Hour = Now.Hour And _  
            AlarmTime.Minute = Now.Minute Then  
            ' Sounds an audible beep.  
            Beep()  
            ' Sets lblAlarmVisible to True, and changes the background color based on the   
            ' value of blnColorTicker. The background color of the label will   
            ' flash once per tick of the clock.  
            lblAlarm.Visible = True  
            If blnColorTicker = False Then  
                lblAlarm.BackColor = Color.PeachPuff  
                blnColorTicker = True  
            Else  
                lblAlarm.BackColor = Color.Plum  
                blnColorTicker = False  
            End If  
        Else  
            ' Once the alarm has sounded for a minute, the label is made   
            ' invisible again.  
            lblAlarm.Visible = False  
        End If  
    End Sub  
    ```  
  
     이 코드를 추가하면 몇 가지 작업을 수행할 수 있습니다.  `Overrides` 문은 컨트롤에 기본 컨트롤에서 상속된 메서드 대신 이 메서드를 사용하도록 지시합니다.  이 메서드는 호출될 경우 `MyBase.Timer1_Tick` 문을 호출하여 재정의되는 메서드를 호출하고 원본 컨트롤에 포함된 모든 기능이 이 컨트롤에서 재생성되도록 합니다.  그런 다음 추가 코드를 실행하여 경보 기능을 결합합니다.  경보 소리가 나면 깜박이는 레이블 컨트롤이 나타나고 경고음이 들립니다.  
  
    > [!NOTE]
    >  상속된 이벤트 처리기를 재정의하므로 `Handles` 키워드를 사용하여 해당 이벤트를 지정할 필요가 없습니다.  이벤트가 이미 후크되어 있으므로,  현재 재정의하고 있는 것은 모두 해당 처리기의 구현입니다.  
  
     경보 클럭 컨트롤이 거의 완성되었습니다.  남은 작업은 경보 해제 방법을 구현하는 것입니다.  이 작업을 하려면 `lblAlarm_Click` 메서드에 코드를 추가합니다.  
  
##### 경보 해제 메서드를 구현하려면  
  
1.  솔루션 탐색기에서 **ctlAlarmClock.vb**를 마우스 오른쪽 단추로 클릭한 다음 **디자이너 보기**를 클릭합니다.  
  
2.  디자이너에서 **lblAlarm**을 두 번 클릭합니다.  `Private Sub lblAlarm_Click` 줄에 대해 **코드 편집기**가 열립니다.  
  
3.  이 메서드를 다음 코드와 비슷하게 수정합니다.  
  
     \[Visual Basic\]  
  
    ```  
    Private Sub lblAlarm_Click(ByVal sender As Object, ByVal e As _  
     System.EventArgs) Handles lblAlarm.Click  
        ' Turns off the alarm.  
        AlarmSet = False  
        ' Hides the flashing label.  
        lblAlarm.Visible = False  
    End Sub  
    ```  
  
4.  **파일** 메뉴에서 **모두 저장**을 클릭하여 프로젝트를 저장합니다.  
  
### 폼에서 상속된 컨트롤 사용  
 기본 클래스 컨트롤인 `ctlClock`을 테스트한 것과 같은 방법으로 상속된 컨트롤을 테스트할 수 있습니다. F5 키를 눌러 프로젝트를 빌드하고 **UserControl Test Container**에서 컨트롤을 실행합니다.  자세한 내용은 [방법: UserControl의 런타임 동작 테스트](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)를 참조하십시오.  
  
 컨트롤을 배치하여 사용하려면 폼에서 컨트롤을 호스팅해야 합니다  표준 복합 컨트롤과 마찬가지로 상속된 복합 컨트롤은 독립 실행형이 아니며 폼이나 다른 컨테이너에서 호스팅되어야 합니다.  `ctlAlarmClock`의 기능은 복잡하므로 이를 테스트하려면 추가 코드가 필요합니다.  이 절차에서는 간단한 프로그램을 작성하여 `ctlAlarmClock`의 기능을 테스트합니다.  `ctlAlarmClock`의 `AlarmTime` 속성을 설정하고 표시하는 코드를 작성하여 기본 기능을 테스트합니다.  
  
##### 컨트롤을 빌드하고 테스트 폼에 추가하려면  
  
1.  솔루션 탐색기에서 **ctlClockLib**를 마우스 오른쪽 단추로 클릭하고 **빌드**를 클릭합니다.  
  
2.  **파일** 메뉴에서 **추가**를 가리킨 다음 **새 프로젝트**를 클릭합니다.  
  
3.  새 **Windows 응용 프로그램** 프로젝트를 솔루션에 추가하고 `Test`로 명명합니다.  
  
     **Test** 프로젝트가 솔루션 탐색기에 추가됩니다.  
  
4.  솔루션 탐색기에서 `Test` 프로젝트 노드를 마우스 오른쪽 단추로 클릭한 다음 **참조 추가**를 클릭하여 **참조 추가** 대화 상자를 엽니다.  
  
5.  **프로젝트**라는 레이블이 붙은 탭을 클릭합니다.  **ctlClockLib** 프로젝트가 **프로젝트 이름** 아래에 나열됩니다.  **ctlClockLib**를 두 번 클릭하여 해당 참조를 테스트 프로젝트에 추가합니다.  
  
6.  솔루션 탐색기에서 **Test**를 오른쪽 마우스 단추로 클릭하고 **빌드**를 클릭합니다.  
  
7.  **도구 상자**에서 **ctlClockLib Components** 노드를 확장합니다.  
  
8.  `ctlAlarmClock`을 두 번 클릭하여 **ctlAlarmClock** 인스턴스를 폼에 추가합니다.  
  
9. **도구 상자**에서 **DateTimePicker**를 찾아 두 번 클릭하여 <xref:System.Windows.Forms.DateTimePicker> 컨트롤을 폼에 추가하고 **Label**을 두 번 클릭하여 <xref:System.Windows.Forms.Label> 컨트롤을 추가합니다.  
  
10. 마우스를 사용하여 폼에서 편리한 위치에 컨트롤을 배치합니다.  
  
11. 이러한 컨트롤의 속성을 다음과 같은 방법으로 설정합니다.  
  
    |컨트롤|Property|값|  
    |---------|--------------|-------|  
    |`label1`|**Text**|`(공백)`|  
    ||**Name**|`lblTest`|  
    |`dateTimePicker1`|**Name**|`dtpTest`|  
    ||**Format**|<xref:System.Windows.Forms.DateTimePickerFormat>|  
  
12. 디자이너에서 **dtpTest**를 두 번 클릭합니다.  
  
     `Private Sub dtpTest_ValueChanged`에 대해 **코드 편집기**가 열립니다.  
  
13. 코드를 다음과 비슷하게 수정합니다.  
  
     \[Visual Basic\]  
  
    ```  
    Private Sub dtpTest_ValueChanged(ByVal sender As Object, ByVal e As _  
        System.EventArgs) Handles dtpTest.ValueChanged  
        ctlAlarmClock1.AlarmTime = dtpTest.Value  
        ctlAlarmClock1.AlarmSet = True  
        lblTest.Text = "Alarm Time is " & Format(ctlAlarmClock1.AlarmTime, _  
            "hh:mm")  
    End Sub  
    ```  
  
14. 솔루션 탐색기에서 **Test**를 마우스 오른쪽 단추로 클릭하고 **시작 프로젝트로 설정**을 클릭합니다.  
  
15. **디버그** 메뉴에서 **디버깅 시작**을 클릭합니다.  
  
     테스트 프로그램이 시작됩니다.  현재 시간이 `ctlAlarmClock` 컨트롤에서 업데이트되고 시작 시간이 <xref:System.Windows.Forms.DateTimePicker> 컨트롤에 표시됩니다.  
  
16. 분이 표시되는 <xref:System.Windows.Forms.DateTimePicker>를 클릭합니다.  
  
17. 키보드를 사용하여 `ctlAlarmClock`에 표시된 현재 시간보다 1분 빠른 분 값을 설정합니다.  
  
     경보 설정 시간이 `lblTest`에 표시됩니다.  표시된 시간이 경보 설정 시간에 도달할 때까지 기다립니다.  표시된 시간이 경보가 설정된 시간에 도달하면 경고음이 들리고 `lblAlarm`이 깜박입니다.  
  
18. `lblAlarm`을 클릭하여 경보를 해제합니다.  경보를 다시 설정할 수 있습니다.  
  
     이 연습에서는 주요 개념을 많이 다루었습니다.  컨트롤과 구성 요소를 복합 컨트롤 컨테이너에 결합하여 복합 컨트롤을 만드는 방법을 설명했습니다.  컨트롤에 속성을 추가하고 사용자 지정 기능을 구현하는 코드를 작성하는 방법을 설명했습니다.  마지막 단원에서는 상속을 통해 주어진 복합 컨트롤의 기능을 확장하고 호스트 메서드를 재정의하여 그 기능을 변경하는 방법을 설명했습니다.  
  
## 참고 항목  
 [사용자 지정 컨트롤의 종류](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)   
 [방법: 합성 컨트롤 제작](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md)   
 [방법: 도구 상자 항목 선택 대화 상자에 컨트롤 표시](../../../../docs/framework/winforms/controls/how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)   
 [Component Authoring Walkthroughs](../Topic/Component%20Authoring%20Walkthroughs.md)