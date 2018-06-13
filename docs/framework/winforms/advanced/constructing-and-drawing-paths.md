---
title: 경로 구성 및 그리기
ms.date: 03/30/2017
helpviewer_keywords:
- paths [Windows Forms], drawing
- drawing paths [Windows Forms]
- graphics paths [Windows Forms], creating
- graphics paths [Windows Forms], drawing
- examples [Windows Forms], drawing paths
ms.assetid: f16ec921-56cf-46d1-9741-d7316ad06b23
ms.openlocfilehash: 120bb3edcf8e35feca37f02dda5148ba4eebd0ea
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33520658"
---
# <a name="constructing-and-drawing-paths"></a><span data-ttu-id="830f7-102">경로 구성 및 그리기</span><span class="sxs-lookup"><span data-stu-id="830f7-102">Constructing and Drawing Paths</span></span>
<span data-ttu-id="830f7-103">경로 시퀀스의 기본 그래픽 (선, 사각형, 곡선, 텍스트 및 like)를 조작 하 고 하나의 단위로 그릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="830f7-103">A path is a sequence of graphics primitives (lines, rectangles, curves, text, and the like) that can be manipulated and drawn as a single unit.</span></span> <span data-ttu-id="830f7-104">경로 나눌 수 있으며 *수치* 열려 있거나 닫힌 합니다.</span><span class="sxs-lookup"><span data-stu-id="830f7-104">A path can be divided into *figures* that are either open or closed.</span></span> <span data-ttu-id="830f7-105">도형 여러 기본 요소를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="830f7-105">A figure can contain several primitives.</span></span>  
  
 <span data-ttu-id="830f7-106">호출 하 여 패스를 그릴 수는 <xref:System.Drawing.Graphics.DrawPath%2A> 의 메서드는 <xref:System.Drawing.Graphics> 클래스를 호출 하 여 경로 채울 수는 <xref:System.Drawing.Graphics.FillPath%2A> 의 메서드는 <xref:System.Drawing.Graphics> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="830f7-106">You can draw a path by calling the <xref:System.Drawing.Graphics.DrawPath%2A> method of the <xref:System.Drawing.Graphics> class, and you can fill a path by calling the <xref:System.Drawing.Graphics.FillPath%2A> method of the <xref:System.Drawing.Graphics> class.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="830f7-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="830f7-107">In This Section</span></span>  
 [<span data-ttu-id="830f7-108">방법: 선, 곡선 및 도형으로 그림 만들기</span><span class="sxs-lookup"><span data-stu-id="830f7-108">How to: Create Figures from Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-figures-from-lines-curves-and-shapes.md)  
 <span data-ttu-id="830f7-109">사용 하는 방법을 보여 줍니다.는 <xref:System.Drawing.Drawing2D.GraphicsPath> 에 그림을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="830f7-109">Shows how to use a <xref:System.Drawing.Drawing2D.GraphicsPath> to create figures.</span></span>  
  
 [<span data-ttu-id="830f7-110">방법: 열린 그림 채우기</span><span class="sxs-lookup"><span data-stu-id="830f7-110">How to: Fill Open Figures</span></span>](../../../../docs/framework/winforms/advanced/how-to-fill-open-figures.md)  
 <span data-ttu-id="830f7-111">작성 하는 방법에 설명 된 <xref:System.Drawing.Drawing2D.GraphicsPath>합니다.</span><span class="sxs-lookup"><span data-stu-id="830f7-111">Explains how to fill a <xref:System.Drawing.Drawing2D.GraphicsPath>.</span></span>  
  
 [<span data-ttu-id="830f7-112">방법: 구부러진 경로를 선으로 펴기</span><span class="sxs-lookup"><span data-stu-id="830f7-112">How to: Flatten a Curved Path into a Line</span></span>](../../../../docs/framework/winforms/advanced/how-to-flatten-a-curved-path-into-a-line.md)  
 <span data-ttu-id="830f7-113">평면화 하는 방법을 보여 줍니다는 <xref:System.Drawing.Drawing2D.GraphicsPath>합니다.</span><span class="sxs-lookup"><span data-stu-id="830f7-113">Shows how to flatten a <xref:System.Drawing.Drawing2D.GraphicsPath>.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="830f7-114">참조</span><span class="sxs-lookup"><span data-stu-id="830f7-114">Reference</span></span>  
 <xref:System.Drawing.Drawing2D.GraphicsPath>  
 <span data-ttu-id="830f7-115">이 클래스를 설명 하 고 모든 해당 멤버의 링크를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="830f7-115">Describes this class and contains links to all of its members.</span></span>
