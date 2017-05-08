---
title: "방법: Windows Forms ContextMenu 구성 요소를 사용하여 메뉴 항목 추가 및 제거 | Microsoft Docs"
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
  - "상황에 맞는 메뉴, 항목 추가"
  - "상황에 맞는 메뉴, 예제"
  - "상황에 맞는 메뉴, 항목 제거"
  - "ContextMenu 구성 요소[Windows Forms], 항목 추가"
  - "ContextMenu 구성 요소[Windows Forms], 항목 제거"
  - "예제[Windows Forms], 상황에 맞는 메뉴"
  - "바로 가기 메뉴, 항목 추가"
  - "바로 가기 메뉴, 예제"
  - "바로 가기 메뉴, 항목 제거"
ms.assetid: 426d1eaf-7fb8-4b0b-8a33-5e8721786ea4
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# 방법: Windows Forms ContextMenu 구성 요소를 사용하여 메뉴 항목 추가 및 제거
Windows Forms에서 바로 가기 메뉴 항목을 추가 및 제거하는 방법을 설명합니다.  
  
 Windows Forms <xref:System.Windows.Forms.ContextMenu> 구성 요소에서는 선택한 개체와 관련하여 자주 사용하는 명령을 표시하는 메뉴를 제공합니다.  <xref:System.Windows.Forms.Menu.MenuItems%2A> 컬렉션에 <xref:System.Windows.Forms.MenuItem> 개체를 추가하여 바로 가기 메뉴에 항목을 추가할 수 있습니다.  
  
 바로 가기 메뉴에서 항목을 완전히 제거할 수도 있지만, 런타임에 항목을 숨기거나 사용할 수 없도록 표시하는 것이 더 나을 수도 있습니다.  
  
> [!IMPORTANT]
>  <xref:System.Windows.Forms.MenuStrip> 및 <xref:System.Windows.Forms.ContextMenuStrip>은 이전 버전의 <xref:System.Windows.Forms.MainMenu> 및 <xref:System.Windows.Forms.ContextMenu> 컨트롤에 새로운 기능이 추가된 것으로, 이전 컨트롤을 대체합니다. 그러나 이전 버전과의 호환성 및 앞으로의 사용 가능성을 고려하여 <xref:System.Windows.Forms.MainMenu> 및 <xref:System.Windows.Forms.ContextMenu>를 계속 유지하도록 선택할 수 있습니다.  
  
### 바로 가기 메뉴에서 항목을 제거하려면  
  
1.  <xref:System.Windows.Forms.ContextMenu> 구성 요소의 <xref:System.Windows.Forms.Menu.MenuItems%2A> 컬렉션에서 <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> 또는 <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> 메서드를 사용하여 특정 메뉴 항목을 제거합니다.  
  
    ```vb  
    ' Removes the first item in the shortcut menu.  
    ContextMenu1.MenuItems.RemoveAt(0)  
    ' Removes a particular object from the shortcut menu.  
    ContextMenu1.MenuItems.Remove(mnuItemNew)  
  
    ```  
  
    ```csharp  
    // Removes the first item in the shortcut menu.  
    contextMenu1.MenuItems.RemoveAt(0);  
    // Removes a particular object from the shortcut menu.  
    contextMenu1.MenuItems.Remove(mnuItemNew);  
  
    ```  
  
    ```cpp  
    // Removes the first item in the shortcut menu.  
    contextMenu1->MenuItems->RemoveAt(0);  
    // Removes a particular object from the shortcut menu.  
    contextMenu1->MenuItems->Remove(mnuItemNew);  
    ```  
  
     또는  
  
2.  <xref:System.Windows.Forms.ContextMenu> 구성 요소의 `MenuItems` 컬렉션에서 `Clear` 메서드를 사용하여 메뉴에서 모든 항목을 제거합니다.  
  
    ```vb  
    ContextMenu1.MenuItems.Clear()  
  
    ```  
  
    ```csharp  
    contextMenu1.MenuItems.Clear();  
  
    ```  
  
    ```cpp  
    contextMenu1->MenuItems->Clear();  
    ```  
  
## 참고 항목  
 <xref:System.Windows.Forms.ContextMenu>   
 [ContextMenu 구성 요소](../../../../docs/framework/winforms/controls/contextmenu-component-windows-forms.md)   
 [ContextMenu 구성 요소 개요](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md)