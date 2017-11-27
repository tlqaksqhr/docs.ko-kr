---
title: "펜을 사용하여 선과 도형 그리기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pens
- examples [Windows Forms], drawing lines and shapes
- examples [Windows Forms], pens
- drawing
ms.assetid: 8a7542ab-3e9e-443f-8405-2d6053528e20
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0913dc2745e1b244e4b03c0e6b946441a401c5b1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="using-a-pen-to-draw-lines-and-shapes"></a><span data-ttu-id="fdf7d-102">펜을 사용하여 선과 도형 그리기</span><span class="sxs-lookup"><span data-stu-id="fdf7d-102">Using a Pen to Draw Lines and Shapes</span></span>
<span data-ttu-id="fdf7d-103">사용 하 여 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] `Pen` 개체를 선 세그먼트, 곡선 및 도형 윤곽선을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="fdf7d-103">Use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] `Pen` objects to draw line segments, curves, and the outlines of shapes.</span></span> <span data-ttu-id="fdf7d-104">이 섹션에서는 *줄* 선분만 의미를 지정 하지 않는 한, 이러한 항목 중 하나를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdf7d-104">In this section, *line* refers to any of these, unless specified to mean only a line segment.</span></span> <span data-ttu-id="fdf7d-105">색, 너비, 맞춤 및 해당 펜을 사용 하 여 그리는 선의 스타일을 제어 하는 펜의 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdf7d-105">Set the properties of a pen to control the color, width, alignment, and style of lines drawn with that pen.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fdf7d-106">단원 내용</span><span class="sxs-lookup"><span data-stu-id="fdf7d-106">In This Section</span></span>  
 [<span data-ttu-id="fdf7d-107">방법: 펜을 사용하여 선 그리기</span><span class="sxs-lookup"><span data-stu-id="fdf7d-107">How to: Use a Pen to Draw Lines</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-a-pen-to-draw-lines.md)  
 <span data-ttu-id="fdf7d-108">선을 그리는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdf7d-108">Explains how to draw lines.</span></span>  
  
 [<span data-ttu-id="fdf7d-109">방법: 펜을 사용하여 사각형 그리기</span><span class="sxs-lookup"><span data-stu-id="fdf7d-109">How to: Use a Pen to Draw Rectangles</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-a-pen-to-draw-rectangles.md)  
 <span data-ttu-id="fdf7d-110">사각형을 그리는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdf7d-110">Describes how to draw rectangles.</span></span>  
  
 [<span data-ttu-id="fdf7d-111">방법: 펜 굵기 및 맞춤 설정</span><span class="sxs-lookup"><span data-stu-id="fdf7d-111">How to: Set Pen Width and Alignment</span></span>](../../../../docs/framework/winforms/advanced/how-to-set-pen-width-and-alignment.md)  
 <span data-ttu-id="fdf7d-112">너비 및 맞춤을 변경 하는 방법에 설명 된 `Pen` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="fdf7d-112">Explains how to change the width and alignment of a `Pen` object.</span></span>  
  
 [<span data-ttu-id="fdf7d-113">방법: 선 끝이 있는 선 그리기</span><span class="sxs-lookup"><span data-stu-id="fdf7d-113">How to: Draw a Line with Line Caps</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-line-with-line-caps.md)  
 <span data-ttu-id="fdf7d-114">선을 그릴 때 엔드 캡을 추가 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdf7d-114">Describes how to add end caps when drawing a line.</span></span>  
  
 [<span data-ttu-id="fdf7d-115">방법: 선 조인</span><span class="sxs-lookup"><span data-stu-id="fdf7d-115">How to: Join Lines</span></span>](../../../../docs/framework/winforms/advanced/how-to-join-lines.md)  
 <span data-ttu-id="fdf7d-116">두 줄을 조인 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fdf7d-116">Shows how to join two lines.</span></span>  
  
 [<span data-ttu-id="fdf7d-117">방법: 사용자 지정 파선 그리기</span><span class="sxs-lookup"><span data-stu-id="fdf7d-117">How to: Draw a Custom Dashed Line</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-custom-dashed-line.md)  
 <span data-ttu-id="fdf7d-118">파선된 선을 그리는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdf7d-118">Describes how to draw a dashed line.</span></span>  
  
 [<span data-ttu-id="fdf7d-119">방법: 질감으로 채워진 선 그리기</span><span class="sxs-lookup"><span data-stu-id="fdf7d-119">How to: Draw a Line Filled with a Texture</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-line-filled-with-a-texture.md)  
 <span data-ttu-id="fdf7d-120">질감으로 채워진 선 그리기 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdf7d-120">Explains how to draw a texture-filled line.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="fdf7d-121">참조</span><span class="sxs-lookup"><span data-stu-id="fdf7d-121">Reference</span></span>  
 <xref:System.Drawing.Pen>  
 <span data-ttu-id="fdf7d-122">이 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="fdf7d-122">Describes this class and has links to all its members.</span></span>
