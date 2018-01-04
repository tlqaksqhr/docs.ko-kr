---
title: "방법: 내용에 맞게 Windows Forms Label 컨트롤 크기 조정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- captions [Windows Forms], sizing
- sizing controls
- size [Windows Forms], controls
- labels [Windows Forms], sizing to fit contents
- Label control [Windows Forms], sizing to fit contents
ms.assetid: 99648964-63b2-438c-980e-d24103ad602b
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a2c34506ca33af80b83f365893e56a5a9d437b89
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-size-a-windows-forms-label-control-to-fit-its-contents"></a><span data-ttu-id="d8b14-102">방법: 내용에 맞게 Windows Forms Label 컨트롤 크기 조정</span><span class="sxs-lookup"><span data-stu-id="d8b14-102">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>
<span data-ttu-id="d8b14-103">Windows Forms <xref:System.Windows.Forms.Label> 또는 여러 줄 컨트롤이 될 수 있으며 자동으로 크기를 조정할 수의 캡션을 맞게 자동 하거나 크기에서 고정 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8b14-103">The Windows Forms <xref:System.Windows.Forms.Label> control can be single-line or multi-line, and it can be either fixed in size or can automatically resize itself to accommodate its caption.</span></span> <span data-ttu-id="d8b14-104"><xref:System.Windows.Forms.Label.AutoSize%2A> 속성을 사용 하면를 캡션에 맞게 컨트롤 크기 조정 되는 런타임 시 캡션이 변경 하는 경우에 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b14-104">The <xref:System.Windows.Forms.Label.AutoSize%2A> property helps you size the controls to fit larger or smaller captions, which is particularly useful if the caption will change at run time.</span></span>  
  
### <a name="to-make-a-label-control-resize-dynamically-to-fit-its-contents"></a><span data-ttu-id="d8b14-105">내용에 맞게 동적으로 조정 레이블 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="d8b14-105">To make a label control resize dynamically to fit its contents</span></span>  
  
1.  <span data-ttu-id="d8b14-106">설정의 <xref:System.Windows.Forms.Label.AutoSize%2A> 속성을 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b14-106">Set its <xref:System.Windows.Forms.Label.AutoSize%2A> property to `true`.</span></span>  
  
 <span data-ttu-id="d8b14-107">경우 <xref:System.Windows.Forms.Label.AutoSize%2A> 로 설정 된 `false`, 지정 된 단어는 <xref:System.Windows.Forms.Label.Text%2A> 속성은 가능한 경우 다음 줄으로 줄 바꿈이 되지만 컨트롤 증가 하지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d8b14-107">If <xref:System.Windows.Forms.Label.AutoSize%2A> is set to `false`, the words specified in the <xref:System.Windows.Forms.Label.Text%2A> property will wrap to the next line if possible, but the control will not grow.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8b14-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d8b14-108">See Also</span></span>  
 [<span data-ttu-id="d8b14-109">방법: Windows Forms Label 컨트롤을 사용하여 선택키 만들기</span><span class="sxs-lookup"><span data-stu-id="d8b14-109">How to: Create Access Keys with Windows Forms Label Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md)  
 [<span data-ttu-id="d8b14-110">Label 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="d8b14-110">Label Control Overview</span></span>](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)  
 [<span data-ttu-id="d8b14-111">레이블 컨트롤</span><span class="sxs-lookup"><span data-stu-id="d8b14-111">Label Control</span></span>](../../../../docs/framework/winforms/controls/label-control-windows-forms.md)
