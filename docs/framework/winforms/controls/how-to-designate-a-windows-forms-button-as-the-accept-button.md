---
title: "방법: Windows Forms 단추를 적용 단추로 지정 | Microsoft Docs"
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
  - "Windows Forms에 있는 적용 단추"
  - "Button 컨트롤[Windows Forms], 기본값으로 지정"
  - "단추, Windows Forms의 기본값"
  - "Windows Forms 컨트롤, 폼의 기본 단추"
ms.assetid: 22cc9da6-b913-4e04-9554-dee443ac5c3a
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: Windows Forms 단추를 적용 단추로 지정
Windows Form에서는 <xref:System.Windows.Forms.Button> 컨트롤을 적용 단추\(또는 기본 단추\)로 지정할 수 있습니다.  폼에서 포커스의 위치에 관계없이 Enter 키를 누를 때마다 기본 단추가 클릭됩니다.  
  
> [!NOTE]
>  포커스가 있는 컨트롤이 다른 단추인 경우에는 예외입니다. 이 경우에는 포커스가 있는 단추나 여러 줄로 된 텍스트 상자 또는 Enter 키를 보유한 사용자 지정 컨트롤이 클릭됩니다.  
  
### 적용 단추를 지정하려면  
  
1.  폼의 <xref:System.Windows.Forms.Form.AcceptButton%2A> 속성을 해당 <xref:System.Windows.Forms.Button> 컨트롤로 설정합니다.  
  
    ```vb  
    Private Sub SetDefault(ByVal myDefaultBtn As Button)  
      Me.AcceptButton = myDefaultBtn   
    End Sub  
    ```  
  
    ```csharp  
    private void SetDefault(Button myDefaultBtn)  
    {  
       this.AcceptButton = myDefaultBtn;  
    }  
    ```  
  
    ```cpp  
    private:  
       void SetDefault(Button ^ myDefaultBtn)  
       {  
          this->AcceptButton = myDefaultBtn;  
       }  
    ```  
  
## 참고 항목  
 <xref:System.Windows.Forms.Form.AcceptButton%2A>   
 [Button 컨트롤 개요](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)   
 [Windows Forms Button 컨트롤 선택 방법](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)   
 [방법: Windows Forms 단추 클릭에 응답](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)   
 [방법: Windows Forms Button을 취소 단추로 지정](../../../../docs/framework/winforms/controls/how-to-designate-a-windows-forms-button-as-the-cancel-button.md)   
 [Button 컨트롤](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)