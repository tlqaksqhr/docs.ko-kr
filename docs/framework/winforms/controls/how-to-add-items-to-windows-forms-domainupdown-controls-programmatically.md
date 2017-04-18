---
title: "방법: 프로그래밍 방식으로 Windows Forms DomainUpDown 컨트롤에 항목 추가 | Microsoft Docs"
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
  - "DomainUpDown 컨트롤[Windows Forms], 항목 추가"
  - "spin button 컨트롤, 항목 추가"
ms.assetid: fd31d314-33eb-4181-90f8-d32ed0c4e072
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: 프로그래밍 방식으로 Windows Forms DomainUpDown 컨트롤에 항목 추가
코드를 작성하여 Windows Forms <xref:System.Windows.Forms.DomainUpDown> 컨트롤에 항목을 추가할 수 있습니다.  컨트롤의 <xref:System.Windows.Forms.DomainUpDown.Items%2A> 속성에 항목을 추가하려면 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> 클래스의 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> 또는 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> 메서드를 호출합니다.  <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> 메서드는 컬렉션의 끝에 항목을 추가하고 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> 메서드는 지정된 위치에 항목을 추가합니다.  
  
### 새 항목을 추가하려면  
  
1.  <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> 메서드를 사용하여 항목 목록의 끝에 항목을 추가합니다.  
  
    ```vb  
    DomainUpDown1.Items.Add("noodles")  
  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Add("noodles");  
  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Add("noodles");  
    ```  
  
     또는  
  
2.  <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> 메서드를 사용하여 목록에서 지정된 위치에 항목을 삽입합니다.  
  
    ```vb  
    ' Inserts an item at the third position in the list  
    DomainUpDown1.Items.Insert(2, "rice")  
  
    ```  
  
    ```csharp  
    // Inserts an item at the third position in the list  
    domainUpDown1.Items.Insert(2, "rice");  
  
    ```  
  
    ```cpp  
    // Inserts an item at the third position in the list  
    domainUpDown1->Items->Insert(2, "rice");  
    ```  
  
## 참고 항목  
 <xref:System.Windows.Forms.DomainUpDown>   
 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A?displayProperty=fullName>   
 <xref:System.Collections.ArrayList.Insert%2A?displayProperty=fullName>   
 [DomainUpDown 컨트롤](../../../../docs/framework/winforms/controls/domainupdown-control-windows-forms.md)   
 [DomainUpDown 컨트롤 개요](../../../../docs/framework/winforms/controls/domainupdown-control-overview-windows-forms.md)