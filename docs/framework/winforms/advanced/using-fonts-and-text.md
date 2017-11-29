---
title: "글꼴 및 텍스트 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- GDI [Windows Forms], drawing text [Windows Forms]
- text [Windows Forms], drawing in Windows Forms
- examples [Windows Forms], fonts and text
- fonts [Windows Forms], using in Windows Forms
- strings [Windows Forms], drawing in Windows Forms
ms.assetid: d43640f3-da94-4df2-a29d-a9d021a1c069
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c18dde7265a07eb45e0211a882b19acc6342e924
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="using-fonts-and-text"></a><span data-ttu-id="c6346-102">글꼴 및 텍스트 사용</span><span class="sxs-lookup"><span data-stu-id="c6346-102">Using Fonts and Text</span></span>
<span data-ttu-id="c6346-103">제공 하는 몇 가지 클래스는 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 및 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] Windows Forms의 텍스트를 그리기 위한 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6346-103">There are several classes offered by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] for drawing text on Windows Forms.</span></span> <span data-ttu-id="c6346-104">[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics> 클래스에 여러 개의 <xref:System.Drawing.Graphics.DrawString%2A> 텍스트, 위치, 사각형, 글꼴 및 서식을 경계 등의 다양 한 기능을 지정할 수 있도록 하는 메서드.</span><span class="sxs-lookup"><span data-stu-id="c6346-104">The [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics> class has several <xref:System.Drawing.Graphics.DrawString%2A> methods that allow you to specify various features of text, such as location, bounding rectangle, font, and format.</span></span> <span data-ttu-id="c6346-105">그릴 텍스트를 측정 하는 또한 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 정적을 사용 하 여 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 및 <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> 방법에서 제공 되는 `TextRenderer` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="c6346-105">In addition, you can draw and measure text with [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] using the static <xref:System.Windows.Forms.TextRenderer.DrawText%2A> and <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> methods offered by the `TextRenderer` class.</span></span> <span data-ttu-id="c6346-106">[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 메서드 통해서도 위치, 글꼴 및 서식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6346-106">The [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] methods also allow you to specify location, font, and format.</span></span> <span data-ttu-id="c6346-107">그러나 하나를 선택할 수 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 또는 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 텍스트 렌더링에 대 한 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 제안을 향상 된 성능과 더 정확한 텍스트 측정 일반적으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6346-107">You can choose either [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] or [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] for text rendering; however, [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] generally offers better performance and more accurate text measuring.</span></span> <span data-ttu-id="c6346-108">텍스트 렌더링에 영향을 주는 다른 클래스에는 `FontFamily`, `Font`, <xref:System.Drawing.StringFormat>, 및 `TextFormatFlags`합니다.</span><span class="sxs-lookup"><span data-stu-id="c6346-108">Other classes that contribute to text rendering include `FontFamily`, `Font`, <xref:System.Drawing.StringFormat>, and `TextFormatFlags`.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c6346-109">단원 내용</span><span class="sxs-lookup"><span data-stu-id="c6346-109">In This Section</span></span>  
 [<span data-ttu-id="c6346-110">방법: 글꼴 패밀리 및 글꼴 만들기</span><span class="sxs-lookup"><span data-stu-id="c6346-110">How to: Construct Font Families and Fonts</span></span>](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)  
 <span data-ttu-id="c6346-111">만드는 방법을 보여 줍니다 `Font` 및 `FontFamily` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c6346-111">Shows how to create `Font` and `FontFamily` objects.</span></span>  
  
 [<span data-ttu-id="c6346-112">방법: 지정된 위치에 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="c6346-112">How to: Draw Text at a Specified Location</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-at-a-specified-location.md)  
 <span data-ttu-id="c6346-113">에 특정 위치를 사용 하 여 텍스트를 그리는 방법을 설명 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 및 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="c6346-113">Describes how to draw text in a certain location using [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span></span>  
  
 [<span data-ttu-id="c6346-114">방법: 사각형 안에 줄 바꿈된 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="c6346-114">How to: Draw Wrapped Text in a Rectangle</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-wrapped-text-in-a-rectangle.md)  
 <span data-ttu-id="c6346-115">사용 하 여 사각형의 텍스트를 그리는 방법을 설명 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 및 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="c6346-115">Explains how to draw text in a rectangle using [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span></span>  
  
 [<span data-ttu-id="c6346-116">방법: GDI를 사용하여 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="c6346-116">How to: Draw Text with GDI</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 <span data-ttu-id="c6346-117">사용 하는 방법을 보여 줍니다. [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 텍스트를 그리기 위한 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6346-117">Demonstrates how to use [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] for drawing text.</span></span>  
  
 [<span data-ttu-id="c6346-118">방법: 그린 텍스트 맞추기</span><span class="sxs-lookup"><span data-stu-id="c6346-118">How to: Align Drawn Text</span></span>](../../../../docs/framework/winforms/advanced/how-to-align-drawn-text.md)  
 <span data-ttu-id="c6346-119">서식을 지정 하는 방법을 보여 줍니다. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 및 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="c6346-119">Shows how to format [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] text.</span></span>  
  
 [<span data-ttu-id="c6346-120">방법: 세로 텍스트 만들기</span><span class="sxs-lookup"><span data-stu-id="c6346-120">How to: Create Vertical Text</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-vertical-text.md)  
 <span data-ttu-id="c6346-121">세로로 정렬 된 텍스트를 그릴 하는 방법을 설명 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="c6346-121">Describes how to draw vertically aligned text with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span>  
  
 [<span data-ttu-id="c6346-122">방법: 그린 텍스트에 탭 정지 설정</span><span class="sxs-lookup"><span data-stu-id="c6346-122">How to: Set Tab Stops in Drawn Text</span></span>](../../../../docs/framework/winforms/advanced/how-to-set-tab-stops-in-drawn-text.md)  
 <span data-ttu-id="c6346-123">텍스트와 탭 정지를 그리는 방법을 보여 줍니다 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="c6346-123">Shows how draw text with tab stops with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span>  
  
 [<span data-ttu-id="c6346-124">방법: 설치된 글꼴 열거</span><span class="sxs-lookup"><span data-stu-id="c6346-124">How to: Enumerate Installed Fonts</span></span>](../../../../docs/framework/winforms/advanced/how-to-enumerate-installed-fonts.md)  
 <span data-ttu-id="c6346-125">설치 된 글꼴의 이름을 나열 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6346-125">Explains how to list the names of installed fonts.</span></span>  
  
 [<span data-ttu-id="c6346-126">방법: 개인 글꼴 컬렉션 만들기</span><span class="sxs-lookup"><span data-stu-id="c6346-126">How to: Create a Private Font Collection</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-private-font-collection.md)  
 <span data-ttu-id="c6346-127">만드는 방법에 설명 된 <xref:System.Drawing.Text.PrivateFontCollection> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c6346-127">Describes how to create a <xref:System.Drawing.Text.PrivateFontCollection> object.</span></span>  
  
 [<span data-ttu-id="c6346-128">방법: 글꼴 메트릭 얻기</span><span class="sxs-lookup"><span data-stu-id="c6346-128">How to: Obtain Font Metrics</span></span>](../../../../docs/framework/winforms/advanced/how-to-obtain-font-metrics.md)  
 <span data-ttu-id="c6346-129">셀 상승 하강 등 글꼴 메트릭 얻기 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c6346-129">Shows how to obtain font metrics such as cell ascent and descent.</span></span>  
  
 [<span data-ttu-id="c6346-130">방법: 텍스트에 앤티 앨리어싱 사용</span><span class="sxs-lookup"><span data-stu-id="c6346-130">How to: Use Antialiasing with Text</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-antialiasing-with-text.md)  
 <span data-ttu-id="c6346-131">텍스트를 그릴 때 앤티 앨리어싱 사용 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6346-131">Explains how to use antialiasing when drawing text.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c6346-132">참조</span><span class="sxs-lookup"><span data-stu-id="c6346-132">Reference</span></span>  
 <xref:System.Drawing.Font>  
 <span data-ttu-id="c6346-133">이 클래스를 설명 하 고 모든 해당 멤버의 링크를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6346-133">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Drawing.FontFamily>  
 <span data-ttu-id="c6346-134">이 클래스를 설명 하 고 모든 해당 멤버의 링크를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6346-134">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Drawing.Text.PrivateFontCollection>  
 <span data-ttu-id="c6346-135">이 클래스를 설명 하 고 모든 해당 멤버의 링크를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6346-135">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.TextRenderer>  
 <span data-ttu-id="c6346-136">이 클래스를 설명 하 고 모든 해당 멤버의 링크를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6346-136">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.TextFormatFlags>  
 <span data-ttu-id="c6346-137">이 클래스를 설명 하 고 모든 해당 멤버의 링크를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6346-137">Describes this class and contains links to all of its members.</span></span>
