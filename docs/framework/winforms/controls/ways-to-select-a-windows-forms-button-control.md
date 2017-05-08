---
title: "Windows Forms Button 컨트롤 선택 방법 | Microsoft Docs"
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
  - "Button 컨트롤[Windows Forms], 선택"
ms.assetid: fe2fc058-5118-4f70-b264-6147d64a7a8d
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Windows Forms Button 컨트롤 선택 방법
다음과 같은 방법으로 Windows Forms 단추를 선택할 수 있습니다.  
  
-   마우스를 사용하여 단추를 클릭합니다.  
  
-   코드로 단추의 <xref:System.Windows.Forms.Control.Click> 이벤트를 호출합니다.  
  
-   Tab 키를 눌러 포커스를 단추로 이동한 다음 스페이스바 또는 Enter 키를 눌러 단추를 선택합니다.  
  
-   단추에 대한 선택키\(Alt\+괄호 안의 문자\)를 누릅니다.  선택키에 대한 자세한 내용은 [방법: Windows Forms 컨트롤에 대한 선택키 만들기](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)를 참조하십시오.  
  
-   단추가 폼의 "적용" 단추인 경우 다른 컨트롤에 포커스가 있어도 Enter 키를 누르면 이 단추가 클릭됩니다. 그러나 다른 컨트롤이 또 다른 단추이거나 여러 줄로 된 텍스트 상자 또는 Enter 키를 보유한 사용자 정의 컨트롤인 경우는 예외입니다.  
  
-   단추가 폼의 "취소" 단추인 경우 다른 컨트롤에 포커스가 있어도 Esc 키를 누르면 이 단추가 선택됩니다.  
  
-   단추를 프로그래밍 방식으로 선택하려면 <xref:System.Windows.Forms.Button.PerformClick%2A> 메서드를 호출합니다.  
  
## 참고 항목  
 [Button 컨트롤 개요](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)   
 [방법: Windows Forms 단추 클릭에 응답](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)   
 [Button 컨트롤](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)