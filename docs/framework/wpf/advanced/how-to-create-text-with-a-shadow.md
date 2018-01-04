---
title: "방법: 그림자가 적용된 텍스트 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- typography [WPF], shadow effects
- shadow effects in text [WPF]
- text [WPF], shadowed
ms.assetid: 6ab9c754-6001-4708-b479-5367f2fd1a35
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b031b0dce8e1fd06399ded0b6d612a23323ae837
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-text-with-a-shadow"></a><span data-ttu-id="cc1ea-102">방법: 그림자가 적용된 텍스트 만들기</span><span class="sxs-lookup"><span data-stu-id="cc1ea-102">How to: Create Text with a Shadow</span></span>
<span data-ttu-id="cc1ea-103">이 단원의 예제에서는 표시된 텍스트에 대해 그림자 효과를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cc1ea-103">The examples in this section show how to create a shadow effect for displayed text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc1ea-104">예</span><span class="sxs-lookup"><span data-stu-id="cc1ea-104">Example</span></span>  
 <span data-ttu-id="cc1ea-105"><xref:System.Windows.Media.Effects.DropShadowEffect> 개체 다양 한 놓기에 대 한 그림자 효과 만들 수 있습니다 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="cc1ea-105">The <xref:System.Windows.Media.Effects.DropShadowEffect> object allows you to create a variety of drop shadow effects for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] objects.</span></span> <span data-ttu-id="cc1ea-106">다음 예제에서는 그림자 효과가 적용된 텍스트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cc1ea-106">The following example shows a drop shadow effect applied to text.</span></span> <span data-ttu-id="cc1ea-107">이 경우 그림자는 그림자 색깔이 흐린, 부드러운 그림자입니다.</span><span class="sxs-lookup"><span data-stu-id="cc1ea-107">In this case, the shadow is a soft shadow, which means the shadow color blurs.</span></span>  
  
 <span data-ttu-id="cc1ea-108">![Softness &#61; 인 텍스트 그림자 0.25](../../../../docs/framework/wpf/advanced/media/shadowtext01.jpg "ShadowText01")</span><span class="sxs-lookup"><span data-stu-id="cc1ea-108">![Text shadow with Softness &#61; 0.25](../../../../docs/framework/wpf/advanced/media/shadowtext01.jpg "ShadowText01")</span></span>  
<span data-ttu-id="cc1ea-109">부드러운 그림자가 적용된 텍스트의 예</span><span class="sxs-lookup"><span data-stu-id="cc1ea-109">Example of text with a soft shadow</span></span>  
  
 <span data-ttu-id="cc1ea-110">그림자의 너비를 설정 하 여 제어할 수 있습니다는 <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="cc1ea-110">You can control the width of a shadow by setting the <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> property.</span></span> <span data-ttu-id="cc1ea-111">값이 `4.0` 그림자 높이 인 4 픽셀을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cc1ea-111">A value of `4.0` indicates a shadow width of 4 pixels.</span></span> <span data-ttu-id="cc1ea-112">부드러운 정도 제어할 수 있습니다 또는 수정 하 여 그림자 흐림 효과 <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="cc1ea-112">You can control the softness, or blur, of a shadow by modifying the <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> property.</span></span> <span data-ttu-id="cc1ea-113">값이 `0.0` 없는 흐림 효과 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cc1ea-113">A value of `0.0` indicates no blurring.</span></span> <span data-ttu-id="cc1ea-114">다음 코드 예제에서는 부드러운 그림자를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cc1ea-114">The following code example shows how to create a soft shadow.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet1)]  
  
> [!NOTE]
>  <span data-ttu-id="cc1ea-115">이러한 그림자 효과 통과 하지 않는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 텍스트 렌더링 파이프라인.</span><span class="sxs-lookup"><span data-stu-id="cc1ea-115">These shadow effects do not go through the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] text rendering pipeline.</span></span> <span data-ttu-id="cc1ea-116">따라서 이러한 효과를 사용할 때 ClearType이 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc1ea-116">As a result, ClearType is disabled when using these effects.</span></span>  
  
 <span data-ttu-id="cc1ea-117">다음 예제에서는 진한 그림자 효과가 적용된 텍스트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cc1ea-117">The following example shows a hard drop shadow effect applied to text.</span></span> <span data-ttu-id="cc1ea-118">이 경우 그림자가 흐려지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cc1ea-118">In this case, the shadow is not blurred.</span></span>  
  
 <span data-ttu-id="cc1ea-119">![Softness &#61; 인 텍스트 그림자 0](../../../../docs/framework/wpf/advanced/media/shadowtext02.jpg "ShadowText02")</span><span class="sxs-lookup"><span data-stu-id="cc1ea-119">![Text shadow with Softness &#61; 0](../../../../docs/framework/wpf/advanced/media/shadowtext02.jpg "ShadowText02")</span></span>  
<span data-ttu-id="cc1ea-120">진한 그림자가 적용된 텍스트의 예</span><span class="sxs-lookup"><span data-stu-id="cc1ea-120">Example of text with a hard shadow</span></span>  
  
 <span data-ttu-id="cc1ea-121">설정 하 여 하드 그림자를 만들 수는 <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> 속성을 `0.0`는 없는 뜨 리고 사용 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cc1ea-121">You can create a hard shadow by setting the <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> property to `0.0`, which indicates that no blurring is used.</span></span> <span data-ttu-id="cc1ea-122">그림자의 방향을 수정 하 여 제어할 수 있습니다는 <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="cc1ea-122">You can control the direction of the shadow by modifying the <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> property.</span></span> <span data-ttu-id="cc1ea-123">이 속성의 방향 값도 값으로 설정 간의 `0` 및 `360`합니다.</span><span class="sxs-lookup"><span data-stu-id="cc1ea-123">Set the directional value of this property to a degree between `0` and `360`.</span></span> <span data-ttu-id="cc1ea-124">다음 그림의 방향 값을 보여 줍니다.는 <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc1ea-124">The following illustration shows the directional values of the <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> property setting.</span></span>  
  
 <span data-ttu-id="cc1ea-125">![그림자의 DropShadow 정도 설정](../../../../docs/framework/wpf/advanced/media/shadowtext08.png "ShadowText08")</span><span class="sxs-lookup"><span data-stu-id="cc1ea-125">![DropShadow degree setting of shadow](../../../../docs/framework/wpf/advanced/media/shadowtext08.png "ShadowText08")</span></span>  
<span data-ttu-id="cc1ea-126">DropShadow 방향 다이어그램</span><span class="sxs-lookup"><span data-stu-id="cc1ea-126">DropShadow Direction diagram</span></span>  
  
 <span data-ttu-id="cc1ea-127">다음 코드 예제에서는 진한 그림자를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cc1ea-127">The following code example shows how to create a hard shadow.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet2)]  
  
## <a name="using-a-blur-effect"></a><span data-ttu-id="cc1ea-128">흐림 효과 사용</span><span class="sxs-lookup"><span data-stu-id="cc1ea-128">Using a Blur Effect</span></span>  
 <span data-ttu-id="cc1ea-129">A <xref:System.Windows.Media.Effects.BlurBitmapEffect> 텍스트 개체 뒤에 배치할 수 있는 그림자 같은 효과 만드는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc1ea-129">A <xref:System.Windows.Media.Effects.BlurBitmapEffect> can be used to create a shadow-like effect that can be placed behind a text object.</span></span> <span data-ttu-id="cc1ea-130">텍스트에 적용된 흐림 비트맵 효과는 모든 방향에서 균등하게 텍스트를 흐리게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cc1ea-130">A blur bitmap effect applied to text blurs the text evenly in all directions.</span></span>  
  
 <span data-ttu-id="cc1ea-131">다음 예제에서는 흐림 효과가 적용된 텍스트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cc1ea-131">The following example shows a blur effect applied to text.</span></span>  
  
 <span data-ttu-id="cc1ea-132">![BlurBitmapEffect를 사용한 텍스트 그림자](../../../../docs/framework/wpf/advanced/media/shadowtext06.jpg "ShadowText06")</span><span class="sxs-lookup"><span data-stu-id="cc1ea-132">![Text shadow using a BlurBitmapEffect](../../../../docs/framework/wpf/advanced/media/shadowtext06.jpg "ShadowText06")</span></span>  
<span data-ttu-id="cc1ea-133">흐림 효과가 적용된 텍스트의 예</span><span class="sxs-lookup"><span data-stu-id="cc1ea-133">Example of text with a blur effect</span></span>  
  
 <span data-ttu-id="cc1ea-134">다음 코드 예제에는 흐린 효과를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cc1ea-134">The following code example shows how to create a blur effect.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/BlurShadows.xaml#textshadowsnippet6)]  
  
## <a name="using-a-translate-transform"></a><span data-ttu-id="cc1ea-135">좌표 이동 변환 사용</span><span class="sxs-lookup"><span data-stu-id="cc1ea-135">Using a Translate Transform</span></span>  
 <span data-ttu-id="cc1ea-136">A <xref:System.Windows.Media.TranslateTransform> 텍스트 개체 뒤에 배치할 수 있는 그림자 같은 효과 만드는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc1ea-136">A <xref:System.Windows.Media.TranslateTransform> can be used to create a shadow-like effect that can be placed behind a text object.</span></span>  
  
 <span data-ttu-id="cc1ea-137">다음 코드 예제에서는 한 <xref:System.Windows.Media.TranslateTransform> 텍스트 오프셋 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc1ea-137">The following code example uses a <xref:System.Windows.Media.TranslateTransform> to offset text.</span></span> <span data-ttu-id="cc1ea-138">이 예제에서 기본 텍스트 아래에 있는 약간 오프셋된 텍스트 복사본이 그림자 효과를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cc1ea-138">In this example, a slightly offset copy of text below the primary text creates a shadow effect.</span></span>  
  
 <span data-ttu-id="cc1ea-139">![Translatetransform을 사용한 텍스트 그림자](../../../../docs/framework/wpf/advanced/media/shadowtext07.jpg "ShadowText07")</span><span class="sxs-lookup"><span data-stu-id="cc1ea-139">![Text shadow using a TranslateTransform](../../../../docs/framework/wpf/advanced/media/shadowtext07.jpg "ShadowText07")</span></span>  
<span data-ttu-id="cc1ea-140">그림자 효과에 변환을 적용한 텍스트의 예</span><span class="sxs-lookup"><span data-stu-id="cc1ea-140">Example of text using a transform for a shadow effect</span></span>  
  
 <span data-ttu-id="cc1ea-141">다음 코드 예제에서는 그림자 효과에 변환을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cc1ea-141">The following code example shows how to create a transform for a shadow effect.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/TransformShadows.xaml#textshadowsnippet7)]
