---
title: '방법: 3차원 모델의 배율 변환'
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], 3-D objects
- 3-D objects [WPF], scaling
ms.assetid: f3fdfe33-f7dc-44b0-84a5-e43b89947f35
ms.openlocfilehash: 3cca1a210a7dbe410ebaacaaf89c08de8c31c40e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561100"
---
# <a name="how-to-transform-the-scale-of-a-3-d-model"></a><span data-ttu-id="815ac-102">방법: 3차원 모델의 배율 변환</span><span class="sxs-lookup"><span data-stu-id="815ac-102">How to: Transform the Scale of a 3-D Model</span></span>
<span data-ttu-id="815ac-103">이 예에서는 3 차원 개체의 크기를 조정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="815ac-103">This example shows how to scale a 3-D object.</span></span> <span data-ttu-id="815ac-104">3 차원 개체의 크기를 조정 하려면 사용 된 <xref:System.Windows.Media.Media3D.ScaleTransform3D>합니다.</span><span class="sxs-lookup"><span data-stu-id="815ac-104">To scale a 3-D object, use a <xref:System.Windows.Media.Media3D.ScaleTransform3D>.</span></span> <span data-ttu-id="815ac-105"><xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>, 및 <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> 속성에 지정한 계수로 요소 크기 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="815ac-105">The <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>, and <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> properties resize the element by the factor you specify.</span></span> <span data-ttu-id="815ac-106">예를 들어 한 <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> 원래 너비의 150%로 개체를 확장 하는 1.5의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="815ac-106">For example, a <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> value of 1.5 stretches an object to 150 percent of its original width.</span></span> <span data-ttu-id="815ac-107">A <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> 값이 0.5 개체의 높이 50%로 축소 합니다.</span><span class="sxs-lookup"><span data-stu-id="815ac-107">A <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> value of 0.5 shrinks the height of an object by 50 percent.</span></span> <span data-ttu-id="815ac-108">아래 코드를 사용 하 여 보여 줍니다는 <xref:System.Windows.Media.Media3D.ScaleTransform3D> 에 대 한 변환으로는 <xref:System.Windows.Media.Media3D.GeometryModel3D>합니다.</span><span class="sxs-lookup"><span data-stu-id="815ac-108">The code below shows using a <xref:System.Windows.Media.Media3D.ScaleTransform3D> as the transform for a <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="815ac-109">예제</span><span class="sxs-lookup"><span data-stu-id="815ac-109">Example</span></span>  
 <span data-ttu-id="815ac-110">다음 코드에서는 전체 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="815ac-110">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="815ac-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="815ac-111">See Also</span></span>  
 [<span data-ttu-id="815ac-112">3차원 변환에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="815ac-112">Animate 3-D Translations</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-3-d-translations.md)  
 [<span data-ttu-id="815ac-113">3차원 장면 만들기</span><span class="sxs-lookup"><span data-stu-id="815ac-113">Create a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)  
 [<span data-ttu-id="815ac-114">3차원 그래픽 개요</span><span class="sxs-lookup"><span data-stu-id="815ac-114">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
