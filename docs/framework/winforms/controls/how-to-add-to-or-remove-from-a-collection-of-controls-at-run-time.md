---
title: "방법: 런타임에 컨트롤 컬렉션에서 컨트롤 추가 또는 제거 | Microsoft Docs"
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
  - "컬렉션, 항목 추가"
  - "컨트롤[Windows Forms], 컬렉션을 사용한 추가"
  - "컨트롤[Windows Forms], 컬렉션을 사용한 제거"
  - "컨트롤 컬렉션"
  - "런타임, 컨트롤 추가"
  - "런타임, 컨트롤 제거"
ms.assetid: 771bf895-3d5f-469b-a324-3528f343657e
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: 런타임에 컨트롤 컬렉션에서 컨트롤 추가 또는 제거
응용 프로그램을 개발할 때는 일반적으로 폼의 컨테이너 컨트롤\(예: <xref:System.Windows.Forms.Panel>이나 <xref:System.Windows.Forms.GroupBox> 컨트롤 또는 폼 자체\)에 컨트롤을 추가하거나 제거하는 작업을 하게 됩니다.  디자인 타임에는 컨트롤을 패널이나 그룹 상자로 직접 끌어 올 수 있으며,  런타임에는 이러한 컨트롤이 자체 컨트롤에 배치된 컨트롤을 추적하는 `Controls` 컬렉션을 관리합니다.  
  
> [!NOTE]
>  다음 코드 예제는 자체 컨트롤에 배치된 컨트롤의 컬렉션을 관리하는 모든 컨트롤에 적용됩니다.  
  
### 프로그래밍 방식으로 컬렉션에 컨트롤을 추가하려면  
  
1.  추가할 컨트롤의 인스턴스를 만듭니다.  
  
2.  새 컨트롤의 속성을 설정합니다.  
  
3.  컨트롤을 부모 컨트롤의 `Controls` 컬렉션에 추가합니다.  
  
     다음 코드 예제에서는 <xref:System.Windows.Forms.Button> 컨트롤의 인스턴스를 만드는 방법을 보여 줍니다.  이 예제를 실행하려면 폼에 <xref:System.Windows.Forms.Panel> 컨트롤이 있어야 하며 만들어질 단추에 대한 이벤트 처리 메서드인 `NewPanelButton_Click`이 이미 있어야 합니다.  
  
    ```vb  
    Public NewPanelButton As New Button()  
  
    Public Sub AddNewControl()  
       ' The Add method will accept as a parameter any object that derives  
       ' from the Control class. In this case, it is a Button control.  
       Panel1.Controls.Add(NewPanelButton)  
       ' The event handler indicated for the Click event in the code   
       ' below is used as an example. Substite the appropriate event  
       ' handler for your application.  
       AddHandler NewPanelButton.Click, AddressOf NewPanelButton_Click  
    End Sub  
  
    ```  
  
    ```csharp  
    public Button newPanelButton = new Button();  
  
    public void addNewControl()  
    {   
       // The Add method will accept as a parameter any object that derives  
       // from the Control class. In this case, it is a Button control.  
       panel1.Controls.Add(newPanelButton);  
       // The event handler indicated for the Click event in the code   
       // below is used as an example. Substite the appropriate event  
       // handler for your application.  
       this.newPanelButton.Click += new System.EventHandler(this. NewPanelButton_Click);  
    }  
    ```  
  
### 프로그래밍 방식으로 컬렉션에서 컨트롤을 제거하려면  
  
1.  이벤트에서 이벤트 처리기를 제거합니다.  [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]에서는 [RemoveHandler Statement](../../../../ocs/visual-basic/language-reference/statements/removehandler-statement.md) 키워드를 사용하고 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]에서는 [\-\= 연산자](../Topic/-=%20Operator%20\(C%23%20Reference\)2.md)를 사용합니다.  
  
2.  `Remove` 메서드를 사용하여 패널의 `Controls` 컬렉션에서 해당 컨트롤을 삭제합니다.  
  
3.  <xref:System.Windows.Forms.Control.Dispose%2A> 메서드를 호출하여 해당 컨트롤에서 사용하던 모든 리소스를 해제합니다.  
  
    ```vb  
    Public Sub RemoveControl()  
    ' NOTE: The code below uses the instance of   
    ' the button (NewPanelButton) from the previous example.  
       If Panel1.Controls.Contains(NewPanelButton) Then  
          RemoveHandler NewPanelButton.Click, AddressOf _   
             NewPanelButton_Click  
          Panel1.Controls.Remove(NewPanelButton)  
          NewPanelButton.Dispose()  
       End If  
    End Sub  
  
    ```  
  
    ```csharp  
    private void removeControl(object sender, System.EventArgs e)  
    {  
    // NOTE: The code below uses the instance of   
    // the button (newPanelButton) from the previous example.  
       if(panel1.Controls.Contains(newPanelButton))  
       {  
          this.newPanelButton.Click -= new System.EventHandler(this.   
             NewPanelButton_Click);  
          panel1.Controls.Remove(newPanelButton);  
          newPanelButton.Dispose();  
       }  
    }  
    ```  
  
## 참고 항목  
 <xref:System.Windows.Forms.Panel>   
 [Panel 컨트롤](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)