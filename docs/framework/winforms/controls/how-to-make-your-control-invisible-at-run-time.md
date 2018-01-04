---
title: "방법: 런타임에 컨트롤 숨기기"
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
helpviewer_keywords:
- controls [Windows Forms], making invisible at run time
- invisible controls
- user controls [Windows Forms], invisible
- custom controls [Windows Forms], invisible
- run time [Windows Forms], making controls invisible
ms.assetid: 69eb2e72-32f5-4f79-a157-c2c5f60c1628
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6e28a682c6f3bfc52a293daebeade960c1875bb5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-make-your-control-invisible-at-run-time"></a><span data-ttu-id="68152-102">방법: 런타임에 컨트롤 숨기기</span><span class="sxs-lookup"><span data-stu-id="68152-102">How to: Make Your Control Invisible at Run Time</span></span>
<span data-ttu-id="68152-103">런타임 시 표시 되지 않는 사용자 정의 컨트롤 만들기 하려는 경우 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68152-103">There are times when you might want to create a user control that is invisible at run time.</span></span> <span data-ttu-id="68152-104">예를 들어 알람 시계에 있는 컨트롤은 경보를 울릴 제외 하 고 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68152-104">For example, a control that is an alarm clock might be invisible except when the alarm was sounding.</span></span> <span data-ttu-id="68152-105">설정 하 여 쉽게 이렇게는 <xref:System.Windows.Forms.Control.Visible%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="68152-105">This is easily accomplished by setting the <xref:System.Windows.Forms.Control.Visible%2A> property.</span></span> <span data-ttu-id="68152-106">경우는 <xref:System.Windows.Forms.Control.Visible%2A> 속성은 `true`, 컨트롤을 정상적으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68152-106">If the <xref:System.Windows.Forms.Control.Visible%2A> property is `true`, your control will appear as normal.</span></span> <span data-ttu-id="68152-107">경우 `false`, 컨트롤에 표시 되지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="68152-107">If `false`, your control will be hidden.</span></span> <span data-ttu-id="68152-108">컨트롤의 코드 숨겨진 동안 계속 실행 될 수 있습니다 하지만 사용자 인터페이스를 통해 컨트롤과 상호 작용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="68152-108">Although code in your control may still run while invisible, you will not be able to interact with the control through the user interface.</span></span> <span data-ttu-id="68152-109">사용자 입력 (예: 마우스 클릭)에 계속 응답 보이지 않는 컨트롤을 만들려는 경우에 투명 한 컨트롤을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68152-109">If you want to create an invisible control that still responds to user input (for example, mouse clicks), you should create a transparent control.</span></span> <span data-ttu-id="68152-110">자세한 내용은 참조 [컨트롤에 투명 한 배경을 지정](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="68152-110">For more information, see [Giving Your Control a Transparent Background](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md).</span></span>  
  
### <a name="to-make-your-control-invisible-at-run-time"></a><span data-ttu-id="68152-111">런타임 시 컨트롤을 보이지 않도록 하려면</span><span class="sxs-lookup"><span data-stu-id="68152-111">To make your control invisible at run time</span></span>  
  
1.  <span data-ttu-id="68152-112"><xref:System.Windows.Forms.Control.Visible%2A> 속성을 `false`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="68152-112">Set the <xref:System.Windows.Forms.Control.Visible%2A> property to `false`.</span></span>  
  
    ```vb  
    ' To set the Visible property from within your object's own code.  
    Me.Visible = False  
    ' To set the Visible property from another object.  
    myControl1.Visible = False  
    ```  
  
    ```csharp  
    // To set the Visible property from within your object's own code.  
    this.Visible = false;  
    // To set the Visible property from another object.  
    myControl1.Visible = false;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="68152-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="68152-113">See Also</span></span>  
 <xref:System.Windows.Forms.Control.Visible%2A>  
 [<span data-ttu-id="68152-114">.NET Framework에서 사용자 지정 Windows Forms 컨트롤 개발</span><span class="sxs-lookup"><span data-stu-id="68152-114">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [<span data-ttu-id="68152-115">방법: 컨트롤에 투명한 배경 적용</span><span class="sxs-lookup"><span data-stu-id="68152-115">How to: Give Your Control a Transparent Background</span></span>](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)
