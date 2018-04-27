---
title: '연습: Visual Basic에서 합성 컨트롤 제작'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Visual Basic]
- user controls [Visual Basic]
- UserControl class [Windows Forms], walkthroughs
- user controls [Windows Forms], creating with Visual Basic
- controls [Windows Forms], composite controls
- composite controls [Windows Forms], creating
- custom controls [Windows Forms], creating
ms.assetid: f50e270e-4db2-409a-8319-6db6ca5c7daf
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 71d1da2767ca15c4f78a4297d916f735a0ad604c
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-authoring-a-composite-control-with-visual-basic"></a>연습: Visual Basic에서 합성 컨트롤 제작
복합 컨트롤은 사용자 지정 그래픽 인터페이스를 만들고 재사용할 수 있는 방법을 제공합니다. 복합 컨트롤은 기본적으로 시각적 표현이 있는 구성 요소입니다. 따라서 사용자 입력의 유효성을 검사하고 표시 속성을 수정하거나 작성자가 요구하는 다른 작업을 수행하여 기능을 확장할 수 있는 하나 이상의 Windows Forms 컨트롤, 구성 요소 또는 코드 블록으로 구성할 수 있습니다. 복합 컨트롤은 다른 컨트롤과 동일한 방식으로 Windows Forms에 배치할 수 있습니다. 이 연습의 첫 번째 부분에서는 `ctlClock`이라는 간단한 복합 컨트롤을 만듭니다. 두 번째 부분에서는 상속을 통해 `ctlClock`의 기능을 확장합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
## <a name="creating-the-project"></a>프로젝트 만들기  
 새 프로젝트를 만들 때는 이에 대한 이름을 지정하여 루트 네임스페이스, 어셈블리 이름 및 프로젝트 이름을 설정하고 기본 구성 요소가 올바른 네임스페이스에 있는지 확인합니다.  
  
#### <a name="to-create-the-ctlclocklib-control-library-and-the-ctlclock-control"></a>ctlClockLib 컨트롤 라이브러리 및 ctlClock 컨트롤을 만들려면  
  
1.  **파일** 메뉴에서 **새로 만들기**를 가리키고 **프로젝트**를 선택하여 **새 프로젝트** 대화 상자를 엽니다.  
  
2.  Visual Basic 프로젝트의 목록에서 선택 된 **Windows 컨트롤 라이브러리** 프로젝트 템플릿, 형식 `ctlClockLib` 에 **이름** 상자를 선택한 다음 클릭 **확인**합니다.  
  
     프로젝트 이름, `ctlClockLib`는 기본적으로 루트 네임스페이스에도 할당됩니다. 루트 네임스페이스는 어셈블리에서 구성 요소의 이름을 정규화하는 데 사용됩니다. 예를 들어 두 어셈블리에서 `ctlClock`이라는 구성 요소를 제공하면 `ctlClockLib.ctlClock.`을 사용하여 `ctlClock` 구성 요소를 지정할 수 있습니다.  
  
3.  솔루션 탐색기에서 **UserControl1.vb**를 마우스 오른쪽 단추로 클릭한 다음 **이름 바꾸기**를 클릭합니다. 파일 이름을 `ctlClock.vb`로 변경합니다. 코드 요소 “UserControl1”에 대한 모든 참조 이름을 변경할지 묻는 메시지가 표시되면 **예** 단추를 클릭합니다.  
  
    > [!NOTE]
    >  기본적으로 합성 컨트롤에서 상속 된 <xref:System.Windows.Forms.UserControl> 시스템에서 제공 하는 클래스입니다. <xref:System.Windows.Forms.UserControl> 클래스 모든 복합 컨트롤에 필요한 기능을 제공 하 고 표준 메서드 및 속성을 구현 합니다.  
  
4.  **파일** 메뉴에서 **모두 저장**을 클릭하여 프로젝트를 저장합니다.  
  
