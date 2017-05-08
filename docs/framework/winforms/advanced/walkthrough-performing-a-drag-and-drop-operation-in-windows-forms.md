---
title: "연습: Windows Forms에서 끌어서 놓기 작업 수행 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "끌어서 놓기, Windows Forms"
  - "Windows Forms, 끌어서 놓기 작업"
ms.assetid: eb66f6bf-4a7d-4c2d-b276-40fefb2d3b6c
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 연습: Windows Forms에서 끌어서 놓기 작업 수행
Windows 기반 응용 프로그램 내에서 끌어서 놓기 작업을 수행하려면 일련의 이벤트를 처리해야 하는데 그 중에서도 가장 두드러진 이벤트는 <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave> 및 <xref:System.Windows.Forms.Control.DragDrop> 이벤트입니다.  이러한 이벤트의 이벤트 인수에 있는 정보를 사용하여 끌어서 놓기 작업을 쉽게 구현할 수 있습니다.  
  
## 데이터 끌기  
 모든 끌어서 놓기 작업은 끌기에서 시작됩니다.  끌기가 시작될 때 데이터를 수집하는 기능은 <xref:System.Windows.Forms.Control.DoDragDrop%2A> 메서드에서 구현합니다.  
  
 다음 예제에서는 <xref:System.Windows.Forms.Control.MouseDown> 이벤트가 가장 직관적인 방법\(대부분의 끌어서 놓기 작업은 마우스 단추를 누름으로써 시작\)이므로 이 이벤트를 끌기 작업의 시작 방법으로 사용합니다.  하지만 모든 이벤트를 끌어서 놓기 프로시저의 시작 방법으로 사용할 수 있습니다.  
  
> [!NOTE]
>  특정 컨트롤에는 사용자 지정 끌기 관련 이벤트가 있습니다.  예를 들어, <xref:System.Windows.Forms.ListView> 및 <xref:System.Windows.Forms.TreeView> 컨트롤에는 <xref:System.Windows.Forms.TreeView.ItemDrag> 이벤트가 있습니다.  
  
#### 끌기 작업을 시작하려면  
  
1.  에 있는 <xref:System.Windows.Forms.Control.MouseDown>끌기가 시작 됩니다, 컨트롤 사용에 대 한 이벤트는 `DoDragDrop` 끌 수 데이터를 설정 하는 방법 및 허용 된 효과가 끌기 갖지 것입니다.  자세한 내용은 <xref:System.Windows.Forms.DragEventArgs.Data%2A> 및 <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>를 참조하십시오.  
  
     다음 예제에서는 끌기 작업을 시작하는 방법을 보여 줍니다.  끌기가 시작되는 컨트롤은 <xref:System.Windows.Forms.Button> 컨트롤이며 끌고 있는 데이터는 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Text%2A> 속성을 나타내는 문자열이며 허용되는 효과는 복사 또는 이동입니다.  
  
    ```vb  
    Private Sub Button1_MouseDown(ByVal sender As Object, ByVal e As System.Windows.Forms.MouseEventArgs) Handles Button1.MouseDown  
       Button1.DoDragDrop(Button1.Text, DragDropEffects.Copy Or DragDropEffects.Move)  
    End Sub  
  
    ```  
  
    ```csharp  
    private void button1_MouseDown(object sender,   
    System.Windows.Forms.MouseEventArgs e)  
    {  
       button1.DoDragDrop(button1.Text, DragDropEffects.Copy |   
          DragDropEffects.Move);  
    }  
  
    ```  
  
    > [!NOTE]
    >  모든 데이터를 `DoDragDrop` 메서드의 매개 변수로 사용할 수 있습니다. 위의 예제에서는 해당 속성이 끌기 작업할 <xref:System.Windows.Forms.Button> 컨트롤의 위치와 관련되어 있기 때문에 하드 코딩된 값이나 데이터 집합에서 검색된 데이터를 사용하지 않고 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Text%2A> 속성을 사용했습니다.  끌어서 놓기 작업을 Windows 기반 응용 프로그램에 결합시킬 때는 이 점을 기억해 두시기 바랍니다.  
  
 끌기 작업이 적용 중인 동안 <xref:System.Windows.Forms.Control.QueryContinueDrag> 이벤트를 처리할 수 있습니다. 이 이벤트는 시스템에 "권한을 요청"하여 끌기 작업을 계속할 수 있도록 합니다.  이 메서드를 처리할 때는 커서가 트리 뷰를 가리킬 때 <xref:System.Windows.Forms.TreeView> 컨트롤에 있는 <xref:System.Windows.Forms.TreeNode>를 확장하는 것처럼 끌기 작업의 효과를 나타내는 메서드를 호출하는 것이 좋습니다.  
  
