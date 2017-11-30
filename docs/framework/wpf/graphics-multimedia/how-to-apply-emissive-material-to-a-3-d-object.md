---
title: "방법: 3차원 개체에 EmissiveMaterial 적용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- EmissiveMaterial [WPF], applying to 3-D objects
- 3-D objects [WPF], applying EmissiveMaterial
ms.assetid: fd442cc2-5adc-487a-ba70-e45ed54bb3b4
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 069ab4e417d639a36a9168fa950f4b4f6df4c2c2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-apply-emissive-material-to-a-3-d-object"></a><span data-ttu-id="ae092-102">방법: 3차원 개체에 EmissiveMaterial 적용</span><span class="sxs-lookup"><span data-stu-id="ae092-102">How to: Apply Emissive Material to a 3-D Object</span></span>
<span data-ttu-id="ae092-103">다음 예제에서는 사용 하는 방법을 보여 줍니다. <xref:System.Windows.Media.Media3D.EmissiveMaterial> 색은 기존 자료 같은 EmissiveMaterial의 브러시의 색을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae092-103">The following example shows how to use <xref:System.Windows.Media.Media3D.EmissiveMaterial> to add color to an existing Material equal to the color of the EmissiveMaterial's brush.</span></span> <span data-ttu-id="ae092-104">다음 코드 <xref:System.Windows.Media.Media3D.DiffuseMaterial> 및 <xref:System.Windows.Media.Media3D.EmissiveMaterial> 파란색 DiffuseMaterial의 모양에 추가할 조합 하 여 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae092-104">The code below shows <xref:System.Windows.Media.Media3D.DiffuseMaterial> and <xref:System.Windows.Media.Media3D.EmissiveMaterial> applied in combination to add blue to the DiffuseMaterial's appearance.</span></span>  
  
 [!code-xaml[3DGallery_snip#EmmisiveMaterialAnimationExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emmisivematerialanimationexampleinline1)]  
  
 <span data-ttu-id="ae092-105">프로시저 코드</span><span class="sxs-lookup"><span data-stu-id="ae092-105">In procedural code:</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexampleinline1)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="ae092-106">예제</span><span class="sxs-lookup"><span data-stu-id="ae092-106">Example</span></span>  
 <span data-ttu-id="ae092-107">다음 코드에서는 XAML 전체 샘플을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ae092-107">The following code shows the entire sample in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#EmissiveMaterialExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emissivematerialexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="ae092-108">예제</span><span class="sxs-lookup"><span data-stu-id="ae092-108">Example</span></span>  
 <span data-ttu-id="ae092-109">다음은 프로시저 코드의 전체 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="ae092-109">Below is the entire sample in procedural code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="ae092-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ae092-110">See Also</span></span>  
 [<span data-ttu-id="ae092-111">3차원 장면 만들기</span><span class="sxs-lookup"><span data-stu-id="ae092-111">Create a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)  
 [<span data-ttu-id="ae092-112">3차원 그래픽 개요</span><span class="sxs-lookup"><span data-stu-id="ae092-112">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [<span data-ttu-id="ae092-113">3차원 장면의 Material 속성에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="ae092-113">Animate Material Properties in a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-material-properties-in-a-3-d-scene.md)  
 [<span data-ttu-id="ae092-114">3차원 개체의 앞과 뒤에 Material 적용</span><span class="sxs-lookup"><span data-stu-id="ae092-114">Apply Material to the Front and Back of a 3-D Object</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-material-to-the-front-and-back-of-a-3-d-object.md)