## <a name="adding-windows-controls-and-components-to-the-composite-control"></a>복합 컨트롤에 Windows 컨트롤 및 구성 요소 추가  
 시각적 인터페이스는 복합 컨트롤의 필수적인 부분입니다. 이 시각적 인터페이스는 하나 이상의 Windows 컨트롤을 디자이너 화면에 추가하여 구현합니다. 다음 데모에서는 Windows 컨트롤을 복합 컨트롤에 통합하고 기능을 구현하는 코드를 작성합니다.  
  
#### <a name="to-add-a-label-and-a-timer-to-your-composite-control"></a>복합 컨트롤에 레이블 및 타이머를 추가하려면  
  
1.  솔루션 탐색기에서 **ctlClock.vb**를 마우스 오른쪽 단추로 클릭한 후 **뷰 디자이너**를 클릭합니다.  
  
2.  도구 상자에서 **공용 컨트롤** 노드를 확장한 후 **레이블**을 두 번 클릭합니다.  
  
     A <xref:System.Windows.Forms.Label> 라는 컨트롤 `Label1` 디자이너 화면에 컨트롤에 추가 됩니다.  
  
3.  디자이너에서 **Label1**을 클릭합니다. 속성 창에서 다음 속성을 설정합니다.  
  
    |속성|다음으로 변경|  
    |--------------|---------------|  
    |**이름**|`lblDisplay`|  
    |**텍스트**|`(blank space)`|  
    |**TextAlign**|`MiddleCenter`|  
    |**Font.Size**|`14`|  
  
4.  **도구 상자**에서 **구성 요소** 노드를 확장한 후 **타이머**를 두 번 클릭합니다.  
  
     때문에 <xref:System.Windows.Forms.Timer> 는 구성 요소를 런타임 시 시각적으로 표시 되지 있기 합니다. 따라서 디자이너 화면에 컨트롤과 함께 나타나지 않으며 구성 요소 디자이너(디자이너 화면 맨 아래 트레이)에 나타납니다.  
  
5.  구성 요소 디자이너에서 클릭 **Timer1**, 다음 설정의 <xref:System.Windows.Forms.Timer.Interval%2A> 속성을 `1000` 및 <xref:System.Windows.Forms.Timer.Enabled%2A> 속성을 `True`합니다.  
  
     <xref:System.Windows.Forms.Timer.Interval%2A> 속성 timer 구성 요소에서 작동 하는 빈도 제어 합니다. `Timer1`이 틱할 때마다 `Timer1_Tick` 이벤트에 있는 코드를 실행합니다. 간격은 틱 사이에 시간(밀리초)을 나타냅니다.  
  
6.  구성 요소 디자이너에서 **Timer1**을 두 번 클릭하여 `ctlClock`에 대한 `Timer1_Tick` 이벤트로 이동합니다.  
  
7.  다음 코드 샘플과 비슷하도록 코드를 수정합니다. `Private`에서 `Protected`로 액세스 한정자를 변경해야 합니다.  
  
    ```vb  
    Protected Sub Timer1_Tick(ByVal sender As Object, ByVal e As _  
        System.EventArgs) Handles Timer1.Tick  
        ' Causes the label to display the current time.    
        lblDisplay.Text = Format(Now, "hh:mm:ss")  
    End Sub  
    ```  
  
     이 코드를 통해 `lblDisplay`에 현재 시간이 표시됩니다. `Timer1`의 간격은 `1000`으로 설정되었으므로 이 이벤트는 천 밀리초마다 발생하므로 현재 시간이 1초마다 업데이트됩니다.  
  
8.  메서드를 재정의 가능하도록 수정합니다. 자세한 내용은 아래의 “사용자 컨트롤에서 상속” 섹션을 참조하세요.  
  
    ```vb  
    Protected Overridable Sub Timer1_Tick(ByVal sender As Object, ByVal _  
        e As System.EventArgs) Handles Timer1.Tick  
    ```  
  
9. **파일** 메뉴에서 **모두 저장**을 클릭하여 프로젝트를 저장합니다.  
  
