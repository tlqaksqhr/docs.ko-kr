---
title: "방법: Windows Forms DomainUpDown 컨트롤에서 항목 제거"
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
- DomainUpDown control [Windows Forms], removing items from
- spin button control [Windows Forms], removing items
ms.assetid: e70f5cbc-b497-41a9-975a-344c00e56ed2
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7cab9bf4445c7322c1b4824f26c0821de8c58657
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-remove-items-from-windows-forms-domainupdown-controls"></a><span data-ttu-id="77d22-102">방법: Windows Forms DomainUpDown 컨트롤에서 항목 제거</span><span class="sxs-lookup"><span data-stu-id="77d22-102">How to: Remove Items from Windows Forms DomainUpDown Controls</span></span>
<span data-ttu-id="77d22-103">Windows Forms에서 항목을 제거할 수 <xref:System.Windows.Forms.DomainUpDown> 호출 하 여 컨트롤의 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> 또는 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> 의 메서드는 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="77d22-103">You can remove items from the Windows Forms <xref:System.Windows.Forms.DomainUpDown> control by calling the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> or <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class.</span></span> <span data-ttu-id="77d22-104"><xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> 메서드가 특정 항목을 제거 하는 동안는 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> 메서드 위치에 항목을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="77d22-104">The <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> method removes a specific item, while the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method removes an item by its position.</span></span>  
  
### <a name="to-remove-an-item"></a><span data-ttu-id="77d22-105">항목을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="77d22-105">To remove an item</span></span>  
  
-   <span data-ttu-id="77d22-106">사용 하 여는 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> 의 메서드는 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> 이름별으로 항목을 제거 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="77d22-106">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class to remove an item by name.</span></span>  
  
    ```vb  
    DomainUpDown1.Items.Remove("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Remove("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Remove("noodles");  
    ```  
  
     <span data-ttu-id="77d22-107">또는</span><span class="sxs-lookup"><span data-stu-id="77d22-107">-or-</span></span>  
  
-   <span data-ttu-id="77d22-108">사용 하 여는 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> 메서드를 해당 위치에 항목을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="77d22-108">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method to remove an item by its position.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="77d22-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="77d22-109">See Also</span></span>  
 <xref:System.Windows.Forms.DomainUpDown>  
 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="77d22-110">DomainUpDown 컨트롤</span><span class="sxs-lookup"><span data-stu-id="77d22-110">DomainUpDown Control</span></span>](../../../../docs/framework/winforms/controls/domainupdown-control-windows-forms.md)  
 [<span data-ttu-id="77d22-111">DomainUpDown 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="77d22-111">DomainUpDown Control Overview</span></span>](../../../../docs/framework/winforms/controls/domainupdown-control-overview-windows-forms.md)
