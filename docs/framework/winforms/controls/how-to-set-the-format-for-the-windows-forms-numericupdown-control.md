---
title: "방법: Windows Forms NumericUpDown 컨트롤의 형식 설정"
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
- NumericUpDown control [Windows Forms], formatting values
- up-down controls [Windows Forms], formatting numeric values
ms.assetid: fa7c5557-6bfb-45b2-975d-8887b23b0ba0
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 001cc32aa9e1f31695f3b349480b6dd5154b31a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-the-format-for-the-windows-forms-numericupdown-control"></a><span data-ttu-id="dc2a5-102">방법: Windows Forms NumericUpDown 컨트롤의 형식 설정</span><span class="sxs-lookup"><span data-stu-id="dc2a5-102">How to: Set the Format for the Windows Forms NumericUpDown Control</span></span>
<span data-ttu-id="dc2a5-103">Windows Forms에서 값이 표시 되는 방식을 구성할 수 있습니다 <xref:System.Windows.Forms.NumericUpDown> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc2a5-103">You can configure how values are displayed in the Windows Forms <xref:System.Windows.Forms.NumericUpDown> control.</span></span> <span data-ttu-id="dc2a5-104"><xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> 속성 소수점 뒤 나타나는 숫자의 개수를 결정; 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="dc2a5-104">The <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> property determines how many numbers appear after the decimal point; the default is 0.</span></span> <span data-ttu-id="dc2a5-105"><xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> 속성 10 진수 3 자리 마다는 구분 기호를 삽입할지 여부를 결정 있고 기본값은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="dc2a5-105">The <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> property determines whether a separator will be inserted between every three decimal digits; the default is `false`.</span></span> <span data-ttu-id="dc2a5-106">컨트롤 값을 표시할 수 10 진수 형식 대신 16 진수의 경우는 <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> 속성이 `true`; 기본값은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="dc2a5-106">The control can display values in hexadecimal instead of decimal format, if the <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> property is set to `true`; the default is `false`.</span></span>  
  
### <a name="to-format-the-numeric-value"></a><span data-ttu-id="dc2a5-107">숫자 값의 서식을 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="dc2a5-107">To format the numeric value</span></span>  
  
-   <span data-ttu-id="dc2a5-108">설정 하 여 10 진수 값이 표시는 <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> 속성을 설정 하 고는 정수는 <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> 속성을 `true` 또는 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="dc2a5-108">Display a decimal value by setting the <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> property to an integer and setting the <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> property to `true` or `false`.</span></span>  
  
    ```vb  
    NumericUpDown1.DecimalPlaces = 2  
    NumericUpDown1.ThousandsSeparator = True  
    ```  
  
    ```csharp  
    numericUpDown1.DecimalPlaces = 2;  
    numericUpDown1.ThousandsSeparator = true;  
    ```  
  
    ```cpp  
    numericUpDown1->DecimalPlaces = 2;  
    numericUpDown1->ThousandsSeparator = true;  
    ```  
  
     <span data-ttu-id="dc2a5-109">또는</span><span class="sxs-lookup"><span data-stu-id="dc2a5-109">-or-</span></span>  
  
-   <span data-ttu-id="dc2a5-110">16 진수 값을 설정 하 여 표시 된 <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> 속성을 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="dc2a5-110">Display a hexadecimal value by setting the <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> property to `true`.</span></span>  
  
    ```vb  
    NumericUpDown1.Hexadecimal = True  
    ```  
  
    ```csharp  
    numericUpDown1.Hexadecimal = true;  
    ```  
  
    ```cpp  
    numericUpDown1->Hexadecimal = true;  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="dc2a5-111">값이 16 진수로 폼에 표시 되는 경우에 모든 테스트에서 수행한는 <xref:System.Windows.Forms.NumericUpDown.Value%2A> 속성을 테스트 하는 10 진수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="dc2a5-111">Even if the value is displayed on the form as hexadecimal, any tests you perform on the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property will be testing its decimal value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc2a5-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc2a5-112">See Also</span></span>  
 <xref:System.Windows.Forms.NumericUpDown>  
 [<span data-ttu-id="dc2a5-113">NumericUpDown 컨트롤</span><span class="sxs-lookup"><span data-stu-id="dc2a5-113">NumericUpDown Control</span></span>](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md)  
 [<span data-ttu-id="dc2a5-114">NumericUpDown 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="dc2a5-114">NumericUpDown Control Overview</span></span>](../../../../docs/framework/winforms/controls/numericupdown-control-overview-windows-forms.md)
