---
title: "방법: 3차원 개체의 앞과 뒤에 Material 적용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 3-D objects [WPF], applying Material class
- Material class [WPF], applying to both sides of 3-D object
- classes [WPF], Material
ms.assetid: d93c8ad6-4939-4d29-9544-4d16d98093c1
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c5ead8805c3d16bc16e259bdf90a19f05500563c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-apply-material-to-the-front-and-back-of-a-3-d-object"></a><span data-ttu-id="58cf9-102">방법: 3차원 개체의 앞과 뒤에 Material 적용</span><span class="sxs-lookup"><span data-stu-id="58cf9-102">How to: Apply Material to the Front and Back of a 3-D Object</span></span>
<span data-ttu-id="58cf9-103">적용 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Media.Media3D.Material> 를 맨 앞과 뒤 3 차원 개체를 개체의 양쪽 모두 표시 하도록 개체에 애니메이션을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="58cf9-103">The following example shows how to apply a <xref:System.Windows.Media.Media3D.Material> to the front and back of a 3-D object and animate the object to show both sides of the object.</span></span> <span data-ttu-id="58cf9-104"><xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> 속성의는 <xref:System.Windows.Media.Media3D.GeometryModel3D> 빨간색을 적용 하는 데 사용 되 <xref:System.Windows.Media.Brush> 개체의 전면에 및 <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> 속성의는 <xref:System.Windows.Media.Media3D.GeometryModel3D> 옆에 파란색을 적용 하는 데 사용 되 <xref:System.Windows.Media.Brush> 개체의 뒷면에 합니다.</span><span class="sxs-lookup"><span data-stu-id="58cf9-104">The <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D> is used to apply a red <xref:System.Windows.Media.Brush> to the front side of the object and the <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> property of the <xref:System.Windows.Media.Media3D.GeometryModel3D> is used to apply a blue <xref:System.Windows.Media.Brush> to the back side of the object.</span></span> <span data-ttu-id="58cf9-105">아래 코드 개체에 대 한 자료의 응용 프로그램을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58cf9-105">The code below shows the application of the materials to the object:</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="58cf9-106">예</span><span class="sxs-lookup"><span data-stu-id="58cf9-106">Example</span></span>  
 <span data-ttu-id="58cf9-107">다음 코드에서는 전체 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58cf9-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="58cf9-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="58cf9-108">See Also</span></span>  
 [<span data-ttu-id="58cf9-109">3차원 장면 만들기</span><span class="sxs-lookup"><span data-stu-id="58cf9-109">Create a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)  
 [<span data-ttu-id="58cf9-110">3차원 그래픽 개요</span><span class="sxs-lookup"><span data-stu-id="58cf9-110">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [<span data-ttu-id="58cf9-111">3차원 장면의 Material 속성에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="58cf9-111">Animate Material Properties in a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-material-properties-in-a-3-d-scene.md)  
 [<span data-ttu-id="58cf9-112">3차원 개체에 EmissiveMaterial 적용</span><span class="sxs-lookup"><span data-stu-id="58cf9-112">Apply Emissive Material to a 3-D Object</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-emissive-material-to-a-3-d-object.md)
