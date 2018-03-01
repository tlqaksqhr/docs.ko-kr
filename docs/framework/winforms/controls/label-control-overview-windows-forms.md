---
title: "Label 컨트롤 개요(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Label
helpviewer_keywords:
- images [Windows Forms], displaying in labels
- labels
- Label control [Windows Forms], about Label control
ms.assetid: dcad7f44-11b7-4c55-b0c0-d984ade43d7d
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f68642eb5f996722097976e042006afbf366ae39
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="label-control-overview-windows-forms"></a><span data-ttu-id="8ebb9-102">Label 컨트롤 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="8ebb9-102">Label Control Overview (Windows Forms)</span></span>
<span data-ttu-id="8ebb9-103">Windows Forms <xref:System.Windows.Forms.Label> 컨트롤은 텍스트 또는 사용자가 편집할 수 없는 이미지를 표시 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ebb9-103">Windows Forms <xref:System.Windows.Forms.Label> controls are used to display text or images that cannot be edited by the user.</span></span> <span data-ttu-id="8ebb9-104">양식에서 개체를 식별 하는 데 사용 됩니다-컨트롤에 대 한 설명을 처리 해를 클릭 한 경우 예를 들어 제공 하거나 런타임에 이벤트 또는 응용 프로그램에서 프로세스에 대 한 응답에 정보를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ebb9-104">They are used to identify objects on a form — to provide a description of what a certain control will do if clicked, for example, or to display information in response to a run-time event or process in your application.</span></span> <span data-ttu-id="8ebb9-105">예를 들어 텍스트 상자, 목록 상자, 콤보 상자, 및 등을 설명 캡션을 추가할 레이블을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ebb9-105">For example, you can use labels to add descriptive captions to text boxes, list boxes, combo boxes, and so on.</span></span> <span data-ttu-id="8ebb9-106">이벤트에 대 한 응답에는 레이블에 의해 런타임에 표시 되는 텍스트를 변경 하는 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ebb9-106">You can also write code that changes the text displayed by a label in response to events at run time.</span></span> <span data-ttu-id="8ebb9-107">예를 들어 응용 프로그램 변수를 사용할 경우 변경 내용을 처리 하는 데 몇 분 정도 진행 상태 메시지 레이블에 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ebb9-107">For example, if your application takes a few minutes to process a change, you can display a processing-status message in a label.</span></span>  
  
## <a name="working-with-the-label-control"></a><span data-ttu-id="8ebb9-108">레이블 컨트롤</span><span class="sxs-lookup"><span data-stu-id="8ebb9-108">Working with the Label Control</span></span>  
 <span data-ttu-id="8ebb9-109">때문에 <xref:System.Windows.Forms.Label> 컨트롤이 포커스를 받을 수 없습니다, 다른 컨트롤에 대 한 선택 키를 만드는 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ebb9-109">Because the <xref:System.Windows.Forms.Label> control cannot receive the focus, it can also be used to create access keys for other controls.</span></span> <span data-ttu-id="8ebb9-110">사용자를을 함께 ALT 키를 눌러 다른 컨트롤을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ebb9-110">An access key allows a user to select the other control by pressing the ALT key with the access key.</span></span> <span data-ttu-id="8ebb9-111">자세한 내용은 참조 [만드는 액세스 키에 대 한 Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md) 및 [하는 방법: Windows Forms Label 컨트롤 선택 키 만들기](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8ebb9-111">For more information, see [Creating Access Keys for Windows Forms Controls](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md) and [How to: Create Access Keys with Windows Forms Label Controls](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md).</span></span>  
  
 <span data-ttu-id="8ebb9-112">에 포함 된 레이블에 표시 되는 캡션을 <xref:System.Windows.Forms.Label.Text%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="8ebb9-112">The caption displayed in the label is contained in the <xref:System.Windows.Forms.Label.Text%2A> property.</span></span> <span data-ttu-id="8ebb9-113"><xref:System.Windows.Forms.Label.TextAlign%2A> 속성 레이블 내에서 텍스트의 맞춤을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ebb9-113">The <xref:System.Windows.Forms.Label.TextAlign%2A> property allows you to set the alignment of the text within the label.</span></span> <span data-ttu-id="8ebb9-114">자세한 내용은 참조 [하는 방법: Windows Forms 컨트롤에서 텍스트 표시 설정](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8ebb9-114">For more information, see [How to: Set the Text Displayed by a Windows Forms Control](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ebb9-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8ebb9-115">See Also</span></span>  
 <xref:System.Windows.Forms.Label>  
 [<span data-ttu-id="8ebb9-116">방법: 내용에 맞게 Windows Forms Label 컨트롤 크기 조정</span><span class="sxs-lookup"><span data-stu-id="8ebb9-116">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>](../../../../docs/framework/winforms/controls/how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)  
 [<span data-ttu-id="8ebb9-117">방법: Windows Forms Label 컨트롤을 사용하여 선택키 만들기</span><span class="sxs-lookup"><span data-stu-id="8ebb9-117">How to: Create Access Keys with Windows Forms Label Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md)