## <a name="adding-properties-to-the-composite-control"></a>복합 컨트롤에 속성 추가  
 이제 시계 컨트롤 캡슐화는 <xref:System.Windows.Forms.Label> 제어 및 <xref:System.Windows.Forms.Timer> 기본적인 속성 집합과 함께 각 구성 요소입니다. 이러한 컨트롤의 개별 속성은 이후 컨트롤 사용자가 액세스할 수 없지만 적절한 코드 블록을 작성하여 사용자 지정 속성을 만들고 노출할 수 있습니다. 다음 프로시저에서 사용자가 배경 및 텍스트 색을 변경할 수 있도록 컨트롤에 속성을 추가합니다.  
  
#### <a name="to-add-a-property-to-your-composite-control"></a>복합 컨트롤에 속성을 추가하려면  
  
1.  솔루션 탐색기에서 **ctlClock.vb**를 마우스 오른쪽 단추로 클릭한 후 **코드 보기**를 클릭합니다.  
  
     컨트롤에 대한 코드 편집기가 열립니다.  
  
2.  `Public Class ctlClock` 문을 찾습니다. 아래에 다음 코드를 입력합니다.  
  
    ```vb  
    Private colFColor as Color  
    Private colBColor as Color  
    ```  
  
     이러한 문은 작성하려는 속성에 대한 값을 저장하는 데 사용할 private 변수를 만듭니다.  
  
