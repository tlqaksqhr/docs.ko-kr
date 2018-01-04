---
title: "선 및 채우기 알파 혼합"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- lines [Windows Forms], adding transparency
- examples [Windows Forms], alpha blending
- alpha blending [Windows Forms], using with lines
- alpha blending
- lines [Windows Forms], alpha blending
- fills [Windows Forms], alpha blending
- alpha blending [Windows Forms], using with fills
- shapes [Windows Forms], adding transparency
ms.assetid: 5440f48c-3ac9-44c3-b170-c1c110bdbab8
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2a46efeccf9ab343ca0da07fad07138bd72e4e44
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="alpha-blending-lines-and-fills"></a><span data-ttu-id="33bba-102">선 및 채우기 알파 혼합</span><span class="sxs-lookup"><span data-stu-id="33bba-102">Alpha Blending Lines and Fills</span></span>
<span data-ttu-id="33bba-103">[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], 색이 알파, 빨간색, 녹색 및 파란색에 대 한 8 비트는 32 비트 값입니다.</span><span class="sxs-lookup"><span data-stu-id="33bba-103">In [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], a color is a 32-bit value with 8 bits each for alpha, red, green, and blue.</span></span> <span data-ttu-id="33bba-104">알파 값 색의 투명도 이면-범위 배경색으로 색 혼합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="33bba-104">The alpha value indicates the transparency of the color — the extent to which the color is blended with the background color.</span></span> <span data-ttu-id="33bba-105">알파 값 범위는 0에서 255까지, 여기서 0 완전히 투명 한 색을 나타내는 경우 255 완전히 불투명 한 색을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="33bba-105">Alpha values range from 0 through 255, where 0 represents a fully transparent color, and 255 represents a fully opaque color.</span></span>  
  
 <span data-ttu-id="33bba-106">알파 혼합 픽셀 단위의 혼합 원본과 배경 색 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="33bba-106">Alpha blending is a pixel-by-pixel blending of source and background color data.</span></span> <span data-ttu-id="33bba-107">각 원본 색의 세 가지 구성 (빨강, 녹색, 파랑)는 다음과 같은 식에 따라 배경색의 해당 구성 요소와 혼합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="33bba-107">Each of the three components (red, green, blue) of a given source color is blended with the corresponding component of the background color according to the following formula:</span></span>  
  
 <span data-ttu-id="33bba-108">displayColor sourceColor × 알파 = 255 / backgroundColor × (255-alpha) + 255 /</span><span class="sxs-lookup"><span data-stu-id="33bba-108">displayColor = sourceColor × alpha / 255 + backgroundColor × (255 – alpha) / 255</span></span>  
  
 <span data-ttu-id="33bba-109">예를 들어 소스 색의 빨간색 구성 요소는 150 및 배경 색의 빨강 구성은 100입니다.</span><span class="sxs-lookup"><span data-stu-id="33bba-109">For example, suppose the red component of the source color is 150 and the red component of the background color is 100.</span></span> <span data-ttu-id="33bba-110">알파 값이 200 이면 생성 된 색의 빨강 구성 다음과 같이 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="33bba-110">If the alpha value is 200, the red component of the resultant color is calculated as follows:</span></span>  
  
 <span data-ttu-id="33bba-111">150 × 200 / 255 + 100 × (255 – 200) / 255 = 139</span><span class="sxs-lookup"><span data-stu-id="33bba-111">150 × 200 / 255 + 100 × (255 – 200) / 255 = 139</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="33bba-112">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="33bba-112">In This Section</span></span>  
 [<span data-ttu-id="33bba-113">방법: 불투명 및 반투명 선 그리기</span><span class="sxs-lookup"><span data-stu-id="33bba-113">How to: Draw Opaque and Semitransparent Lines</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-opaque-and-semitransparent-lines.md)  
 <span data-ttu-id="33bba-114">알파 혼합 선을 그리는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="33bba-114">Shows how to draw alpha-blended lines.</span></span>  
  
 [<span data-ttu-id="33bba-115">방법: 불투명 및 반투명 브러시를 사용하여 그리기</span><span class="sxs-lookup"><span data-stu-id="33bba-115">How to: Draw with Opaque and Semitransparent Brushes</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-with-opaque-and-semitransparent-brushes.md)  
 <span data-ttu-id="33bba-116">브러시에 알파 혼합 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="33bba-116">Explains how to alpha-blend with brushes.</span></span>  
  
 [<span data-ttu-id="33bba-117">방법: 합성 모드를 사용하여 알파 혼합 조절</span><span class="sxs-lookup"><span data-stu-id="33bba-117">How to: Use Compositing Mode to Control Alpha Blending</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-compositing-mode-to-control-alpha-blending.md)  
 <span data-ttu-id="33bba-118">사용 하 여 알파 혼합을 제어 하는 방법을 설명 <xref:System.Drawing.Drawing2D.CompositingMode>합니다.</span><span class="sxs-lookup"><span data-stu-id="33bba-118">Describes how to control alpha blending using <xref:System.Drawing.Drawing2D.CompositingMode>.</span></span>  
  
 [<span data-ttu-id="33bba-119">방법: 색 매트릭스를 사용하여 이미지에 알파 값 설정</span><span class="sxs-lookup"><span data-stu-id="33bba-119">How to: Use a Color Matrix to Set Alpha Values in Images</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-a-color-matrix-to-set-alpha-values-in-images.md)  
 <span data-ttu-id="33bba-120">사용 하는 방법에 설명 된 <xref:System.Drawing.Imaging.ColorMatrix> 알파 혼합을 제어 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="33bba-120">Explains how to use a <xref:System.Drawing.Imaging.ColorMatrix> object to control alpha blending.</span></span>
