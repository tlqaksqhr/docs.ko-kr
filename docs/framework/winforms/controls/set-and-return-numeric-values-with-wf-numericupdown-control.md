---
title: "방법: Windows Forms NumericUpDown 컨트롤을 사용하여 숫자 값 설정 및 반환"
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
- numeric values [Windows Forms], Windows Forms
- Windows Forms, numeric values
- Windows Forms controls, NumericUpDown
- NumericUpDown control [Windows Forms], setting and returning values
ms.assetid: 5bd8f8cd-4c12-49ea-9cc3-2a647d064689
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f31f0b247c882b8ccba84930f7e21f5eea088a35
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-and-return-numeric-values-with-the-windows-forms-numericupdown-control"></a><span data-ttu-id="9b061-102">방법: Windows Forms NumericUpDown 컨트롤을 사용하여 숫자 값 설정 및 반환</span><span class="sxs-lookup"><span data-stu-id="9b061-102">How to: Set and Return Numeric Values with the Windows Forms NumericUpDown Control</span></span>
<span data-ttu-id="9b061-103">Windows Forms의 숫자 값 <xref:System.Windows.Forms.NumericUpDown> 컨트롤 따라 사용자가 해당 <xref:System.Windows.Forms.NumericUpDown.Value%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="9b061-103">The numeric value of the Windows Forms <xref:System.Windows.Forms.NumericUpDown> control is determined by its <xref:System.Windows.Forms.NumericUpDown.Value%2A> property.</span></span> <span data-ttu-id="9b061-104">다른 속성의 경우와 마찬가지로 컨트롤의 값에 대 한 조건부 검사를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b061-104">You can write conditional tests for the control's value just as with any other property.</span></span> <span data-ttu-id="9b061-105">한 번의 <xref:System.Windows.Forms.NumericUpDown.Value%2A> 속성이 설정 되어,이 경우에 작업을 수행 하는 코드를 작성 하 여 직접 조정할 수 있습니다 또는 호출할 수 있습니다는 <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> 및 <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="9b061-105">Once the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property is set, you can adjust it directly by writing code to perform operations on it, or you can call the <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> and <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> methods.</span></span>  
  
### <a name="to-set-the-numeric-value"></a><span data-ttu-id="9b061-106">숫자 값을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="9b061-106">To set the numeric value</span></span>  
  
1.  <span data-ttu-id="9b061-107">값을 할당는 <xref:System.Windows.Forms.NumericUpDown.Value%2A> 코드 또는 속성 창에서 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="9b061-107">Assign a value to the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property in code or in the Properties window.</span></span>  
  
    ```vb  
    NumericUpDown1.Value = 55  
    ```  
  
    ```csharp  
    numericUpDown1.Value = 55;  
    ```  
  
    ```cpp  
    numericUpDown1->Value = 55;  
    ```  
  
     <span data-ttu-id="9b061-108">또는</span><span class="sxs-lookup"><span data-stu-id="9b061-108">-or-</span></span>  
  
2.  <span data-ttu-id="9b061-109">호출 된 <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> 또는 <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> 값에 지정 된 크기를 늘리거나 메서드는 <xref:System.Windows.Forms.NumericUpDown.Increment%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="9b061-109">Call the <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> or <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> method to increase or decrease the value by the amount specified in the <xref:System.Windows.Forms.NumericUpDown.Increment%2A> property.</span></span>  
  
    ```vb  
    NumericUpDown1.UpButton()  
    ```  
  
    ```csharp  
    numericUpDown1.UpButton();  
    ```  
  
    ```cpp  
    numericUpDown1->UpButton();  
    ```  
  
### <a name="to-return-the-numeric-value"></a><span data-ttu-id="9b061-110">숫자 값을 반환 하려면</span><span class="sxs-lookup"><span data-stu-id="9b061-110">To return the numeric value</span></span>  
  
-   <span data-ttu-id="9b061-111">액세스는 <xref:System.Windows.Forms.NumericUpDown.Value%2A> 코드에서 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="9b061-111">Access the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property in code.</span></span>  
  
    ```vb  
    If NumericUpDown1.Value >= 65 Then  
       MessageBox.Show("Age is: " & NumericUpDown1.Value.ToString)  
    Else  
       MessageBox.Show("The customer is ineligible for a senior citizen discount.")  
    End If  
    ```  
  
    ```csharp  
    if(numericUpDown1.Value >= 65)  
    {  
       MessageBox.Show("Age is: " + numericUpDown1.Value.ToString());  
    }  
    else  
    {  
       MessageBox.Show("The customer is ineligible for a senior citizen discount.");  
    }  
    ```  
  
    ```cpp  
    if(numericUpDown1->Value >= 65)  
    {  
       MessageBox::Show(String::Concat("Age is: ",  
          numericUpDown1->Value.ToString()));  
    }  
    else  
    {  
       MessageBox::Show  
          ("The customer is ineligible for a senior citizen discount.");  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9b061-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9b061-112">See Also</span></span>  
 <xref:System.Windows.Forms.NumericUpDown>  
 <xref:System.Windows.Forms.NumericUpDown.Value%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.NumericUpDown.Increment%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.NumericUpDown.UpButton%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.NumericUpDown.DownButton%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="9b061-113">NumericUpDown 컨트롤</span><span class="sxs-lookup"><span data-stu-id="9b061-113">NumericUpDown Control</span></span>](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md)  
 [<span data-ttu-id="9b061-114">NumericUpDown 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="9b061-114">NumericUpDown Control Overview</span></span>](../../../../docs/framework/winforms/controls/numericupdown-control-overview-windows-forms.md)
