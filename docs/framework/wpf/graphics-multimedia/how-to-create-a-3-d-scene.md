---
title: "방법: 3차원 장면 만들기"
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
- scenes [WPF], 3-D
- 3-D scenes
ms.assetid: adb4a598-71a2-4dd5-b677-ea3fc11b78b2
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f52642a1764a7db01d4ca330f3bf25bdca10fa06
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-3-d-scene"></a><span data-ttu-id="1610c-102">방법: 3차원 장면 만들기</span><span class="sxs-lookup"><span data-stu-id="1610c-102">How to: Create a 3-D Scene</span></span>
<span data-ttu-id="1610c-103">이 예제에는 회전 된 플랫 용지의 처럼 보이는 3 차원 개체를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1610c-103">This example shows how to create a 3-D object that looks like a flat sheet of paper which has been rotated.</span></span> <span data-ttu-id="1610c-104">A <xref:System.Windows.Controls.Viewport3D> 다음 구성 요소와 함께이 간단한 3 차원 장면의 만드는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1610c-104">A <xref:System.Windows.Controls.Viewport3D> along with the following components are used to create this simple 3-D scene:</span></span>  
  
-   <span data-ttu-id="1610c-105">카메라를 사용 하 여 만들어집니다는 <xref:System.Windows.Media.Media3D.PerspectiveCamera>합니다.</span><span class="sxs-lookup"><span data-stu-id="1610c-105">A camera is created using a <xref:System.Windows.Media.Media3D.PerspectiveCamera>.</span></span> <span data-ttu-id="1610c-106">카메라 3 차원 장면의의 일부를 볼 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1610c-106">The camera specifies what part of the 3-D scene is viewable.</span></span>  
  
-   <span data-ttu-id="1610c-107">3 차원 개체 (용지의)를 사용 하 여의 모양을 지정 하는 메시 만들어집니다는 <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> 속성 <xref:System.Windows.Media.Media3D.GeometryModel3D>합니다.</span><span class="sxs-lookup"><span data-stu-id="1610c-107">A mesh is created to specify the shape of 3-D object (sheet of paper) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
-   <span data-ttu-id="1610c-108">재질을 사용 하 여 개체 (이 샘플의 선형 그라데이션)의 화면에 표시할 지정는 <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> 속성 <xref:System.Windows.Media.Media3D.GeometryModel3D>합니다.</span><span class="sxs-lookup"><span data-stu-id="1610c-108">A material is specified to be displayed on the surface of the object (linear gradient in this sample) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
-   <span data-ttu-id="1610c-109">사용 하 여 개체에서 효율적인 광원 만들어집니다 <xref:System.Windows.Media.Media3D.DirectionalLight>합니다.</span><span class="sxs-lookup"><span data-stu-id="1610c-109">A light is created to shine on the object using <xref:System.Windows.Media.Media3D.DirectionalLight>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1610c-110">예</span><span class="sxs-lookup"><span data-stu-id="1610c-110">Example</span></span>  
 <span data-ttu-id="1610c-111">아래 코드에는 XAML에서 3 차원 장면의 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1610c-111">The code below shows how to create a 3-D scene in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Basic3DShapeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/Basic3DShapeExample.xaml#basic3dshapeexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="1610c-112">예</span><span class="sxs-lookup"><span data-stu-id="1610c-112">Example</span></span>  
 <span data-ttu-id="1610c-113">아래 코드에는 프로시저 코드에서 동일한 3d 장면을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1610c-113">The code below shows how to create the same 3-D scene in procedural code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="1610c-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1610c-114">See Also</span></span>  
 [<span data-ttu-id="1610c-115">3차원 그래픽 개요</span><span class="sxs-lookup"><span data-stu-id="1610c-115">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
