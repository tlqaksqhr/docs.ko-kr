---
title: "방법: Windows Forms StatusBar 컨트롤에서 클릭한 패널 확인 | Microsoft Docs"
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
  - "Panel 컨트롤[Windows Forms], 클릭 확인"
  - "PanelClick 이벤트, 패널 클릭 확인"
  - "패널, 클릭한 패널 확인"
  - "상태 표시줄, 패널 클릭 확인"
  - "StatusBar 컨트롤[Windows Forms], 패널 클릭 이벤트 코딩"
  - "StatusBar 컨트롤[Windows Forms], 패널 클릭 확인"
ms.assetid: d14c6092-04b2-4a07-8ddf-0dd11277ff5f
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# 방법: Windows Forms StatusBar 컨트롤에서 클릭한 패널 확인
> [!IMPORTANT]
>  <xref:System.Windows.Forms.StatusStrip> 및 <xref:System.Windows.Forms.ToolStripStatusLabel> 컨트롤은 <xref:System.Windows.Forms.StatusBar> 및 <xref:System.Windows.Forms.StatusBarPanel> 컨트롤에 새로운 기능이 추가된 것으로, 이전 컨트롤을 대체합니다. 그러나 이전 버전과의 호환성 및 앞으로의 사용 가능성을 고려하여 <xref:System.Windows.Forms.StatusBar> 및 <xref:System.Windows.Forms.StatusBarPanel> 컨트롤을 유지하도록 선택할 수 있습니다.  
  
 사용자 클릭에 응답하도록 [StatusBar 컨트롤](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) 컨트롤을 프로그래밍하려면 <xref:System.Windows.Forms.StatusBar.PanelClick> 이벤트 내에서 case 문을 사용합니다.  이벤트에는 클릭된 <xref:System.Windows.Forms.StatusBarPanel> 개체에 대한 참조를 포함하는 인수인 panel 인수가 있습니다.  클릭한 패널의 인덱스를 이 참조를 통해 확인하고 그에 따라 프로그래밍할 수 있습니다.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.StatusBar> 컨트롤의 <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> 속성이 `true`로 설정되어 있어야 합니다.  
  
### 클릭한 패널을 확인하려면  
  
1.  <xref:System.Windows.Forms.StatusBar.PanelClick> 이벤트 처리기에서 `Select Case`\([!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]\) 문 또는 `switch case`\([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] 또는 [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) 문을 사용하여, 클릭한 패널의 인덱스를 이벤트 인수에서 검사하면 어떤 패널을 클릭했는지 확인할 수 있습니다.  
  
     다음 코드 예제에서는 폼에 <xref:System.Windows.Forms.StatusBar> 컨트롤인 `StatusBar1`과 두 개의<xref:System.Windows.Forms.StatusBarPanel> 개체,`StatusBarPanel1` 및`StatusBarPanel2`가 있어야 합니다.  
  
    ```vb  
    Private Sub StatusBar1_PanelClick(ByVal sender As System.Object, ByVal e As System.Windows.Forms.StatusBarPanelClickEventArgs) Handles StatusBar1.PanelClick  
       Select Case StatusBar1.Panels.IndexOf(e.StatusBarPanel)  
         Case 0  
           MessageBox.Show("You have clicked Panel One.")  
         Case 1  
           MessageBox.Show("You have clicked Panel Two.")  
       End Select  
    End Sub  
  
    ```  
  
    ```csharp  
    private void statusBar1_PanelClick(object sender,   
    System.Windows.Forms.StatusBarPanelClickEventArgs e)  
    {  
       switch (statusBar1.Panels.IndexOf(e.StatusBarPanel))  
       {  
          case 0 :  
             MessageBox.Show("You have clicked Panel One.");  
             break;  
          case 1 :  
             MessageBox.Show("You have clicked Panel Two.");  
             break;  
       }  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void statusBar1_PanelClick(System::Object ^  sender,  
          System::Windows::Forms::StatusBarPanelClickEventArgs ^  e)  
       {  
          switch (statusBar1->Panels->IndexOf(e->StatusBarPanel))  
          {  
             case 0 :  
                MessageBox::Show("You have clicked Panel One.");  
                break;  
             case 1 :  
                MessageBox::Show("You have clicked Panel Two.");  
                break;  
          }  
       }  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) 폼의 생성자에 다음 코드를 배치하여 이벤트 처리기를 등록합니다.  
  
    ```csharp  
    this.statusBar1.PanelClick += new   
       System.Windows.Forms.StatusBarPanelClickEventHandler   
       (this.statusBar1_PanelClick);  
  
    ```  
  
    ```cpp  
    this->statusBar1->PanelClick += gcnew  
       System::Windows::Forms::StatusBarPanelClickEventHandler  
       (this, &Form1::statusBar1_PanelClick);  
    ```  
  
## 참고 항목  
 <xref:System.Windows.Forms.StatusBar>   
 <xref:System.Windows.Forms.ToolStripStatusLabel>   
 [방법: 상태 표시줄 패널의 크기 설정](../../../../docs/framework/winforms/controls/how-to-set-the-size-of-status-bar-panels.md)   
 [연습: 런타임에 상태 표시줄 정보 업데이트](../../../../docs/framework/winforms/controls/walkthrough-updating-status-bar-information-at-run-time.md)   
 [StatusBar 컨트롤 개요](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)