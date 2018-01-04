---
title: "방법: 합성 모드를 사용하여 알파 혼합 조절"
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
- alpha blending [Windows Forms], compositing
- colors [Windows Forms], blending
- colors [Windows Forms], controlling transparency
ms.assetid: f331df2d-b395-4b0a-95be-24fec8c9bbb5
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 40461ddb3fdae8076df5290afe669a8eca9f6a8d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-compositing-mode-to-control-alpha-blending"></a><span data-ttu-id="48385-102">방법: 합성 모드를 사용하여 알파 혼합 조절</span><span class="sxs-lookup"><span data-stu-id="48385-102">How to: Use Compositing Mode to Control Alpha Blending</span></span>
<span data-ttu-id="48385-103">다음과 같은 특성을 가진 오프 스크린 비트맵을 만들려고 하는 경우가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48385-103">There may be times when you want to create an off-screen bitmap that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="48385-104">색 한 알파 값으로 255 보다 작아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48385-104">Colors have alpha values that are less than 255.</span></span>  
  
-   <span data-ttu-id="48385-105">색은 알파 혼합 비트맵을 만들면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48385-105">Colors are not alpha blended with each other as you create the bitmap.</span></span>  
  
-   <span data-ttu-id="48385-106">완성된 한 비트맵을 표시 하면 비트맵 색이 알파 혼합 디스플레이 장치에서 배경 색입니다.</span><span class="sxs-lookup"><span data-stu-id="48385-106">When you display the finished bitmap, colors in the bitmap are alpha blended with the background colors on the display device.</span></span>  
  
 <span data-ttu-id="48385-107">이러한 비트맵을 만들려면 빈 생성 <xref:System.Drawing.Bitmap> 개체를 생성 한 다음는 <xref:System.Drawing.Graphics> 해당 비트맵을 기반으로 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="48385-107">To create such a bitmap, construct a blank <xref:System.Drawing.Bitmap> object, and then construct a <xref:System.Drawing.Graphics> object based on that bitmap.</span></span> <span data-ttu-id="48385-108">합성 모드 설정에서 <xref:System.Drawing.Graphics> 개체 <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="48385-108">Set the compositing mode of the <xref:System.Drawing.Graphics> object to <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48385-109">예</span><span class="sxs-lookup"><span data-stu-id="48385-109">Example</span></span>  
 <span data-ttu-id="48385-110">다음 예제에서는 한 <xref:System.Drawing.Graphics> 기반 개체는 <xref:System.Drawing.Bitmap> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="48385-110">The following example creates a <xref:System.Drawing.Graphics> object based on a <xref:System.Drawing.Bitmap> object.</span></span> <span data-ttu-id="48385-111">코드를 사용 하 여는 <xref:System.Drawing.Graphics> 개체와 두 개의 반투명 브러시 (알파 160 =) 페인트 하는 비트맵을 합니다.</span><span class="sxs-lookup"><span data-stu-id="48385-111">The code uses the <xref:System.Drawing.Graphics> object along with two semitransparent brushes (alpha = 160) to paint on the bitmap.</span></span> <span data-ttu-id="48385-112">코드에는 빨간색 타원과 반투명 브러시를 사용 하 여 녹색 타원을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="48385-112">The code fills a red ellipse and a green ellipse using the semitransparent brushes.</span></span> <span data-ttu-id="48385-113">녹색 타원 겹치는 빨간색 타원 하지만 때문에 녹색에서 빨간색 혼합 되지는 않습니다의 합성 모드는 <xref:System.Drawing.Graphics> 개체로 설정 되어 <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy>합니다.</span><span class="sxs-lookup"><span data-stu-id="48385-113">The green ellipse overlaps the red ellipse, but the green is not blended with the red because the compositing mode of the <xref:System.Drawing.Graphics> object is set to <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy>.</span></span>  
  
 <span data-ttu-id="48385-114">코드는 화면에 두 번 비트맵을 그립니다: 한 번 흰색 배경 기반 및 컬러 배경에 한 번입니다.</span><span class="sxs-lookup"><span data-stu-id="48385-114">The code draws the bitmap on the screen twice: once on a white background and once on a multicolored background.</span></span> <span data-ttu-id="48385-115">두 타원의 일부인 경우 비트맵의 픽셀 160, 알파 구성 요소가 없으므로 줄임표는 화면의 배경색 배경색과 혼합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48385-115">The pixels in the bitmap that are part of the two ellipses have an alpha component of 160, so the ellipses are blended with the background colors on the screen.</span></span>  
  
 <span data-ttu-id="48385-116">다음 그림에서는 코드 예제의 출력을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="48385-116">The following illustration shows the output of the code example.</span></span> <span data-ttu-id="48385-117">Note 줄임표, 배경색과 혼합 됩니다 하지만 서로 혼합 된 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="48385-117">Note that the ellipses are blended with the background, but they are not blended with each other.</span></span>  
  
 <span data-ttu-id="48385-118">![복사 원본](../../../../docs/framework/winforms/advanced/media/sourcecopy.png "sourcecopy")</span><span class="sxs-lookup"><span data-stu-id="48385-118">![Source Copy](../../../../docs/framework/winforms/advanced/media/sourcecopy.png "sourcecopy")</span></span>  
  
 <span data-ttu-id="48385-119">코드 예제에서는이 문이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48385-119">The code example contains this statement:</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.AlphaBlending#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#41)]  
  
 <span data-ttu-id="48385-120">백그라운드 뿐 아니라 서로 혼합 타원을 하려는 경우 해당 문을 다음과 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48385-120">If you want the ellipses to be blended with each other as well as with the background, change that statement to the following:</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.AlphaBlending#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#42)]  
  
 <span data-ttu-id="48385-121">다음 그림에서는 수정 된 코드의 출력을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="48385-121">The following illustration shows the output of the revised code.</span></span>  
  
 <span data-ttu-id="48385-122">![통해 소스](../../../../docs/framework/winforms/advanced/media/sourceover.png "sourceover")</span><span class="sxs-lookup"><span data-stu-id="48385-122">![Source Over](../../../../docs/framework/winforms/advanced/media/sourceover.png "sourceover")</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#43)]
 [!code-vb[System.Drawing.AlphaBlending#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#43)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="48385-123">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="48385-123">Compiling the Code</span></span>  
 <span data-ttu-id="48385-124">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventArgs>의 매개 변수인 `e`<xref:System.Windows.Forms.PaintEventHandler>가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="48385-124">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48385-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="48385-125">See Also</span></span>  
 <xref:System.Drawing.Color.FromArgb%2A>  
 [<span data-ttu-id="48385-126">선 및 채우기 알파 혼합</span><span class="sxs-lookup"><span data-stu-id="48385-126">Alpha Blending Lines and Fills</span></span>](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)
