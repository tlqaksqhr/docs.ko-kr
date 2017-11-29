---
title: "방법: 3차원 변환에 애니메이션 효과 주기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], 3-D translations
- 3-D translations [WPF], animating
ms.assetid: d4eece1f-0cd2-4a2c-8370-293354c380e4
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a0477943b715a23a1d6992f7e9da885ffa01061c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-3-d-translations"></a><span data-ttu-id="b73ac-102">방법: 3차원 변환에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="b73ac-102">How to: Animate 3-D Translations</span></span>
<span data-ttu-id="b73ac-103">이 항목에 설정 된 번역 변형에 애니메이션을 적용 하는 방법을 보여 줍니다는 [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="b73ac-103">This topic demonstrates how to animate a translation transformation set on a [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] model.</span></span>  
  
 <span data-ttu-id="b73ac-104">아래 코드의 응용을 보여 줍니다.는 <xref:System.Windows.Media.Media3D.TranslateTransform3D> 개체는 <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> 속성은 <xref:System.Windows.Media.Media3D.GeometryModel3D>합니다.</span><span class="sxs-lookup"><span data-stu-id="b73ac-104">The code below shows the application of a <xref:System.Windows.Media.Media3D.TranslateTransform3D> object to the <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline1)]  
  
 <span data-ttu-id="b73ac-105"><xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> 속성 <xref:System.Windows.Media.Media3D.TranslateTransform3D> 개체 아래에 있는 코드를 사용 하 여 애니메이션 효과가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b73ac-105">The <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> property of this <xref:System.Windows.Media.Media3D.TranslateTransform3D> object is animated using the code below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline2)]  
  
## <a name="example"></a><span data-ttu-id="b73ac-106">예제</span><span class="sxs-lookup"><span data-stu-id="b73ac-106">Example</span></span>  
 <span data-ttu-id="b73ac-107">다음 코드에서는 전체 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b73ac-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="b73ac-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b73ac-108">See Also</span></span>  
 [<span data-ttu-id="b73ac-109">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="b73ac-109">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="b73ac-110">3차원 장면 만들기</span><span class="sxs-lookup"><span data-stu-id="b73ac-110">Create a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)  
 [<span data-ttu-id="b73ac-111">3차원 그래픽 개요</span><span class="sxs-lookup"><span data-stu-id="b73ac-111">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [<span data-ttu-id="b73ac-112">Transform 개요</span><span class="sxs-lookup"><span data-stu-id="b73ac-112">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
