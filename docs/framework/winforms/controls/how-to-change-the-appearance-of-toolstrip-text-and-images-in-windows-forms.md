---
title: "방법: Windows Forms에서 ToolStrip 텍스트 및 이미지의 모양 변경"
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
- ToolStrip control [Windows Forms], appearance
- toolbars [Windows Forms], images
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], appearance
- ToolStrip control [Windows Forms], images
- ToolStrip control [Windows Forms], text
- toolbars [Windows Forms], text
ms.assetid: d62dc9d1-2edd-4dfa-aed7-1335d6e13d86
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fe88ff8d31a83b8516b11cd9aadd4bc2d4bf99a9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-appearance-of-toolstrip-text-and-images-in-windows-forms"></a><span data-ttu-id="d65c4-102">방법: Windows Forms에서 ToolStrip 텍스트 및 이미지의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="d65c4-102">How to: Change the Appearance of ToolStrip Text and Images in Windows Forms</span></span>
<span data-ttu-id="d65c4-103">텍스트 및 이미지에 표시 되는지 여부를 제어할 수 있습니다는 <xref:System.Windows.Forms.ToolStripItem> 서로 기준으로 정렬 되는 방법 및 및 <xref:System.Windows.Forms.ToolStrip>합니다.</span><span class="sxs-lookup"><span data-stu-id="d65c4-103">You can control whether text and images are displayed on a <xref:System.Windows.Forms.ToolStripItem> and how they are aligned relative to each other and the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
### <a name="to-define-what-is-displayed-on-a-toolstripitem"></a><span data-ttu-id="d65c4-104">ToolStripItem에 표시 되는 항목을 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="d65c4-104">To define what is displayed on a ToolStripItem</span></span>  
  
-   <span data-ttu-id="d65c4-105">설정의 <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> 속성을 원하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d65c4-105">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property to the desired value.</span></span> <span data-ttu-id="d65c4-106">이 속성은 `Image`, `ImageAndText`, `None`, 및 `Text`합니다.</span><span class="sxs-lookup"><span data-stu-id="d65c4-106">The possibilities are `Image`, `ImageAndText`, `None`, and `Text`.</span></span> <span data-ttu-id="d65c4-107">기본값은 `ImageAndText`입니다.</span><span class="sxs-lookup"><span data-stu-id="d65c4-107">The default is `ImageAndText`.</span></span>  
  
    ```vb  
    ToolStripButton2.DisplayStyle = _  
        System.Windows.Forms.ToolStripItemDisplayStyle.Image  
    ```  
  
    ```csharp  
    toolStripButton2.DisplayStyle = System.Windows.Forms.ToolStripItemDisplayStyle.Image;  
    ```  
  
### <a name="to-align-text-on-a-toolstripitem"></a><span data-ttu-id="d65c4-108">ToolStripItem에 텍스트를 맞추는</span><span class="sxs-lookup"><span data-stu-id="d65c4-108">To align text on a ToolStripItem</span></span>  
  
-   <span data-ttu-id="d65c4-109">설정의 <xref:System.Windows.Forms.ToolStripItem.TextAlign%2A> 속성을 원하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d65c4-109">Set the <xref:System.Windows.Forms.ToolStripItem.TextAlign%2A> property to the desired value.</span></span> <span data-ttu-id="d65c4-110">이 속성은 위쪽, 가운데 및 아래쪽, 왼쪽, 가운데 및 오른쪽으로의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="d65c4-110">The possibilities are any combination of top, middle, and bottom with left, center, and right.</span></span> <span data-ttu-id="d65c4-111">기본값은 `MiddleCenter`입니다.</span><span class="sxs-lookup"><span data-stu-id="d65c4-111">The default is `MiddleCenter`.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.TextAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.TextAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-align-an-image-on-a-toolstripitem"></a><span data-ttu-id="d65c4-112">ToolStripItem에 있는 이미지에 맞게</span><span class="sxs-lookup"><span data-stu-id="d65c4-112">To align an image on a ToolStripItem</span></span>  
  
-   <span data-ttu-id="d65c4-113">설정의 <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A> 속성을 원하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d65c4-113">Set the <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A> property to the desired value.</span></span> <span data-ttu-id="d65c4-114">이 속성은 위쪽, 가운데 및 아래쪽, 왼쪽, 가운데 및 오른쪽으로의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="d65c4-114">The possibilities are any combination of top, middle, and bottom with left, center, and right.</span></span> <span data-ttu-id="d65c4-115">기본값은 `MiddleLeft`입니다.</span><span class="sxs-lookup"><span data-stu-id="d65c4-115">The default is `MiddleLeft`.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.ImageAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.ImageAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-define-how-toolstripitem-text-and-images-are-displayed-relative-to-each-other"></a><span data-ttu-id="d65c4-116">ToolStripItem 텍스트 및 이미지를 서로 맞춰 표시 되는 방법을 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="d65c4-116">To define how ToolStripItem text and images are displayed relative to each other</span></span>  
  
-   <span data-ttu-id="d65c4-117">설정의 <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> 속성을 원하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d65c4-117">Set the <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> property to the desired value.</span></span> <span data-ttu-id="d65c4-118">이 속성은 `ImageAboveText`, `ImageBeforeText`, `Overlay`, `TextAboveImage`, 및 `TextBeforeImage`합니다.</span><span class="sxs-lookup"><span data-stu-id="d65c4-118">The possibilities are `ImageAboveText`, `ImageBeforeText`, `Overlay`, `TextAboveImage`, and `TextBeforeImage`.</span></span> <span data-ttu-id="d65c4-119">기본값은 `ImageBeforeText`입니다.</span><span class="sxs-lookup"><span data-stu-id="d65c4-119">The default is `ImageBeforeText`.</span></span>  
  
    ```vb  
    ToolStripButton1.TextImageRelation = _  
        System.Windows.Forms.TextImageRelation.ImageAboveText  
    ```  
  
    ```csharp  
    toolStripButton1.TextImageRelation = System.Windows.Forms.TextImageRelation.ImageAboveText;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d65c4-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d65c4-120">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip>  
 [<span data-ttu-id="d65c4-121">ToolStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="d65c4-121">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [<span data-ttu-id="d65c4-122">ToolStrip 컨트롤 아키텍처</span><span class="sxs-lookup"><span data-stu-id="d65c4-122">ToolStrip Control Architecture</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [<span data-ttu-id="d65c4-123">ToolStrip 기술 요약</span><span class="sxs-lookup"><span data-stu-id="d65c4-123">ToolStrip Technology Summary</span></span>](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
