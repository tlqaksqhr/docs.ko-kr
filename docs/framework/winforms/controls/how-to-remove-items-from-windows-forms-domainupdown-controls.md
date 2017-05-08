---
title: "방법: Windows Forms DomainUpDown 컨트롤에서 항목 제거 | Microsoft Docs"
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
  - "DomainUpDown 컨트롤[Windows Forms], 항목 제거"
  - "spin button 컨트롤, 항목 제거"
ms.assetid: e70f5cbc-b497-41a9-975a-344c00e56ed2
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: Windows Forms DomainUpDown 컨트롤에서 항목 제거
<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> 클래스의 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> 또는 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> 메서드를 호출하여 Windows Forms <xref:System.Windows.Forms.DomainUpDown> 컨트롤에서 항목을 제거할 수 있습니다.  <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> 메서드는 특정 항목을 제거하고 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> 메서드는 특정 위치에 있는 항목을 제거합니다.  
  
### 항목을 제거하려면  
  
-   이름으로 항목을 제거하려면 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> 클래스의 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> 메서드를 사용합니다.  
  
    ```vb  
    DomainUpDown1.Items.Remove("noodles")  
  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Remove("noodles");  
  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Remove("noodles");  
    ```  
  
     또는  
  
-   특정 위치에 있는 항목을 제거하려면 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> 메서드를 사용합니다.  
  
    ```vb  
    ' Removes the first item in the list.  
    DomainUpDown1.Items.RemoveAt(0)  
  
    ```  
  
    ```csharp  
    // Removes the first item in the list.  
    domainUpDown1.Items.RemoveAt(0);  
  
    ```  
  
    ```cpp  
    // Removes the first item in the list.  
    domainUpDown1->Items->RemoveAt(0);  
    ```  
  
## 참고 항목  
 <xref:System.Windows.Forms.DomainUpDown>   
 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A?displayProperty=fullName>   
 [DomainUpDown 컨트롤](../../../../docs/framework/winforms/controls/domainupdown-control-windows-forms.md)   
 [DomainUpDown 컨트롤 개요](../../../../docs/framework/winforms/controls/domainupdown-control-overview-windows-forms.md)