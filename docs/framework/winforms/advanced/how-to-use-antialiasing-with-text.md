---
title: "방법: 텍스트에 앤티 앨리어싱 사용"
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
- strings [Windows Forms], smoothing drawn
- antialiasing [Windows Forms], using with text
- text [Windows Forms], smoothing
- text [Windows Forms], antialiasing
- strings [Windows Forms], antialiasing when drawing
ms.assetid: 48fc34f3-f236-4b01-a0cb-f0752e6d22ae
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bb5a57f8bcbdc1edad78dcd48ad495a187bbb44a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-use-antialiasing-with-text"></a><span data-ttu-id="26ce6-102">방법: 텍스트에 앤티 앨리어싱 사용</span><span class="sxs-lookup"><span data-stu-id="26ce6-102">How to: Use Antialiasing with Text</span></span>
<span data-ttu-id="26ce6-103">*앤티 앨리어싱* 그려지는 그래픽 및 텍스트의 모양을 가독성을 향상 시키는 거친 다듬기 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="26ce6-103">*Antialiasing* refers to the smoothing of jagged edges of drawn graphics and text to improve their appearance or readability.</span></span> <span data-ttu-id="26ce6-104">관리 되는 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 클래스, 낮은 품질의 텍스트와 고품질 앤티 앨리어싱된 텍스트를 렌더링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26ce6-104">With the managed [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] classes, you can render high quality antialiased text, as well as lower quality text.</span></span> <span data-ttu-id="26ce6-105">일반적으로 더 높은 품질 렌더링은 낮은 품질로 렌더링할 보다 처리 시간이 오래 합니다.</span><span class="sxs-lookup"><span data-stu-id="26ce6-105">Typically, higher quality rendering takes more processing time than lower quality rendering.</span></span> <span data-ttu-id="26ce6-106">텍스트 품질 수준을 설정 하려면 설정는 <xref:System.Drawing.Graphics.TextRenderingHint%2A> 속성은 <xref:System.Drawing.Graphics> 의 요소 중 하나에 <xref:System.Drawing.Text.TextRenderingHint> 열거형</span><span class="sxs-lookup"><span data-stu-id="26ce6-106">To set the text quality level, set the <xref:System.Drawing.Graphics.TextRenderingHint%2A> property of a <xref:System.Drawing.Graphics> to one of the elements of the <xref:System.Drawing.Text.TextRenderingHint> enumeration</span></span>  
  
## <a name="example"></a><span data-ttu-id="26ce6-107">예제</span><span class="sxs-lookup"><span data-stu-id="26ce6-107">Example</span></span>  
 <span data-ttu-id="26ce6-108">다음 코드 예제에서는 두 개의 다른 품질 설정 사용 하 여 텍스트를 그립니다.</span><span class="sxs-lookup"><span data-stu-id="26ce6-108">The following code example draws text with two different quality settings.</span></span>  
  
 <span data-ttu-id="26ce6-109">다음 그림은 코드의 출력 예제 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="26ce6-109">The following illustration shows the output of the cod example code.</span></span>  
  
 <span data-ttu-id="26ce6-110">![글꼴 텍스트](../../../../docs/framework/winforms/advanced/media/fontstext10.png "FontsText10")</span><span class="sxs-lookup"><span data-stu-id="26ce6-110">![Fonts Text](../../../../docs/framework/winforms/advanced/media/fontstext10.png "FontsText10")</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="26ce6-111">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="26ce6-111">Compiling the Code</span></span>  
 <span data-ttu-id="26ce6-112">이전 코드 예제는 Windows Forms에서 사용 하도록 설계 되었으며 필요 <xref:System.Windows.Forms.PaintEventArgs> `e`의 매개 변수인 <xref:System.Windows.Forms.PaintEventHandler>합니다.</span><span class="sxs-lookup"><span data-stu-id="26ce6-112">The preceding code example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26ce6-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="26ce6-113">See Also</span></span>  
 [<span data-ttu-id="26ce6-114">글꼴 및 텍스트 사용</span><span class="sxs-lookup"><span data-stu-id="26ce6-114">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
