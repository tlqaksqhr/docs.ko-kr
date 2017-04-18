---
title: "방법: Windows Forms Button을 취소 단추로 지정 | Microsoft Docs"
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
  - "Button 컨트롤[Windows Forms], 취소 단추로 지정"
  - "단추, 취소 단추"
ms.assetid: 252f0834-e54b-44d9-96f7-ee5f50e94f2c
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: Windows Forms Button을 취소 단추로 지정
모든 Windows Forms에서 <xref:System.Windows.Forms.Button> 컨트롤을 취소 단추로 지정할 수 있습니다.  폼에서 포커스의 위치에 관계없이 Esc 키를 누를 때마다 취소 단추가 클릭됩니다.  어떤 동작 없이 빠르게 작업을 종료할 수 있도록 프로그래밍할 때 일반적으로 이 단추를 사용합니다.  
  
### 취소 단추를 지정하려면  
  
1.  폼의 <xref:System.Windows.Forms.Form.CancelButton%2A> 속성을 해당 <xref:System.Windows.Forms.Button> 컨트롤로 설정합니다.  
  
    ```vb  
    Private Sub SetCancelButton(ByVal myCancelBtn As Button)  
       Me.CancelButton = myCancelBtn  
    End Sub  
    ```  
  
    ```csharp  
    private void SetCancelButton(Button myCancelBtn)  
    {  
       this.CancelButton = myCancelBtn;  
    }  
    ```  
  
    ```cpp  
    private:  
       void SetCancelButton(Button ^ myCancelBtn)  
       {  
          this->CancelButton = myCancelBtn;  
       }  
    ```  
  
## 참고 항목  
 <xref:System.Windows.Forms.Form.CancelButton%2A>   
 [Button 컨트롤 개요](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)   
 [Windows Forms Button 컨트롤 선택 방법](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)   
 [방법: Windows Forms 단추 클릭에 응답](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)   
 [방법: Windows Forms 단추를 적용 단추로 지정](../../../../docs/framework/winforms/controls/how-to-designate-a-windows-forms-button-as-the-accept-button.md)   
 [Button 컨트롤](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)