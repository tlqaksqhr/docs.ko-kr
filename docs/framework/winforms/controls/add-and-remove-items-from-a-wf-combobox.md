---
title: "방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤에서 항목 추가 및 제거 | Microsoft Docs"
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
  - "CheckedListBox 컨트롤[Windows Forms], 항목 추가 및 제거"
  - "콤보 상자, 항목 추가"
  - "콤보 상자, 항목 제거"
  - "ComboBox 컨트롤[Windows Forms], 항목 추가 및 제거"
  - "목록 상자, 항목 추가"
  - "목록 상자, 항목 제거"
  - "ListBox 컨트롤[Windows Forms], 항목 추가 및 제거"
ms.assetid: 7224c8d2-4118-443e-ae1e-d7c17d1e69ee
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# 방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤에서 항목 추가 및 제거
Windows Forms 콤보 상자, 목록 상자 또는 확인 목록 상자는 다양한 데이터 소스에 바인딩할 수 있기 때문에 이러한 컨트롤에 항목을 추가할 수 있는 방법은 여러 가지가 있습니다.  그러나 이 항목에서는 가장 간단한 방법을 설명하므로 데이터 바인딩이 필요 없습니다.  표시되는 항목은 일반적으로 문자열이지만 모든 개체를 사용할 수 있습니다.  컨트롤에 표시되는 텍스트는 개체의`ToString` 메서드가 반환하는 값입니다.  
  
### 항목을 추가하려면  
  
1.  `ObjectCollection` 클래스의 `Add` 메서드를 사용하여 목록에 문자열이나 개체를 추가합니다.  컬렉션은`Items` 속성을 사용하여 참조합니다.  
  
    ```vb  
    ComboBox1.Items.Add("Tokyo")  
  
    ```  
  
    ```csharp  
    comboBox1.Items.Add("Tokyo");  
  
    ```  
  
    ```cpp  
    comboBox1->Items->Add("Tokyo");  
    ```  
  
     \-또는\-  
  
2.  목록에서 원하는 지점에 문자열이 나 개체를 삽입은`Insert` 메서드:  
  
    ```vb  
    CheckedListBox1.Items.Insert(0, "Copenhagen")  
  
    ```  
  
    ```csharp  
    checkedListBox1.Items.Insert(0, "Copenhagen");  
  
    ```  
  
    ```cpp  
    checkedListBox1->Items->Insert(0, "Copenhagen");  
    ```  
  
     \-또는\-  
  
3.  전체 배열을`Items` 컬렉션에 할당합니다.  
  
    ```vb  
    Dim ItemObject(9) As System.Object  
    Dim i As Integer  
       For i = 0 To 9  
       ItemObject(i) = "Item" & i  
    Next i  
    ListBox1.Items.AddRange(ItemObject)  
  
    ```  
  
    ```csharp  
    System.Object[] ItemObject = new System.Object[10];  
    for (int i = 0; i <= 9; i++)  
    {  
       ItemObject[i] = "Item" + i;  
    }  
    listBox1.Items.AddRange(ItemObject);  
  
    ```  
  
    ```cpp  
    Array<System::Object^>^ ItemObject = gcnew Array<System::Object^>(10);  
    for (int i = 0; i <= 9; i++)  
    {  
       ItemObject[i] = String::Concat("Item", i.ToString());  
    }  
    listBox1->Items->AddRange(ItemObject);  
    ```  
  
### 항목을 제거하려면  
  
1.  호출 하는`Remove` 또는`RemoveAt` 메서드 항목을 삭제 합니다.  
  
     `Remove` 제거할 항목을 지정 하는 인수가 하나 있습니다.`RemoveAt` 는 지정 된 인덱스 번호를 가진 항목을 제거 합니다.  
  
    ```vb  
    ' To remove item with index 0:  
    ComboBox1.Items.RemoveAt(0)  
    ' To remove currently selected item:  
    ComboBox1.Items.Remove(ComboBox1.SelectedItem)  
    ' To remove "Tokyo" item:  
    ComboBox1.Items.Remove("Tokyo")  
  
    ```  
  
    ```csharp  
    // To remove item with index 0:  
    comboBox1.Items.RemoveAt(0);  
    // To remove currently selected item:  
    comboBox1.Items.Remove(comboBox1.SelectedItem);  
    // To remove "Tokyo" item:  
    comboBox1.Items.Remove("Tokyo");  
  
    ```  
  
    ```cpp  
    // To remove item with index 0:  
    comboBox1->Items->RemoveAt(0);  
    // To remove currently selected item:  
    comboBox1->Items->Remove(comboBox1->SelectedItem);  
    // To remove "Tokyo" item:  
    comboBox1->Items->Remove("Tokyo");  
    ```  
  
### 모든 항목을 제거하려면  
  
1.  `Clear` 메서드를 호출하여 컬렉션에서 모든 항목을 제거합니다.  
  
    ```vb  
    ListBox1.Items.Clear()  
  
    ```  
  
    ```csharp  
    listBox1.Items.Clear();  
  
    ```  
  
    ```cpp  
    listBox1->Items->Clear();  
    ```  
  
## 참고 항목  
 <xref:System.Windows.Forms.ComboBox>   
 <xref:System.Windows.Forms.ListBox>   
 <xref:System.Windows.Forms.CheckedListBox>   
 [방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤의 내용 정렬](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)   
 [ListBox 대신 Windows Forms ComboBox를 사용해야 하는 경우](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)   
 [옵션 목록 표시에 사용하는 Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)