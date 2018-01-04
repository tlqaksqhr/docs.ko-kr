---
title: "방법: Windows Forms ToolTip 구성 요소의 지연 변경"
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
- ToolTip component [Windows Forms], delay values
- tooltips [Windows Forms], delay values
- examples [Windows Forms], tooltips
ms.assetid: 08979ba7-dd84-477b-ab17-8d06e759be99
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f8506df062729a98adc1aa1e0dcb524aa4ec812c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-delay-of-the-windows-forms-tooltip-component"></a><span data-ttu-id="3c915-102">방법: Windows Forms ToolTip 구성 요소의 지연 변경</span><span class="sxs-lookup"><span data-stu-id="3c915-102">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>
<span data-ttu-id="3c915-103">Windows Forms에 대해 설정할 수 있는 지연 값이 여러 <xref:System.Windows.Forms.ToolTip> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3c915-103">There are multiple delay values that you can set for a Windows Forms <xref:System.Windows.Forms.ToolTip> component.</span></span> <span data-ttu-id="3c915-104">이러한 모든 속성에 대 한 측정 단위는 밀리초입니다.</span><span class="sxs-lookup"><span data-stu-id="3c915-104">The unit of measure for all these properties is milliseconds.</span></span> <span data-ttu-id="3c915-105"><xref:System.Windows.Forms.ToolTip.InitialDelay%2A> 속성 표시할 도구 설명 문자열에 대 한 연결된 된 컨트롤에 가리키고 있어야 기간을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c915-105">The <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> property determines how long the user must point at the associated control for the ToolTip string to appear.</span></span> <span data-ttu-id="3c915-106"><xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> 속성 후속 도구 설명 문자열이 다른 한 도구 설명과 연관 된 컨트롤에서 마우스를 이동할 때 나타나는 데 걸리는 시간 (밀리초)의 수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c915-106">The <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> property sets the number of milliseconds it takes for subsequent ToolTip strings to appear as the mouse moves from one ToolTip-associated control to another.</span></span> <span data-ttu-id="3c915-107"><xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> 속성 도구 설명 문자열이 표시 되는 시간의 길이 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c915-107">The <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> property determines the length of time the ToolTip string is shown.</span></span> <span data-ttu-id="3c915-108">값을 설정 하 여 개별적으로 또는 이러한 값을 설정할 수는 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> 속성, 속성에 할당 된 값에 따라 설정 됩니다는 지연 된 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> 속성.</span><span class="sxs-lookup"><span data-stu-id="3c915-108">You can set these values individually, or by setting the value of the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property; the other delay properties are set based on the value assigned to the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property.</span></span> <span data-ttu-id="3c915-109">예를 들어, <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> N 값으로 설정 되어 <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> N로 설정 되어 <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> 의 값으로 설정 되어 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> 5로 나눈 (또는 N/5) 및 <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> 다섯 번의 값에 해당 값으로 설정 됩니다는 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> 속성 (또는 5N).</span><span class="sxs-lookup"><span data-stu-id="3c915-109">For example, when <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> is set to a value N, <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> is set to N, <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> is set to the value of <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> divided by five (or N/5), and <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> is set to a value that is five times the value of the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property (or 5N).</span></span>  
  
### <a name="to-set-the-delay"></a><span data-ttu-id="3c915-110">지연 시간을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="3c915-110">To set the delay</span></span>  
  
1.  <span data-ttu-id="3c915-111">이 예제에 나와 있는 것 처럼 다음 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c915-111">Set the following properties as shown in this example.</span></span>  
  
    ```vb  
    ToolTip1.InitialDelay = 500  
    ToolTip1.ReshowDelay = 100  
    ToolTip1.AutoPopDelay = 5000  
    ```  
  
    ```csharp  
    ToolTip1.InitialDelay = 500;  
    ToolTip1.ReshowDelay = 100;  
    ToolTip1.AutoPopDelay = 5000;  
    ```  
  
    ```cpp  
    toolTip1->InitialDelay = 500;  
    toolTip1->ReshowDelay = 100;  
    toolTip1->AutoPopDelay = 5000;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3c915-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3c915-112">See Also</span></span>  
 [<span data-ttu-id="3c915-113">ToolTip 구성 요소 개요</span><span class="sxs-lookup"><span data-stu-id="3c915-113">ToolTip Component Overview</span></span>](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md)  
 [<span data-ttu-id="3c915-114">방법: 디자인 타임에 Windows Form의 컨트롤에 도구 설명 설정</span><span class="sxs-lookup"><span data-stu-id="3c915-114">How to: Set ToolTips for Controls on a Windows Form at Design Time</span></span>](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)  
 [<span data-ttu-id="3c915-115">ToolTip 구성 요소</span><span class="sxs-lookup"><span data-stu-id="3c915-115">ToolTip Component</span></span>](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)
