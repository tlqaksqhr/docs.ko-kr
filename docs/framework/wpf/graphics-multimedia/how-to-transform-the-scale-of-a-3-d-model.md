---
title: "방법: 3차원 모델의 배율 변환"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- scaling [WPF], 3-D objects
- 3-D objects [WPF], scaling
ms.assetid: f3fdfe33-f7dc-44b0-84a5-e43b89947f35
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 14f650d968ca715e47269e0765d791856b681237
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-transform-the-scale-of-a-3-d-model"></a>방법: 3차원 모델의 배율 변환
이 예에서는 3 차원 개체의 크기를 조정 하는 방법을 보여 줍니다. 3 차원 개체의 크기를 조정 하려면 사용 된 <xref:System.Windows.Media.Media3D.ScaleTransform3D>합니다. <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>, 및 <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> 속성에 지정한 계수로 요소 크기 조정 합니다. 예를 들어 한 <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> 원래 너비의 150%로 개체를 확장 하는 1.5의 값입니다. A <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> 값이 0.5 개체의 높이 50%로 축소 합니다. 아래 코드를 사용 하 여 보여 줍니다는 <xref:System.Windows.Media.Media3D.ScaleTransform3D> 에 대 한 변환으로는 <xref:System.Windows.Media.Media3D.GeometryModel3D>합니다.  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexampleinline1)]  
  
## <a name="example"></a>예  
 다음 코드에서는 전체 예제를 보여 줍니다.  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexamplewholepage)]  
  
## <a name="see-also"></a>참고 항목  
 [3차원 변환에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-3-d-translations.md)  
 [3차원 장면 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)  
 [3차원 그래픽 개요](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