3.  2단계에서 변수 선언 아래에 다음 코드를 삽입합니다.  
  
    ```vb  
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
  
     위의 코드는 `ClockForeColor` 및 `ClockBackColor`라는 두 사용자 지정 속성을 만들며 이 속성은 이 컨트롤의 후속 사용자가 `Property` 문을 호출하여 사용할 수 있습니다. `Get` 및 `Set` 문은 속성 값의 저장 및 검색과 속성에 맞는 기능을 구현하는 코드를 위해 제공됩니다.  
  
4.  **파일** 메뉴에서 **모두 저장**을 클릭하여 프로젝트를 저장합니다.  
  
## <a name="testing-the-control"></a>컨트롤 테스트  
 컨트롤은 독립 실행형 프로젝트가 아니며 컨테이너에서 호스팅해야 합니다. 컨트롤의 런타임 동작을 테스트하고 **UserControl 테스트 컨테이너**로 해당 속성을 실행합니다. 자세한 내용은 [방법: UserControl의 런타임 동작 테스트](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)를 참조하세요.  
  
#### <a name="to-test-your-control"></a>컨트롤을 테스트하려면  
  
1.  F5 키를 눌러 프로젝트를 빌드하고 **UserControl 테스트 컨테이너**에서 컨트롤을 실행합니다.  
  
2.  테스트 컨테이너의 속성 눈금에서 `ClockBackColor` 속성을 선택한 후 드롭다운 화살표를 클릭하여 색상표를 표시합니다.  
  
3.  클릭하여 색을 선택합니다.  
  
     컨트롤의 배경색이 선택한 색으로 바뀝니다.  
  
4.  유사한 이벤트 시퀀스를 사용하여 `ClockForeColor` 속성이 예상대로 작동하는지 확인합니다.  
  
5.  **닫기**를 클릭하여 **UserControl 테스트 컨테이너**를 닫습니다.  
  
     이 섹션과 이전 섹션에서는 구성 요소 및 Windows 컨트롤을 코드와 결합하고 패키징하여 복합 컨트롤 형태로 사용자 지정 기능을 제공하는 방법을 살펴보았습니다. 복합 컨트롤에 속성을 노출하고 완료한 후에는 컨트롤을 테스트하는 방법도 알아보았습니다. 다음 섹션에서는 `ctlClock`을 기본으로 사용하여 상속된 복합 컨트롤을 생성하는 방법에 대해 알아봅니다.  
  
## <a name="inheriting-from-a-composite-control"></a>복합 컨트롤에서 상속  
 이전 섹션에서는 Windows 컨트롤, 구성 요소 및 코드를 재사용 가능한 복합 컨트롤에 결합하는 방법을 알아보았습니다. 이제 복합 컨트롤을 다른 컨트롤을 작성하기 위한 기본으로 활용할 수 있습니다. 기본 클래스에서 클래스를 파생시키는 과정을 *상속*이라고 합니다. 이 섹션에서는 `ctlAlarmClock`이라는 복합 컨트롤을 만듭니다. 이 컨트롤은 부모 컨트롤인 `ctlClock`에서 파생됩니다. 부모 메서드를 재정의하고 새 메서드 및 속성을 추가하여 `ctlClock`의 기능을 확장하는 방법을 알아보겠습니다.  
  
 상속된 컨트롤을 만드는 첫 번째 단계는 부모에서 파생시키는 것입니다. 이 작업은 속성, 메서드 및 부모 컨트롤의 그래픽 특성을 모두 포함하는 새 컨트롤을 만들지만 신규 또는 수정된 기능 추가를 위한 기본으로도 활용할 수 있습니다.  
  
#### <a name="to-create-the-inherited-control"></a>상속된 컨트롤을 만들려면  
  
1.  솔루션 탐색기에서 **ctlClockLib**를 마우스 오른쪽 단추로 클릭하고 **추가**를 가리킨 다음 **사용자 컨트롤**을 클릭합니다.  
  
     **새 항목 추가** 대화 상자가 열립니다.  
  
2.  **상속된 사용자 정의 컨트롤** 템플릿을 선택합니다.  
  
3.  **이름** 상자에 `ctlAlarmClock.vb`를 입력한 다음 **추가**를 클릭합니다.  
  
     **상속 선택** 대화 상자가 나타납니다.  
  
4.  **구성 요소 이름** 아래에서 **ctlClock**을 두 번 클릭합니다.  
  
5.  솔루션 탐색기에서 현재 프로젝트를 찾아봅니다.  
  
    > [!NOTE]
    >  **ctlAlarmClock.vb**라는 파일이 현재 프로젝트에 추가되었습니다.  
  
### <a name="adding-the-alarm-properties"></a>경보 속성 추가  
 속성은 복합 컨트롤에 추가된 것과 같은 방식으로 상속된 컨트롤에 추가됩니다. 이제 속성 선언 구문을 사용하여 컨트롤에 두 가지 속성, 즉 경보가 꺼지는 날짜와 시간 값을 저장하는 `AlarmTime`과 경보가 설정되는지 여부를 나타내는 `AlarmSet`을 추가합니다.  
  
##### <a name="to-add-properties-to-your-composite-control"></a>복합 컨트롤에 속성을 추가하려면  
  
1.  솔루션 탐색기에서 **ctlAlarmClock**을 마우스 오른쪽 단추로 클릭한 후 **코드 보기**를 클릭합니다.  
  
2.  `Public Class ctlAlarmClock`으로 나타나는 ctlAlarmClock 컨트롤에 대한 클래스 선언을 찾습니다.  클래스 선언에서 다음 코드를 삽입합니다.  
  
    ```vb  
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
  
### <a name="adding-to-the-graphical-interface-of-the-control"></a>컨트롤의 그래픽 인터페이스에 추가  
 상속된 컨트롤에는 상속 원본 컨트롤과 동일한 시각적 인터페이스가 있습니다. 부모 컨트롤과 동일한 구성 요소 컨트롤을 소유하지만, 구체적으로 노출되지 않는 한, 구성 요소 컨트롤의 속성을 사용할 수 없습니다. 복합 컨트롤에 추가하는 것과 같은 방법으로 상속된 복합 컨트롤의 그래픽 인터페이스에 추가할 수 있습니다. 알람 시계의 시각적 인터페이스에 계속 추가하려면 경보가 울릴 때 깜박거리는 레이블 컨트롤을 추가합니다.  
  
##### <a name="to-add-the-label-control"></a>레이블 컨트롤을 추가하려면  
  
