---
title: '방법: 3차원 모델에 다중 변환 적용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3-D models [WPF], applying multiple transformations to
ms.assetid: cb72245a-5560-4c96-9f58-593c66296992
ms.openlocfilehash: 591f12d2e4d51df0d8474f894946b24910f8df86
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558693"
---
# <a name="how-to-apply-multiple-transformations-to-a-3-d-model"></a><span data-ttu-id="e1519-102">방법: 3차원 모델에 다중 변환 적용</span><span class="sxs-lookup"><span data-stu-id="e1519-102">How to: Apply Multiple Transformations to a 3-D Model</span></span>
<span data-ttu-id="e1519-103">이 예제에서는 사용 하는 방법을 보여 줍니다.는 <xref:System.Windows.Media.Media3D.RotateTransform3D> 및 <xref:System.Windows.Media.Media3D.ScaleTransform3D> 회전 하 고 3 차원 모델의 배율을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1519-103">This sample shows how to use a <xref:System.Windows.Media.Media3D.RotateTransform3D> and a <xref:System.Windows.Media.Media3D.ScaleTransform3D> to rotate and change the scale of a 3-D model.</span></span> <span data-ttu-id="e1519-104">아래 코드에 이러한 변환을 적용 하는 방법을 보여 줍니다는 <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> 의 속성을 <xref:System.Windows.Media.Media3D.GeometryModel3D> XAML에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1519-104">The code below shows how to apply these transforms to the <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D> in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Multiple3DTransformationsExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/MultipleTransformationsExample.xaml#multiple3dtransformationsexampleinline1)]  
  
 <span data-ttu-id="e1519-105">코드</span><span class="sxs-lookup"><span data-stu-id="e1519-105">In code:</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/MultipleTransformationsExample.cs#multiple3dtransformationscodeexampleinline1)]
 [!code-vb[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/multipletransformationsexample.vb#multiple3dtransformationscodeexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="e1519-106">예제</span><span class="sxs-lookup"><span data-stu-id="e1519-106">Example</span></span>  
 <span data-ttu-id="e1519-107">다음 코드에서는 XAML 전체 샘플을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e1519-107">The following code shows the entire sample in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Multiple3DTransformationsExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/MultipleTransformationsExample.xaml#multiple3dtransformationsexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="e1519-108">예제</span><span class="sxs-lookup"><span data-stu-id="e1519-108">Example</span></span>  
 <span data-ttu-id="e1519-109">다음은 전체 샘플 코드에서입니다.</span><span class="sxs-lookup"><span data-stu-id="e1519-109">Below is the entire sample in code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/MultipleTransformationsExample.cs#multiple3dtransformationscodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/multipletransformationsexample.vb#multiple3dtransformationscodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="e1519-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e1519-110">See Also</span></span>  
 [<span data-ttu-id="e1519-111">3차원 모델의 배율 변환</span><span class="sxs-lookup"><span data-stu-id="e1519-111">Transform the Scale of a 3-D Model</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-transform-the-scale-of-a-3-d-model.md)
