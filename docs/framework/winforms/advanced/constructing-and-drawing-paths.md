---
title: "경로 구성 및 그리기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- paths [Windows Forms], drawing
- drawing paths [Windows Forms]
- graphics paths [Windows Forms], creating
- graphics paths [Windows Forms], drawing
- examples [Windows Forms], drawing paths
ms.assetid: f16ec921-56cf-46d1-9741-d7316ad06b23
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 50d1952632b29450a441d3cf0c7d66bffc000ea5
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="constructing-and-drawing-paths"></a><span data-ttu-id="7c972-102">경로 구성 및 그리기</span><span class="sxs-lookup"><span data-stu-id="7c972-102">Constructing and Drawing Paths</span></span>
<span data-ttu-id="7c972-103">경로 시퀀스의 기본 그래픽 (선, 사각형, 곡선, 텍스트 및 like)를 조작 하 고 하나의 단위로 그릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c972-103">A path is a sequence of graphics primitives (lines, rectangles, curves, text, and the like) that can be manipulated and drawn as a single unit.</span></span> <span data-ttu-id="7c972-104">경로 나눌 수 있으며 *수치* 열려 있거나 닫힌 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c972-104">A path can be divided into *figures* that are either open or closed.</span></span> <span data-ttu-id="7c972-105">도형 여러 기본 요소를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c972-105">A figure can contain several primitives.</span></span>  
  
 <span data-ttu-id="7c972-106">호출 하 여 패스를 그릴 수는 <xref:System.Drawing.Graphics.DrawPath%2A> 의 메서드는 <xref:System.Drawing.Graphics> 클래스를 호출 하 여 경로 채울 수는 <xref:System.Drawing.Graphics.FillPath%2A> 의 메서드는 <xref:System.Drawing.Graphics> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="7c972-106">You can draw a path by calling the <xref:System.Drawing.Graphics.DrawPath%2A> method of the <xref:System.Drawing.Graphics> class, and you can fill a path by calling the <xref:System.Drawing.Graphics.FillPath%2A> method of the <xref:System.Drawing.Graphics> class.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7c972-107">단원 내용</span><span class="sxs-lookup"><span data-stu-id="7c972-107">In This Section</span></span>  
 [<span data-ttu-id="7c972-108">방법: 선, 곡선 및 도형으로 그림 만들기</span><span class="sxs-lookup"><span data-stu-id="7c972-108">How to: Create Figures from Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-figures-from-lines-curves-and-shapes.md)  
 <span data-ttu-id="7c972-109">사용 하는 방법을 보여 줍니다.는 <xref:System.Drawing.Drawing2D.GraphicsPath> 에 그림을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7c972-109">Shows how to use a <xref:System.Drawing.Drawing2D.GraphicsPath> to create figures.</span></span>  
  
 [<span data-ttu-id="7c972-110">방법: 열린 그림 채우기</span><span class="sxs-lookup"><span data-stu-id="7c972-110">How to: Fill Open Figures</span></span>](../../../../docs/framework/winforms/advanced/how-to-fill-open-figures.md)  
 <span data-ttu-id="7c972-111">작성 하는 방법에 설명 된 <xref:System.Drawing.Drawing2D.GraphicsPath>합니다.</span><span class="sxs-lookup"><span data-stu-id="7c972-111">Explains how to fill a <xref:System.Drawing.Drawing2D.GraphicsPath>.</span></span>  
  
 [<span data-ttu-id="7c972-112">방법: 구부러진 경로를 선으로 펴기</span><span class="sxs-lookup"><span data-stu-id="7c972-112">How to: Flatten a Curved Path into a Line</span></span>](../../../../docs/framework/winforms/advanced/how-to-flatten-a-curved-path-into-a-line.md)  
 <span data-ttu-id="7c972-113">평면화 하는 방법을 보여 줍니다는 <xref:System.Drawing.Drawing2D.GraphicsPath>합니다.</span><span class="sxs-lookup"><span data-stu-id="7c972-113">Shows how to flatten a <xref:System.Drawing.Drawing2D.GraphicsPath>.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="7c972-114">참조</span><span class="sxs-lookup"><span data-stu-id="7c972-114">Reference</span></span>  
 <xref:System.Drawing.Drawing2D.GraphicsPath>  
 <span data-ttu-id="7c972-115">이 클래스를 설명 하 고 모든 해당 멤버의 링크를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c972-115">Describes this class and contains links to all of its members.</span></span>