1.  솔루션 탐색기에서 **ctlAlarmClock**을 마우스 오른쪽 단추로 클릭한 후 **뷰 디자이너**를 클릭합니다.  
  
     `ctlAlarmClock`에 대한 디자이너가 주 창에 열립니다.  
  
2.  `lblDisplay`(컨트롤의 표시 부분)를 클릭하고 속성 창을 확인합니다.  
  
    > [!NOTE]
    >  모든 속성이 표시되는 동안 흐리게 표시됩니다. 이것은 이러한 속성이 `lblDisplay`의 기본 속성이며 속성 창에서 수정하거나 액세스할 수 없음을 나타냅니다. 기본적으로 복합 컨트롤에 포함된 컨트롤은 `Private`이며 해당 속성은 어떤 방법으로도 액세스할 수 없습니다.  
  
    > [!NOTE]
    >  복합 컨트롤의 후속 사용자가 내부 컨트롤에 액세스할 수 있도록 하려면 이를 `Public` 또는 `Protected`로 선언합니다. 이렇게 하면 적절한 코드를 사용하여 복합 컨트롤 내에 포함된 컨트롤의 속성을 설정 및 수정할 수 있습니다.  
  
3.  추가 <xref:System.Windows.Forms.Label> 복합 컨트롤을 제어 합니다.  
  
4.  마우스를 사용 하 여 끌어는 <xref:System.Windows.Forms.Label> 는 표시 상자의 바로 아래에 있는 컨트롤입니다. 속성 창에서 다음 속성을 설정합니다.  
  
    |속성|설정|  
    |--------------|-------------|  
    |**이름**|`lblAlarm`|  
    |**텍스트**|**Alarm!**|  
    |**TextAlign**|`MiddleCenter`|  
    |**Visible**|`False`|  
  
### <a name="adding-the-alarm-functionality"></a>경보 기능 추가  
 이전 프로시저에서는 복합 컨트롤에서 경보 기능을 설정하는 속성 및 컨트롤을 추가했습니다. 이 프로시저에서는 현재 시간을 경보 시간과 비교하여 같으면 알람을 울리고 깜박이는 코드를 추가합니다. `ctlClock`의 `Timer1_Tick` 메소드를 재정의하고 코드를 더 추가하여 `ctlClock`의 모든 고유 기능을 유지하면서 `ctlAlarmClock`의 기능을 확장합니다.  
  
##### <a name="to-override-the-timer1tick-method-of-ctlclock"></a>ctlClock의 Timer1_Tick 메서드를 재정의하려면  
  
1.  솔루션 탐색기에서 **ctlAlarmClock.vb**를 마우스 오른쪽 단추로 클릭한 후 **코드 보기**를 클릭합니다.  
  
2.  `Private blnAlarmSet As Boolean` 문을 찾습니다. 바로 아래에서 다음 문을 추가합니다.  
  
    ```vb  
    Dim blnColorTicker as Boolean  
    ```  
  
