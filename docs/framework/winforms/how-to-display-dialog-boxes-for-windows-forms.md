---
title: "방법: Windows Forms 대화 상자 표시 | Microsoft Docs"
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
  - "대화 상자, Windows Forms에 표시"
  - "Windows Forms 대화 상자, 표시"
  - "Windows Forms, 다른 폼에서 폼 호출"
  - "Windows Forms, 표시"
ms.assetid: aaac1b38-c651-495a-8d3d-5a9bfb32fee3
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: Windows Forms 대화 상자 표시
응용 프로그램에서 다른 폼을 표시할 때와 같은 방법으로 대화 상자를 표시합니다.  시작 폼은 응용 프로그램이 실행될 때 자동으로 로드됩니다.  응용 프로그램에 두 번째 폼 또는 대화 상자를 나타내려면 해당 폼이나 대화 상자를 로드하여 표시하는 코드를 작성합니다.  이와 마찬가지로 폼 또는 대화 상자가 사라지게 하려면 해당 폼이나 대화 상자를 언로드하거나 숨기는 코드를 작성합니다.  
  
### 대화 상자를 표시하려면  
  
1.  대화 상자를 여는 데 사용할 이벤트 처리기로 이동합니다.  메뉴 명령을 선택하거나 단추를 클릭하거나 기타 이벤트가 발생할 때 대화 상자를 표시할 수 있습니다.  
  
2.  이벤트 처리기에 대화 상자를 여는 코드를 추가합니다.  이 예제에서는 Button\-Click 이벤트를 사용하여 대화 상자를 표시합니다.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       Dim dlg1 as new Form()  
       dlg1.ShowDialog()  
    End Sub  
  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)   
    {  
       Form dlg1 = new Form();  
       dlg1.ShowDialog();  
    }  
  
    ```  
  
    ```cpp  
    private:   
      void button1_Click(System::Object ^ sender,  
        System::EventArgs ^ e)  
      {  
        Form ^ dlg1 = gcnew Form();  
        dlg1->ShowDialog();  
      }  
    ```