## 데이터 놓기  
 Windows Form 또는 컨트롤의 위치에서 데이터를 끌기 시작했으면 당연히 다른 위치에 놓으려고 할 것입니다.  데이터를 놓을 수 있도록 올바로 구성된 폼 또는 컨트롤의 영역 위로 가면 커서가 변경됩니다.  <xref:System.Windows.Forms.Control.AllowDrop%2A> 속성을 설정하고 <xref:System.Windows.Forms.Control.DragEnter> 및 <xref:System.Windows.Forms.Control.DragDrop> 이벤트를 처리함으로써 Windows Form 또는 컨트롤 안에 있는 영역에서 놓여지는 데이터를 받아들이도록 만들 수 있습니다.  
  
#### 놓기를 수행하려면  
  
1.  <xref:System.Windows.Forms.Control.AllowDrop%2A> 속성을 true로 설정합니다.  
  
2.  놓기가 발생하는 컨트롤의 `DragEnter` 이벤트에서 끌고 있는 데이터의 형식이 적합한지\(이 경우 <xref:System.Windows.Forms.Control.Text%2A>\) 확인합니다.  그러면 코드에서는 마우스를 놓을 때 나타나는 효과를 <xref:System.Windows.Forms.DragDropEffects> 열거형 값으로 설정합니다.  자세한 내용은 <xref:System.Windows.Forms.DragEventArgs.Effect%2A>를 참조하십시오.  
  
    ```vb  
    Private Sub TextBox1_DragEnter(ByVal sender As Object, ByVal e As System.Windows.Forms.DragEventArgs) Handles TextBox1.DragEnter  
       If (e.Data.GetDataPresent(DataFormats.Text)) Then  
         e.Effect = DragDropEffects.Copy  
       Else  
         e.Effect = DragDropEffects.None  
       End If  
    End Sub  
  
    ```  
  
    ```csharp  
    private void textBox1_DragEnter(object sender,   
    System.Windows.Forms.DragEventArgs e)  
    {  
       if (e.Data.GetDataPresent(DataFormats.Text))   
          e.Effect = DragDropEffects.Copy;  
       else  
          e.Effect = DragDropEffects.None;  
    }  
  
    ```  
  
    > [!NOTE]
    >  고유한 개체를 <xref:System.Windows.Forms.DataObject.SetData%2A> 메서드의 <xref:System.Object> 매개 변수로 지정하여 사용자 고유의 <xref:System.Windows.Forms.DataFormats>를 정의할 수 있습니다.  이 작업을 수행할 때 지정한 개체는 serialize할 수 있어야 합니다.  자세한 내용은 [ISerializable 인터페이스](frlrfSystemRuntimeSerializationISerializableClassTopic)를 참조하십시오.  
  
3.  놓기가 발생하는 컨트롤의 <xref:System.Windows.Forms.Control.DragDrop> 이벤트에서 <xref:System.Windows.Forms.DataObject.GetData%2A> 메서드를 사용하여 끌어 오는 데이터를 검색합니다.  자세한 내용은 [DtaObject.Data 속성](frlrfSystemSecurityCryptographyXmlDataObjectClassDataTopic)을 참조하십시오.  
  
     아래 예제에서는 <xref:System.Windows.Forms.TextBox> 컨트롤이 놓기가 발생하는 컨트롤입니다.  코드에서는 <xref:System.Windows.Forms.TextBox> 컨트롤의 <xref:System.Windows.Forms.Control.Text%2A> 속성을 끌어 오는 데이터와 같게 설정합니다.  
  
    ```vb  
    Private Sub TextBox1_DragDrop(ByVal sender As Object, ByVal e As System.Windows.Forms.DragEventArgs) Handles TextBox1.DragDrop  
       TextBox1.Text = e.Data.GetData(DataFormats.Text).ToString  
    End Sub  
  
    ```  
  
    ```csharp  
    private void textBox1_DragDrop(object sender,   
    System.Windows.Forms.DragEventArgs e)  
    {  
       textBox1.Text = e.Data.GetData(DataFormats.Text).ToString();  
    }  
  
    ```  
  
    > [!NOTE]
    >  또한 <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> 속성을 사용하여 끌어서 놓기 작업 동안 누른 키에 따라 특정 효과\(예: Ctrl 키를 눌렀을 때는 끌어 온 데이터를 복사하는 것이 표준\)가 발생하도록 할 수 있습니다.  
  
## 참고 항목  
 [방법: 클립보드에 데이터 추가](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)   
 [방법: 클립보드에서 데이터 검색](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)   
 [끌어서 놓기 작업 및 클립보드 지원](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)