3.  페이지 하단에서 `End Class` 문을 찾습니다. `End Class` 문 바로 앞에 다음 코드를 추가합니다.  
  
    ```vb  
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
  
     이 코드를 추가하려면 여러 작업을 수행할 수 있습니다. `Overrides` 문은 기본 컨트롤에서 상속된 메서드 대신, 이 메서드를 사용하도록 컨트롤에 지시합니다. 이 메서드가 호출되면 `MyBase.Timer1_Tick` 문을 호출하여 이를 재정의하는 메서드를 호출하여 원래 컨트롤에 통합된 모든 기능이 이 컨트롤에서 재현되도록 합니다. 그런 다음 경보 기능을 통합하는 추가 코드를 실행합니다. 경보가 발생하면 깜박이는 레이블 컨트롤이 나타나고 신호음이 울립니다.  
  
    > [!NOTE]
    >  상속된 이벤트 처리기를 재정의하므로 `Handles` 키워드로 이벤트를 지정할 필요가 없습니다. 이벤트가 이미 후크되었습니다. 재정의하는 모든 내용은 처리기의 구현입니다.  
  
     알람 시계 컨트롤이 거의 완료되었습니다. 이제 해제하는 방법을 구현하는 것만 남았습니다. 이를 위해서는 `lblAlarm_Click` 메서드에 코드를 추가합니다.  
  
##### <a name="to-implement-the-shutoff-method"></a>shutoff 메서드를 구현하려면  
  
1.  솔루션 탐색기에서 **ctlAlarmClock.vb**를 마우스 오른쪽 단추로 클릭한 후 **뷰 디자이너**를 클릭합니다.  
  
2.  디자이너에서 **lblAlarm**을 두 번 클릭합니다. **코드 편집기**에 `Private Sub lblAlarm_Click` 행이 열립니다.  
  
3.  이 메서드를 다음 코드와 비슷하도록 수정합니다.  
  
    ```vb  
    Private Sub lblAlarm_Click(ByVal sender As Object, ByVal e As _  
     System.EventArgs) Handles lblAlarm.Click  
        ' Turns off the alarm.  
        AlarmSet = False  
        ' Hides the flashing label.  
        lblAlarm.Visible = False  
    End Sub  
    ```  
  
4.  **파일** 메뉴에서 **모두 저장**을 클릭하여 프로젝트를 저장합니다.  
  
### <a name="using-the-inherited-control-on-a-form"></a>폼에서 상속된 컨트롤 사용  
 기본 클래스 컨트롤 `ctlClock`을 테스트했던 것과 같은 방법으로 상속된 컨트롤을 테스트할 수 있습니다. F5 키를 눌러 프로젝트를 빌드하고 **UserControl 테스트 컨테이너**에서 컨트롤을 실행합니다. 자세한 내용은 [방법: UserControl의 런타임 동작 테스트](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)를 참조하세요.  
  
 사용할 컨트롤을 배치하려면 폼에서 컨트롤을 호스트해야 합니다. 표준 복합 컨트롤과 마찬가지로 상속된 복합 컨트롤은 독립 실행형으로 사용할 수 없으며 폼 또는 다른 컨테이너에서 호스트해야 합니다. `ctlAlarmClock`은 보다 심도 있는 기능을 포함하므로 테스트하려면 추가 코드가 필요합니다. 이 프로시저에서는 `ctlAlarmClock`의 기능을 테스트하는 간단한 프로그램을 작성합니다. `ctlAlarmClock`의 `AlarmTime` 속성을 설정하고 표시하는 코드를 작성하고 고유한 기능을 테스트합니다.  
  
##### <a name="to-build-and-add-your-control-to-a-test-form"></a>컨트롤을 빌드하고 테스트 폼에 추가하려면  
  
1.  솔루션 탐색기에서 **ctlClockLib**를 마우스 오른쪽 단추로 클릭한 후 **빌드**를 클릭합니다.  
  
2.  **파일** 메뉴에서 **추가**를 가리킨 다음 **새 프로젝트**를 클릭합니다.  
  
3.  솔루션에 새 **Windows 응용 프로그램** 프로젝트를 추가하고 이름을 `Test`로 지정합니다.  
  
     **Test** 프로젝트가 솔루션 탐색기에 추가됩니다.  
  
4.  솔루션 탐색기에서 `Test` 프로젝트 노드를 마우스 오른쪽 단추로 클릭한 다음 **참조 추가**를 클릭하면 **참조 추가** 대화 상자가 표시됩니다.  
  
5.  **프로젝트**로 레이블이 지정된 탭을 클릭합니다. **ctlClockLib** 프로젝트가 **프로젝트 이름** 아래에 나열됩니다. **ctlClockLib**을 두 번 클릭하여 테스트 프로젝트에 참조를 추가합니다.  
  
6.  솔루션 탐색기에서 **Test**를 마우스 오른쪽 단추로 클릭한 후 **빌드**를 클릭합니다.  
  
7.  **도구 상자**에서 **ctlClockLib 구성 요소** 노드를 확장합니다.  
  
8.  **ctlAlarmClock**을 두 번 클릭하여 `ctlAlarmClock`의 인스턴스를 폼에 추가합니다.  
  
9. 에 **도구 상자**을 찾아서 두 번 클릭 **DateTimePicker** 추가 하는 <xref:System.Windows.Forms.DateTimePicker> 양식에 컨트롤을 추가 합니다는 <xref:System.Windows.Forms.Label> 두 번 클릭 하 여 컨트롤 **레이블**.  
  
10. 마우스를 사용하여 폼의 편리한 위치에 컨트롤을 배치합니다.  
  
11. 다음 방식으로 이러한 컨트롤의 속성을 설정합니다.  
  
    |컨트롤|속성|값|  
    |-------------|--------------|-----------|  
    |`label1`|**텍스트**|`(blank space)`|  
    ||**이름**|`lblTest`|  
    |`dateTimePicker1`|**이름**|`dtpTest`|  
    ||**Format**|<xref:System.Windows.Forms.DateTimePickerFormat.Time>|  
  
12. 디자이너에서 **dtpTest**를 두 번 클릭합니다.  
  
     **코드 편집기**에 `Private Sub dtpTest_ValueChanged`가 열립니다.  
  
13. 다음과 비슷하도록 코드를 수정합니다.  
  
    ```vb  
    Private Sub dtpTest_ValueChanged(ByVal sender As Object, ByVal e As _  
        System.EventArgs) Handles dtpTest.ValueChanged  
        ctlAlarmClock1.AlarmTime = dtpTest.Value  
        ctlAlarmClock1.AlarmSet = True  
        lblTest.Text = "Alarm Time is " & Format(ctlAlarmClock1.AlarmTime, _  
            "hh:mm")  
    End Sub  
    ```  
  
14. 솔루션 탐색기에서 **Test**를 마우스 오른쪽 단추로 클릭한 다음 **시작 프로젝트로 설정**을 클릭합니다.  
  
15. **디버그** 메뉴에서 **디버깅 시작**을 클릭합니다.  
  
     테스트 프로그램이 시작됩니다. 현재 시간에서 업데이트 되는 `ctlAlarmClock` 컨트롤 및 시작 시간에 표시 되는지는 <xref:System.Windows.Forms.DateTimePicker> 제어 합니다.  
  
16. 클릭는 <xref:System.Windows.Forms.DateTimePicker> 시간의 분 표시 됩니다.  
  
17. 키보드를 사용하여 `ctlAlarmClock`으로 표시된 현재 시간보다 1분 큰 값(분)을 설정합니다.  
  
     경보 설정 시간이 `lblTest`에 표시됩니다. 표시된 시간이 경보 설정 시간에 도달할 때까지 기다립니다. 표시된 시간이 경보 설정 시간에 도달하면 신호음이 울리고 `lblAlarm`이 깜박입니다.  
  
18. `lblAlarm`을 클릭하여 경보를 해제합니다. 이제 경보를 다시 설정할 수 있습니다.  
  
     이 연습에서 여러 가지 주요 개념을 살펴보았습니다. 컨트롤 및 구성 요소를 복합 컨트롤 컨테이너에 결합하여 복합 컨트롤을 만드는 방법을 배웠습니다. 컨트롤에 속성을 추가하고 사용자 지정 기능을 작성하는 코드를 작성하는 방법도 알아봤습니다. 마지막 섹션에서는 상속성을 통해 지정된 복합 컨트롤의 기능을 확장하고 해당 메서드를 재정의하여 호스트 메서드의 기능을 수정해보았습니다.  
  
## <a name="see-also"></a>참고 항목  
 [사용자 지정 컨트롤의 종류](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 [방법: 복합 컨트롤 작성](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md)  
 [방법: 도구 상자 항목 선택 대화 상자에 컨트롤 표시](../../../../docs/framework/winforms/controls/how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)  
 [구성 요소 제작 연습](http://msdn.microsoft.com/library/c414cca9-2489-4208-8b38-954586d91c13)
