---
title: '방법: Windows Forms DomainUpDown 컨트롤에서 항목 제거'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DomainUpDown control [Windows Forms], removing items from
- spin button control [Windows Forms], removing items
ms.assetid: e70f5cbc-b497-41a9-975a-344c00e56ed2
ms.openlocfilehash: 702e5e2180148758c4b3775a5cc96a1365703166
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532163"
---
# <a name="how-to-remove-items-from-windows-forms-domainupdown-controls"></a>방법: Windows Forms DomainUpDown 컨트롤에서 항목 제거
Windows Forms에서 항목을 제거할 수 <xref:System.Windows.Forms.DomainUpDown> 호출 하 여 컨트롤의 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> 또는 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> 의 메서드는 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> 클래스입니다. <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> 메서드가 특정 항목을 제거 하는 동안는 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> 메서드 위치에 항목을 제거 합니다.  
  
### <a name="to-remove-an-item"></a>항목을 제거 하려면  
  
-   사용 하 여는 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> 의 메서드는 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> 이름별으로 항목을 제거 하는 클래스입니다.  
  
    ```vb  
    DomainUpDown1.Items.Remove("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Remove("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Remove("noodles");  
    ```  
  
     -또는-  
  
-   사용 하 여는 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> 메서드를 해당 위치에 항목을 제거 합니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.DomainUpDown>  
 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A?displayProperty=nameWithType>  
 [DomainUpDown 컨트롤](../../../../docs/framework/winforms/controls/domainupdown-control-windows-forms.md)  
 [DomainUpDown 컨트롤 개요](../../../../docs/framework/winforms/controls/domainupdown-control-overview-windows-forms.md)
