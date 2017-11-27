---
title: "방법: 시스템 브러시로 영역 그리기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- system brushes [WPF], painting with
- painting [WPF], with system brushes
- brushes [WPF], painting with system brushes [WPF]
ms.assetid: 5141a763-9235-42cb-a6bb-afc75513eac7
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 355df3718d90768cdfa8bc9780c44c19eb4bf9bf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-paint-an-area-with-a-system-brush"></a><span data-ttu-id="a8fc9-102">방법: 시스템 브러시로 영역 그리기</span><span class="sxs-lookup"><span data-stu-id="a8fc9-102">How to: Paint an Area with a System Brush</span></span>
<span data-ttu-id="a8fc9-103"><xref:System.Windows.SystemColors> 클래스와 같은 시스템 브러시, 색에 대 한 액세스를 제공 <xref:System.Windows.SystemColors.ControlBrush%2A>, <xref:System.Windows.SystemColors.ControlBrushKey%2A>, 및 <xref:System.Windows.SystemColors.DesktopBrush%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="a8fc9-103">The <xref:System.Windows.SystemColors> class provides access to system brushes and colors, such as <xref:System.Windows.SystemColors.ControlBrush%2A>, <xref:System.Windows.SystemColors.ControlBrushKey%2A>, and <xref:System.Windows.SystemColors.DesktopBrush%2A>.</span></span> <span data-ttu-id="a8fc9-104">시스템 브러시는는 <xref:System.Windows.Media.SolidColorBrush> 개체를 지정된 된 시스템 색으로 영역을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="a8fc9-104">A system brush is a <xref:System.Windows.Media.SolidColorBrush> object that paints an area with the specified system color.</span></span> <span data-ttu-id="a8fc9-105">시스템 브러시는 항상 단색을 생성하므로 그라데이션을 만드는 데는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a8fc9-105">A system brush always produces a solid fill; it can't be used to create a gradient.</span></span>  
  
 <span data-ttu-id="a8fc9-106">시스템 브러시는 정적 또는 동적 리소스로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8fc9-106">You can use system brushes as either a static or a dynamic resource.</span></span> <span data-ttu-id="a8fc9-107">사용자 응용 프로그램이 실행될 때 사용자가 시스템 브러시를 변경하는 경우 브러시가 자동으로 업데이트되게 하려면 동적 리소스를 사용하고, 그렇지 않으면 정적 리소스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a8fc9-107">Use a dynamic resource if you want the brush to update automatically if the user changes the system brush as the application is running; otherwise, use a static resource.</span></span> <span data-ttu-id="a8fc9-108">SystemColors 클래스는 엄격한 명명 규칙을 따르는 다양한 정적 속성을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a8fc9-108">The SystemColors class contains a variety of static properties that follow a strict naming convention:</span></span>  
  
-   <span data-ttu-id="a8fc9-109">*\<SystemColor>*Brush</span><span class="sxs-lookup"><span data-stu-id="a8fc9-109">*\<SystemColor>*Brush</span></span>  
  
     <span data-ttu-id="a8fc9-110">에 대 한 정적 참조는 <xref:System.Windows.Media.SolidColorBrush> 지정된 된 시스템 색의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8fc9-110">Gets a static reference to a <xref:System.Windows.Media.SolidColorBrush> of the specified system color.</span></span>  
  
-   <span data-ttu-id="a8fc9-111">*\<SystemColor>*BrushKey</span><span class="sxs-lookup"><span data-stu-id="a8fc9-111">*\<SystemColor>*BrushKey</span></span>  
  
     <span data-ttu-id="a8fc9-112">에 대 한 동적 참조는 <xref:System.Windows.Media.SolidColorBrush> 지정된 된 시스템 색의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8fc9-112">Gets a dynamic reference to a <xref:System.Windows.Media.SolidColorBrush> of the specified system color.</span></span>  
  
-   <span data-ttu-id="a8fc9-113">*\<SystemColor>*Color</span><span class="sxs-lookup"><span data-stu-id="a8fc9-113">*\<SystemColor>*Color</span></span>  
  
     <span data-ttu-id="a8fc9-114">에 대 한 정적 참조는 <xref:System.Windows.Media.Color> 지정된 된 시스템 색의 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="a8fc9-114">Gets a static reference to a <xref:System.Windows.Media.Color> structure of the specified system color.</span></span>  
  
-   <span data-ttu-id="a8fc9-115">*\<SystemColor>*ColorKey</span><span class="sxs-lookup"><span data-stu-id="a8fc9-115">*\<SystemColor>*ColorKey</span></span>  
  
     <span data-ttu-id="a8fc9-116">에 대 한 동적 참조는 <xref:System.Windows.Media.Color> 지정된 된 시스템 색의 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="a8fc9-116">Gets a dynamic reference to the <xref:System.Windows.Media.Color> structure of the specified system color.</span></span>  
  
 <span data-ttu-id="a8fc9-117">시스템 색은는 <xref:System.Windows.Media.Color> 브러시를 구성 하는 데 사용할 수 있는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="a8fc9-117">A system color is a <xref:System.Windows.Media.Color> structure that can be used to configure a brush.</span></span> <span data-ttu-id="a8fc9-118">예를 들어 그라데이션을 설정 하 여 시스템 색을 사용 하 여 만들 수 있습니다는 <xref:System.Windows.Media.GradientStop.Color%2A> 의 속성을 <xref:System.Windows.Media.LinearGradientBrush> 개체의 그라데이션 중지점 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8fc9-118">For example, you can create a gradient using system colors by setting the <xref:System.Windows.Media.GradientStop.Color%2A> properties of a <xref:System.Windows.Media.LinearGradientBrush> object's gradient stops with system colors.</span></span> <span data-ttu-id="a8fc9-119">예를 들어 참조 [그라데이션에서 시스템 색을 사용 하 여](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a8fc9-119">For an example, see [Use System Colors in a Gradient](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8fc9-120">예제</span><span class="sxs-lookup"><span data-stu-id="a8fc9-120">Example</span></span>  
 <span data-ttu-id="a8fc9-121">다음 예제에서는 동적 시스템 브러시 참조를 사용하여 단추의 배경색을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a8fc9-121">The following example uses a dynamic system brush reference to set the Background of a button.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorDesktopBrushKeyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemBrushExample.xaml#graphicsmmdynamicsystemcolordesktopbrushkeyexamplewholepage)]  
  
 <span data-ttu-id="a8fc9-122">다음 예제에서는 정적 시스템 브러시 참조를 사용하여 단추의 배경색을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a8fc9-122">The next example uses a static system brush reference to set the Background of a button.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorDesktopBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemBrushExample.xaml#graphicsmmstaticsystemcolordesktopbrushexamplewholepage)]  
  
 <span data-ttu-id="a8fc9-123">그라데이션에서 시스템 색을 사용 하는 방법을 보여 주는 예제를 참조 하십시오. [그라데이션에서 사용 하 여 시스템 색상](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a8fc9-123">For an example showing how to use a system color in a gradient, see [Use System Colors in a Gradient](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8fc9-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a8fc9-124">See Also</span></span>  
 [<span data-ttu-id="a8fc9-125">그라데이션에 시스템 색 사용</span><span class="sxs-lookup"><span data-stu-id="a8fc9-125">Use System Colors in a Gradient</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md)  
 [<span data-ttu-id="a8fc9-126">단색 및 그라데이션을 사용한 그리기 개요</span><span class="sxs-lookup"><span data-stu-id="a8fc9-126">Painting with Solid Colors and Gradients Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
