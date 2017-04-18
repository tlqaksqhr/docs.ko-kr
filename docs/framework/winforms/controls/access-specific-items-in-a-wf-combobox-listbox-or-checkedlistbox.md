---
title: "방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤의 특정 항목에 액세스 | Microsoft Docs"
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
  - "CheckedListBox 컨트롤[Windows Forms], 항목 액세스"
  - "콤보 상자, 항목 액세스"
  - "ComboBox 컨트롤[Windows Forms], 항목 액세스"
  - "목록 상자, 항목 액세스"
  - "ListBox 컨트롤[Windows Forms], 항목 액세스"
  - "ListBox 컨트롤[Windows Forms], 항목 정보 반환"
ms.assetid: 1216742f-bcf9-4ff8-8a62-d7c9053c2b96
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤의 특정 항목에 액세스
Windows Forms 콤보 상자, 목록 상자 또는 확인 목록 상자의 특정 항목에 액세스하는 것은 중요한 작업입니다.  이 작업을 통해 어떤 위치에서든지 목록 내에 어떤 항목이 있는지 프로그래밍 방식으로 확인할 수 있습니다.  
  
### 특정 항목에 액세스하려면  
  
1.  특정 항목의 인덱스를 사용하여`Items` 컬렉션을 쿼리합니다.  
  
    ```vb  
    Private Function GetItemText(i As Integer) As String  
       ' Return the text of the item using the index:  
       Return ComboBox1.Items(i).ToString  
    End Function  
  
    ```  
  
    ```csharp  
    private string GetItemText(int i)  
    {  
       // Return the text of the item using the index:  
       return (comboBox1.Items[i].ToString());  
    }  
  
    ```  
  
    ```cpp  
    private:  
       String^ GetItemText(int i)  
       {  
          // Return the text of the item using the index:  
          return (comboBox1->Items->Item[i]->ToString());  
       }  
    ```  
  
## 참고 항목  
 <xref:System.Windows.Forms.ComboBox>   
 <xref:System.Windows.Forms.ListBox>   
 <xref:System.Windows.Forms.CheckedListBox>   
 [옵션 목록 표시에 사용하는 Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)