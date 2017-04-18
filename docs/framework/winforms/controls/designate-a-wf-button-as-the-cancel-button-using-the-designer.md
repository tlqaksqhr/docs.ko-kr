---
title: "방법: 디자이너를 사용하여 Windows Forms 단추를 취소 단추로 지정 | Microsoft Docs"
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
ms.assetid: 30e77d9c-d565-4ab5-a84a-62c043af8822
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: 디자이너를 사용하여 Windows Forms 단추를 취소 단추로 지정
모든 Windows Forms에서 <xref:System.Windows.Forms.Button> 컨트롤을 취소 단추로 지정할 수 있습니다.  폼에서 포커스의 위치에 관계없이 Esc 키를 누를 때마다 취소 단추가 클릭됩니다.  어떤 동작 없이 빠르게 작업을 종료할 수 있도록 프로그래밍할 때 일반적으로 이 단추를 사용합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 취소 단추를 지정하려면  
  
1.  단추가 있는 폼을 선택합니다.  
  
2.  **속성** 창에서 폼의 <xref:System.Windows.Forms.Form.CancelButton%2A> 속성을 <xref:System.Windows.Forms.Button> 컨트롤 이름으로 설정합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.Form.CancelButton%2A>   
 [Button 컨트롤 개요](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)   
 [Windows Forms Button 컨트롤 선택 방법](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)   
 [방법: Windows Forms 단추 클릭에 응답](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)   
 [방법: 디자이너를 사용하여 Windows Forms 단추를 적용 단추로 지정](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-accept-button-using-the-designer.md)   
 [Button 컨트롤](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)