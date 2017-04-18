---
title: "방법: ToolStripMenuItems 숨기기 | Microsoft Docs"
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
  - "메뉴 항목 숨기기"
  - "메뉴 항목, 숨기기"
  - "메뉴, 메뉴 항목 숨기기"
  - "MenuStrip 컨트롤[Windows Forms], 메뉴 항목 숨기기"
  - "ToolStripMenuItems, 숨기기"
ms.assetid: 418a768f-808a-44cd-8cef-f4e161883621
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: ToolStripMenuItems 숨기기
메뉴 항목을 숨기면 응용 프로그램의 사용자 인터페이스를 제어하고 사용자 명령을 제한할 수 있습니다.  메뉴의 모든 항목이 사용할 수 없는 항목일 경우 대개 전체 메뉴를 숨기는 것이 좋습니다.  이렇게 하면 사용자의 혼란을 줄일 수 있습니다.  또한 숨기는 것만으로도 사용자가 바로 가기 키를 사용하여 메뉴 명령에 액세스하는 것이 가능하므로 메뉴 또는 메뉴 항목을 숨김과 동시에 비활성화할 수 있습니다.  
  
### 프로그래밍 방식으로 메뉴 항목을 숨기려면  
  
-   메뉴 항목의 속성을 설정하는 메서드에서 코드를 추가하여 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 속성을 `false`로 설정합니다.  
  
    ```vb  
    MenuItem3.Visible = False  
  
    ```  
  
    ```csharp  
    menuItem3.Visible = false;  
  
    ```  
  
    ```cpp  
    menuItem3->Visible = false;  
  
    ```  
  
## 참고 항목  
 <xref:System.Windows.Forms.ToolStripItem.Visible%2A>   
 <xref:System.Windows.Forms.MenuStrip>   
 [MenuStrip 컨트롤 개요](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)   
 [방법: ToolStripMenuItems 사용 안 함](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems.md)