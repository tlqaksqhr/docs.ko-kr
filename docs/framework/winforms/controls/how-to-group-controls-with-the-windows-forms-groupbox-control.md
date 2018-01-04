---
title: "방법: Windows Forms GroupBox 컨트롤을 사용하여 컨트롤 그룹화"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], grouping
- GroupBox control [Windows Forms], grouping controls
- Windows Forms controls, grouping
ms.assetid: 0bda316d-bd2a-43aa-ac73-342453303169
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7ecdb7b8682b13f93f59d1de21552abfa91b8f50
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-group-controls-with-the-windows-forms-groupbox-control"></a><span data-ttu-id="04041-102">방법: Windows Forms GroupBox 컨트롤을 사용하여 컨트롤 그룹화</span><span class="sxs-lookup"><span data-stu-id="04041-102">How to: Group Controls with the Windows Forms GroupBox Control</span></span>
<span data-ttu-id="04041-103">Windows Forms <xref:System.Windows.Forms.GroupBox> 컨트롤은 다른 컨트롤을 그룹화 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04041-103">Windows Forms <xref:System.Windows.Forms.GroupBox> controls are used to group other controls.</span></span> <span data-ttu-id="04041-104">컨트롤을 그룹화 하는 방법은 세 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04041-104">There are three reasons to group controls:</span></span>  
  
-   <span data-ttu-id="04041-105">그룹을 만들고 visual 관련 된 일반 사용자 인터페이스에 대 한 폼 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="04041-105">To create a visual grouping of related form elements for a clear user interface.</span></span>  
  
-   <span data-ttu-id="04041-106">그룹화 하려면 프로그래밍 방식으로 (예: 라디오 단추).</span><span class="sxs-lookup"><span data-stu-id="04041-106">To create programmatic grouping (of radio buttons, for example).</span></span>  
  
-   <span data-ttu-id="04041-107">에 컨트롤을 디자인 타임에 하나의 단위로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="04041-107">For moving the controls as a unit at design time.</span></span>  
  
### <a name="to-create-a-group-of-controls"></a><span data-ttu-id="04041-108">컨트롤의 그룹을 만들려면</span><span class="sxs-lookup"><span data-stu-id="04041-108">To create a group of controls</span></span>  
  
1.  <span data-ttu-id="04041-109">그리기는 <xref:System.Windows.Forms.GroupBox> 양식에 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="04041-109">Draw a <xref:System.Windows.Forms.GroupBox> control on a form.</span></span>  
  
2.  <span data-ttu-id="04041-110">그룹 상자 안에서 각 그리기 그룹 상자에 다른 컨트롤을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="04041-110">Add other controls to the group box, drawing each inside the group box.</span></span>  
  
     <span data-ttu-id="04041-111">그룹 상자에서 포함 하려는 기존 컨트롤을 설정한 경우에 모든 컨트롤에 선택 클립보드에 잘라낸 수 있습니다는 <xref:System.Windows.Forms.GroupBox> 컨트롤을 선택한 다음 그룹 상자에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="04041-111">If you have existing controls that you want to enclose in a group box, you can select all the controls, cut them to the Clipboard, select the <xref:System.Windows.Forms.GroupBox> control, and then paste them into the group box.</span></span> <span data-ttu-id="04041-112">그룹 상자에 직접를 끌어 올 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04041-112">You can also drag them into the group box.</span></span>  
  
3.  <span data-ttu-id="04041-113">설정의 <xref:System.Windows.Forms.GroupBox.Text%2A> 속성을 적절 한 캡션에 그룹 상자의 합니다.</span><span class="sxs-lookup"><span data-stu-id="04041-113">Set the <xref:System.Windows.Forms.GroupBox.Text%2A> property of the group box to an appropriate caption.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04041-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="04041-114">See Also</span></span>  
 <xref:System.Windows.Forms.GroupBox>  
 [<span data-ttu-id="04041-115">GroupBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="04041-115">GroupBox Control</span></span>](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md)
