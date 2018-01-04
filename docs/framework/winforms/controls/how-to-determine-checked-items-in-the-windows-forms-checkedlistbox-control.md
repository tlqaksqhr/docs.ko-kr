---
title: "방법: Windows Forms CheckedListBox 컨트롤에서 선택된 항목 확인"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- check boxes [Windows Forms], determining checked state
- CheckedListBox control [Windows Forms], determining checked state
ms.assetid: 178b477d-27c9-489c-8914-44a9623a4d41
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 63960740b2fc0cb2c96f9a853480f37857c7901b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-determine-checked-items-in-the-windows-forms-checkedlistbox-control"></a>방법: Windows Forms CheckedListBox 컨트롤에서 선택된 항목 확인
Windows Forms에서 데이터를 표시할 때는 <xref:System.Windows.Forms.CheckedListBox> 컨트롤을 반복할 수 있습니다 중 하나에 저장 된 컬렉션의 <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> 속성 또는 사용 하 여 목록을 단계별로 <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> 선택한 항목을 결정 하는 메서드. <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> 메서드를 해당 인수로 항목 인덱스 번호를 가져와서 반환 `true` 또는 `false`합니다. 반대로 예상 하는 것을 <xref:System.Windows.Forms.ListBox.SelectedItems%2A> 및 <xref:System.Windows.Forms.ListBox.SelectedIndices%2A> 속성에서 선택한 항목을 결정 하지 않습니다; 결정 하는 항목 강조 표시 됩니다.  
  
### <a name="to-determine-checked-items-in-a-checkedlistbox-control"></a>CheckedListBox 컨트롤에서 선택한 항목을 확인 하려면  
  
1.  반복은 <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> 컬렉션, 컬렉션은 0부터 시작 하므로 0부터 시작 합니다. 이 메서드는 전체 목록이 아니라 선택 된 항목의 목록에서 항목 번호를 알려 참고 합니다. 아래 코드 같은 텍스트에 표시 되는 목록에서 첫 번째 항목 체크 하지 하는 경우 두 번째 항목이 선택 되는 "선택한 항목 1 = MyListItem2"입니다.  
  
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
  
     - 또는  
  
2.  단계별로 <xref:System.Windows.Forms.CheckedListBox.Items%2A> 컬렉션, 컬렉션은 0부터 시작 하므로 0부터 시작 하 고 호출에서 <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> 각 항목에 대 한 메서드. 이 메서드를 알려 항목 번호 전체 목록에 목록 체크 인 첫 번째 항목이 고 두 번째 항목을 체크를 다음과 같이 표시 됩니다 "항목 2 = MyListItem2"입니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 [옵션 목록 표시에 사용된 Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
