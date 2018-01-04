---
title: "방법: 프로그래밍 방식으로 Windows Forms DomainUpDown 컨트롤에 항목 추가"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- spin button control [Windows Forms], adding items
- DomainUpDown control [Windows Forms], adding items to
ms.assetid: fd31d314-33eb-4181-90f8-d32ed0c4e072
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9e540e394226f20c40915f4d9de31afcffdf6e35
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-items-to-windows-forms-domainupdown-controls-programmatically"></a>방법: 프로그래밍 방식으로 Windows Forms DomainUpDown 컨트롤에 항목 추가
Windows Forms에 항목을 추가할 수 있습니다 <xref:System.Windows.Forms.DomainUpDown> 코드에서 컨트롤입니다. 호출의 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> 또는 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> 의 메서드는 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> 컨트롤의 항목을 추가 하는 클래스 <xref:System.Windows.Forms.DomainUpDown.Items%2A> 속성입니다. <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> 메서드는 컬렉션의 끝에 항목을 추가 하는 동안는 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> 메서드가 지정된 된 위치에 항목을 추가 합니다.  
  
### <a name="to-add-a-new-item"></a>새 항목을 추가 하려면  
  
1.  사용 하 여는 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> 메서드를 목록 항목의 끝에 항목을 추가 합니다.  
  
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
  
2.  사용 된 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> 메서드를 지정된 된 위치에 있는 목록에 항목을 삽입 합니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.DomainUpDown>  
 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A?displayProperty=nameWithType>  
 <xref:System.Collections.ArrayList.Insert%2A?displayProperty=nameWithType>  
 [DomainUpDown 컨트롤](../../../../docs/framework/winforms/controls/domainupdown-control-windows-forms.md)  
 [DomainUpDown 컨트롤 개요](../../../../docs/framework/winforms/controls/domainupdown-control-overview-windows-forms.md)
