---
title: "방법: ToolStripMenuItems 사용 안 함 | Microsoft Docs"
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
  - "메뉴 항목 사용 안 함"
  - "메뉴 항목, 비활성화"
  - "메뉴 항목, 사용"
  - "메뉴, 메뉴 항목 사용 안 함"
  - "ToolStripMenuItems, 비활성화"
  - "ToolStripMenuItems, 사용"
ms.assetid: bcc1da84-50fd-41d2-8475-103b581d5654
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: ToolStripMenuItems 사용 안 함
사용자의 동작에 따라 메뉴 항목을 활성화 또는 비활성화하여 사용자가 수행하는 명령을 제한하거나 확장할 수 있습니다.  메뉴 항목은 처음 만들 때 기본적으로 활성화되지만 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> 속성을 통해 조정할 수 있습니다.  이 속성은 디자인 타임에 **속성** 창에서 조작하거나, 코드로 설정하여 프로그래밍 방식으로 조작할 수 있습니다.  
  
### 프로그래밍 방식으로 메뉴를 비활성화하려면  
  
-   메뉴 항목의 속성을 설정하는 메서드에 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> 속성을 `false`로 설정하는 코드를 추가합니다.  
  
    ```vb  
    MenuItem1.Enabled = False  
    ```  
  
    ```csharp  
    menuItem1.Enabled = false;  
    ```  
  
    ```cpp  
    menuItem1->Enabled = false;  
    ```  
  
    > [!TIP]
    >  메뉴에서 첫 번째 항목 또는 최상위 항목을 비활성화하면 해당 메뉴에 포함된 모든 메뉴 항목이 숨겨지지만 비활성화되지는 않습니다.  마찬가지로 하위 메뉴 항목을 가진 메뉴 항목을 비활성화하면 해당 하위 메뉴 항목이 숨겨지지만 비활성화되지 않습니다.  특정 메뉴의 모든 명령이 사용할 수 없는 명령일 경우 사용자 인터페이스를 명확하게 표시하기 위해 전체 메뉴를 숨기고 비활성화하는 것이 바람직한 프로그래밍 습관입니다.  메뉴 항목을 숨기기만 할 경우 바로 가기 키를 통해 메뉴 명령에 액세스하는 것을 방지할 수 없으므로 메뉴를 숨기고 비활성화한 다음 모든 항목과 해당 메뉴의 모든 하위 메뉴 항목을 비활성화해야 합니다.  최상위 메뉴 항목의 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 속성을 `false`로 설정하여 전체 메뉴를 숨깁니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStripMenuItem>   
 [방법: ToolStripMenuItems 숨기기](../../../../docs/framework/winforms/controls/how-to-hide-toolstripmenuitems.md)   
 [MenuStrip 컨트롤 개요](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)