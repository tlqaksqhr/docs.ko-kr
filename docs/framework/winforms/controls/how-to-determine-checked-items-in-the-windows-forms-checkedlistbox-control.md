---
title: "방법: Windows Forms CheckedListBox 컨트롤에서 선택된 항목 확인 | Microsoft Docs"
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
  - "확인란, 선택된 항목 확인"
  - "CheckedListBox 컨트롤[Windows Forms], 선택된 항목 확인"
ms.assetid: 178b477d-27c9-489c-8914-44a9623a4d41
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: Windows Forms CheckedListBox 컨트롤에서 선택된 항목 확인
Windows Forms <xref:System.Windows.Forms.CheckedListBox> 컨트롤에서 데이터를 표시할 때는 <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> 속성에 저장된 컬렉션을 순환하거나 <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> 메서드를 사용하여 목록을 조사함으로써 선택된 항목을 확인할 수 있습니다.  <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> 메서드는 항목 인덱스 번호를 인수로 취하여 `true` 또는 `false`를 반환합니다.  기대와 달리, <xref:System.Windows.Forms.ListBox.SelectedItems%2A> 및 <xref:System.Windows.Forms.ListBox.SelectedIndices%2A> 속성은 선택된 항목이 아니라, 강조 표시된 항목을 확인합니다.  
  
### CheckedListBox 컨트롤에서 선택된 항목을 확인하려면  
  
1.  <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> 컬렉션은 0부터 시작하므로 0에서 시작하여 해당 컬렉션을 단계적으로 수행합니다.  이 메서드는 전체 목록이 아니라 선택된 항목의 목록에서 해당 항목 번호를 알려 줍니다.  따라서 목록의 첫 번째 항목은 선택되어 있지 않고 두 번째 항목이 선택되어 있는 경우 아래 코드는 "Checked Item 1 \= MyListItem2"와 같은 텍스트를 표시합니다.  
  
    ```vb  
    ' Determine if there are any items checked.  
    If CheckedListBox1.CheckedItems.Count <> 0 Then  
       ' If so, loop through all checked items and print results.  
       Dim x As Integer  
       Dim s As String = ""  
       For x = 0 To CheckedListBox1.CheckedItems.Count - 1  
          s = s & "Checked Item " & (x + 1).ToString & " = " & CheckedListBox1.CheckedItems(x).ToString & ControlChars.CrLf  
       Next x  
       MessageBox.Show(s)  
    End If  
  
    ```  
  
    ```csharp  
    // Determine if there are any items checked.  
    if(checkedListBox1.CheckedItems.Count != 0)  
    {  
       // If so, loop through all checked items and print results.  
       string s = "";  
       for(int x = 0; x <= checkedListBox1.CheckedItems.Count - 1 ; x++)  
       {  
          s = s + "Checked Item " + (x+1).ToString() + " = " + checkedListBox1.CheckedItems[x].ToString() + "\n";  
       }  
    MessageBox.Show (s);  
    }  
  
    ```  
  
    ```cpp  
    // Determine if there are any items checked.  
    if(checkedListBox1->CheckedItems->Count != 0)  
    {  
       // If so, loop through all checked items and print results.  
       String ^ s = "";  
       for(int x = 0; x <= checkedListBox1->CheckedItems->Count - 1; x++)  
       {  
          s = String::Concat(s, "Checked Item ", (x+1).ToString(),  
             " = ", checkedListBox1->CheckedItems[x]->ToString(),  
             "\n");  
       }  
       MessageBox::Show(s);  
    }  
    ```  
  
     \-또는\-  
  
2.  <xref:System.Windows.Forms.CheckedListBox.Items%2A> 컬렉션은 0부터 시작하므로 0에서 시작하여 해당 컬렉션을 단계적으로 수행하며 각 항목에 대한 <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> 메서드를 호출합니다.  이 메서드는 사용자에게 전체 목록 상의 항목 번호를 제공합니다. 따라서 목록의 첫 번째 항목이 선택되어 있지 않고 두 번째 항목이 선택되어 있는 경우 해당 메서드는 "Item 2 \= MyListItem2"와 같은 텍스트를 표시합니다.  
  
    ```vb  
    Dim i As Integer  
    Dim s As String  
    s = "Checked Items:" & ControlChars.CrLf  
    For i = 0 To (CheckedListBox1.Items.Count - 1)  
       If CheckedListBox1.GetItemChecked(i) = True Then  
          s = s & "Item " & (i + 1).ToString & " = " & CheckedListBox1.Items(i).ToString & ControlChars.CrLf  
       End If  
    Next  
    MessageBox.Show(s)  
  
    ```  
  
    ```csharp  
    int i;  
    string s;   
    s = "Checked items:\n" ;  
    for (i = 0; i <= (checkedListBox1.Items.Count-1); i++)  
    {  
       if (checkedListBox1.GetItemChecked(i))  
       {  
          s = s + "Item " + (i+1).ToString() + " = " + checkedListBox1.Items[i].ToString() + "\n";  
       }  
    }  
    MessageBox.Show (s);  
  
    ```  
  
    ```cpp  
    int i;  
    String ^ s;   
    s = "Checked items:\n" ;  
    for (i = 0; i <= (checkedListBox1->Items->Count-1); i++)  
    {  
       if (checkedListBox1->GetItemChecked(i))  
       {  
          s = String::Concat(s, "Item ", (i+1).ToString(), " = ",  
             checkedListBox1->Item[i]->ToString(), "\n");  
       }  
    }  
    MessageBox::Show(s);  
    ```  
  
## 참고 항목  
 [옵션 목록 표시에 사용하는 Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)