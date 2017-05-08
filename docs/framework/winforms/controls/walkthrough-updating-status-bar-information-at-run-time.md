---
title: "연습: 런타임에 상태 표시줄 정보 업데이트 | Microsoft Docs"
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
  - "패널, 상태 표시줄 새로 고침"
  - "상태 표시줄, 창 새로 고침"
  - "상태 표시줄, 런타임에 업데이트"
  - "StatusBar 컨트롤[Windows Forms], 창 새로 고침"
ms.assetid: cc2abb06-c082-49f7-a5a3-2fd1bbcb58d1
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# 연습: 런타임에 상태 표시줄 정보 업데이트
> [!IMPORTANT]
>  <xref:System.Windows.Forms.StatusStrip> 및 <xref:System.Windows.Forms.ToolStripStatusLabel> 컨트롤은 <xref:System.Windows.Forms.StatusBar> 및 <xref:System.Windows.Forms.StatusBarPanel> 컨트롤에 새로운 기능이 추가된 것으로, 이전 컨트롤을 대체합니다. 그러나 이전 버전과의 호환성 및 앞으로의 사용 가능성을 고려하여 <xref:System.Windows.Forms.StatusBar> 및 <xref:System.Windows.Forms.StatusBarPanel> 컨트롤을 유지하도록 선택할 수 있습니다.  
  
 런타임에 응용 프로그램 상태가 변경되거나 기타 사용자 상호 작용이 발생하면 상태 표시줄 패널의 내용을 런타임에 동적으로 업데이트하라는 메시지가 나타나는 경우가 많습니다.  이런 방식은 대개 Caps Lock, Num Lock 및 Scroll Lock 같은 키가 눌려 있음을 사용자에게 알리거나 편리하게 참조할 수 있도록 날짜나 시계를 표시하는 데 사용됩니다.  
  
 다음 예제에서는 <xref:System.Windows.Forms.StatusBarPanel> 클래스의 인스턴스를 사용하여 시계를 호스팅합니다.  
  
### 업데이트를 위해 상태 표시줄을 준비하려면  
  
1.  Windows Form을 새로 만듭니다.  
  
2.  폼에 <xref:System.Windows.Forms.StatusBar> 컨트롤을 추가합니다.  자세한 내용은 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)를 참조하십시오.  
  
3.  <xref:System.Windows.Forms.StatusBar> 컨트롤에 상태 표시줄 패널을 추가합니다.  자세한 내용은 [방법: StatusBar 컨트롤에 패널 추가](../../../../docs/framework/winforms/controls/how-to-add-panels-to-a-statusbar-control.md)를 참조하십시오.  
  
4.  폼에 추가한 <xref:System.Windows.Forms.StatusBar> 컨트롤에 대해 <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> 속성을 `true`로 설정합니다.  
  
5.  폼에 Windows Forms <xref:System.Windows.Forms.Timer> 구성 요소를 추가합니다.  
  
    > [!NOTE]
    >  Windows Forms <xref:System.Windows.Forms.Timer?displayProperty=fullName> 구성 요소는 Windows Forms 환경에 맞도록 디자인되었습니다.  서버 환경에 적합한 타이머가 필요한 경우에는 [Introduction to Server\-Based Timers](http://msdn.microsoft.com/ko-kr/adc0bc0a-a519-4812-bafc-fb9d1a5801fc)를 참조하십시오.  
  
6.  <xref:System.Windows.Forms.Timer.Enabled%2A> 속성을 `true`으로 설정합니다.  
  
7.  <xref:System.Windows.Forms.Timer>의 <xref:System.Windows.Forms.Timer.Interval%2A> 속성을 30000으로 설정합니다.  
  
    > [!NOTE]
    >  정확한 시간을 반영하여 시간이 표시되도록 하기 위해 <xref:System.Windows.Forms.Timer> 구성 요소의 <xref:System.Windows.Forms.Timer.Interval%2A> 속성은 30초\(30,000밀리초\)로 설정됩니다.  
  
### 상태 표시줄을 업데이트하도록 타이머를 구현하려면  
  
1.  <xref:System.Windows.Forms.StatusBar> 컨트롤의 패널을 업데이트하는 아래의 코드를 <xref:System.Windows.Forms.Timer> 구성 요소의 이벤트 처리기에 삽입합니다.  
  
    ```vb  
    Private Sub Timer1_Tick(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Timer1.Tick  
       StatusBar1.Panels(0).Text = Now.ToShortTimeString  
    End Sub  
  
    ```  
  
    ```csharp  
    private void timer1_Tick(object sender, System.EventArgs e)  
    {  
       statusBar1.Panels[0].Text = DateTime.Now.ToShortTimeString();  
    }  
  
    ```  
  
    ```cpp  
    private:  
      System::Void timer1_Tick(System::Object ^ sender,  
        System::EventArgs ^ e)  
      {  
        statusBar1->Panels[0]->Text =  
          DateTime::Now.ToShortTimeString();  
      }  
    ```  
  
     이제 응용 프로그램을 실행하면 상태 표시줄 패널에서 시계가 작동하는 것을 볼 수 있습니다.  
  
### 응용 프로그램을 테스트하려면  
  
1.  응용 프로그램을 디버깅한 다음 F5 키를 눌러 실행합니다.  디버깅에 대한 자세한 내용은 [Visual Studio의 디버깅](../Topic/Debugging%20in%20Visual%20Studio.md)을 참조하십시오.  
  
    > [!NOTE]
    >  상태 표시줄에 시계가 표시되려면 약 30초가 걸립니다.  이 시간 동안 시계는 최대한 정확하게 맞춰집니다.  반대로, 시계를 더 빨리 나타나게 하려면 위 절차의 7단계에서 설정한 <xref:System.Windows.Forms.Timer.Interval%2A> 속성 값을 줄이면 됩니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.StatusBar>   
 <xref:System.Windows.Forms.ToolStripStatusLabel>   
 [방법: StatusBar 컨트롤에 패널 추가](../../../../docs/framework/winforms/controls/how-to-add-panels-to-a-statusbar-control.md)   
 [방법: Windows Forms StatusBar 컨트롤에서 클릭한 패널 확인](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)   
 [StatusBar 컨트롤 개요](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)