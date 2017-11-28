---
title: "그래픽 인터페이스의 구조"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- GDI+, using managed interface
- graphics [Windows Forms], class structure
ms.assetid: 010a1e46-656b-40a1-8d5d-87aa05ee1243
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cd1da930df151869ea3e891da7057f44ed0a4603
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="structure-of-the-graphics-interface"></a><span data-ttu-id="4afe9-102">그래픽 인터페이스의 구조</span><span class="sxs-lookup"><span data-stu-id="4afe9-102">Structure of the Graphics Interface</span></span>
<span data-ttu-id="4afe9-103">관리 되는 클래스 인터페이스를 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 약 60 개의 클래스, 50 개의 열거형 및 8 구조를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="4afe9-103">The managed class interface to [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] contains about 60 classes, 50 enumerations, and 8 structures.</span></span> <span data-ttu-id="4afe9-104"><xref:System.Drawing.Graphics> 의 핵심 클래스는 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 기능; 실제로 선, 곡선, 도형, 이미지 및 텍스트를 그릴 수 있는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4afe9-104">The <xref:System.Drawing.Graphics> class is at the core of [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] functionality; it is the class that actually draws lines, curves, figures, images, and text.</span></span>  
  
## <a name="important-classes"></a><span data-ttu-id="4afe9-105">중요 한 클래스</span><span class="sxs-lookup"><span data-stu-id="4afe9-105">Important Classes</span></span>  
 <span data-ttu-id="4afe9-106">대부분의 클래스와 함께 동작의 <xref:System.Drawing.Graphics> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4afe9-106">Many classes work together with the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="4afe9-107">예를 들어는 <xref:System.Drawing.Graphics.DrawLine%2A> 메서드 수신는 <xref:System.Drawing.Pen> 를 그릴 선의 특성 (예: 색, 너비, 대시 스타일 및 like)을 포함 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="4afe9-107">For example, the <xref:System.Drawing.Graphics.DrawLine%2A> method receives a <xref:System.Drawing.Pen> object, which holds attributes (color, width, dash style, and the like) of the line to be drawn.</span></span> <span data-ttu-id="4afe9-108"><xref:System.Drawing.Graphics.FillRectangle%2A> 방법에 대 한 포인터를 받을 수는 <xref:System.Drawing.Drawing2D.LinearGradientBrush> 개체와 함께 작동 하는 <xref:System.Drawing.Graphics> 효과 사각형 채울 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="4afe9-108">The <xref:System.Drawing.Graphics.FillRectangle%2A> method can receive a pointer to a <xref:System.Drawing.Drawing2D.LinearGradientBrush> object, which works with the <xref:System.Drawing.Graphics> object to fill a rectangle with a gradually changing color.</span></span> <span data-ttu-id="4afe9-109"><xref:System.Drawing.Font>및 <xref:System.Drawing.StringFormat> 개체 방법이 달라질는 <xref:System.Drawing.Graphics> 개체 텍스트를 그립니다.</span><span class="sxs-lookup"><span data-stu-id="4afe9-109"><xref:System.Drawing.Font> and <xref:System.Drawing.StringFormat> objects influence the way a <xref:System.Drawing.Graphics> object draws text.</span></span> <span data-ttu-id="4afe9-110">A <xref:System.Drawing.Drawing2D.Matrix> 개체를 저장 및 조작의 월드 변형과 <xref:System.Drawing.Graphics> 회전, 크기 조정, 및 이미지 대칭 이동 하는 데 사용 되는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="4afe9-110">A <xref:System.Drawing.Drawing2D.Matrix> object stores and manipulates the world transformation of a <xref:System.Drawing.Graphics> object, which is used to rotate, scale, and flip images.</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="4afe9-111">몇 가지 구조 제공 (예를 들어 <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Point>, 및 <xref:System.Drawing.Size>) 데이터를 그래픽 구성에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="4afe9-111"> provides several structures (for example, <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Point>, and <xref:System.Drawing.Size>) for organizing graphics data.</span></span> <span data-ttu-id="4afe9-112">또한 특정 클래스에는 주로 구조적된 데이터 형식으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4afe9-112">Also, certain classes serve primarily as structured data types.</span></span> <span data-ttu-id="4afe9-113">예를 들어는 <xref:System.Drawing.Imaging.BitmapData> 클래스에 대 한 도우미는는 <xref:System.Drawing.Bitmap> 클래스 및 <xref:System.Drawing.Drawing2D.PathData> 클래스에 대 한 도우미는는 <xref:System.Drawing.Drawing2D.GraphicsPath> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4afe9-113">For example, the <xref:System.Drawing.Imaging.BitmapData> class is a helper for the <xref:System.Drawing.Bitmap> class, and the <xref:System.Drawing.Drawing2D.PathData> class is a helper for the <xref:System.Drawing.Drawing2D.GraphicsPath> class.</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="4afe9-114">컬렉션 관련 상수 여러 열거형을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4afe9-114"> defines several enumerations, which are collections of related constants.</span></span> <span data-ttu-id="4afe9-115">예를 들어는 <xref:System.Drawing.Drawing2D.LineJoin> 열거형에는 요소가 <xref:System.Drawing.Drawing2D.LineJoin.Bevel>, <xref:System.Drawing.Drawing2D.LineJoin.Miter>, 및 <xref:System.Drawing.Drawing2D.LineJoin.Round>, 조인 두 선으로 사용할 수 있는 스타일을 지정 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="4afe9-115">For example, the <xref:System.Drawing.Drawing2D.LineJoin> enumeration contains the elements <xref:System.Drawing.Drawing2D.LineJoin.Bevel>, <xref:System.Drawing.Drawing2D.LineJoin.Miter>, and <xref:System.Drawing.Drawing2D.LineJoin.Round>, which specify styles that can be used to join two lines.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4afe9-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4afe9-116">See Also</span></span>  
 [<span data-ttu-id="4afe9-117">그래픽 개요</span><span class="sxs-lookup"><span data-stu-id="4afe9-117">Graphics Overview</span></span>](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)  
 [<span data-ttu-id="4afe9-118">GDI + 관리 코드 정보</span><span class="sxs-lookup"><span data-stu-id="4afe9-118">About GDI+ Managed Code</span></span>](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)  
 [<span data-ttu-id="4afe9-119">관리되는 그래픽 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="4afe9-119">Using Managed Graphics Classes</span></span>](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)
