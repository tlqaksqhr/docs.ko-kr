---
title: "방법: 이미지를 축소판으로 로드"
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
- loading images as thumbnails [WPF]
- images [WPF], loading as thumbnails
- thumbnails [WPF], loading images as
ms.assetid: 02e055a0-54df-499a-b8b6-ab6ff7535cff
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0e91e032162e6e652daf18268d05c2a7db291bfc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-load-an-image-as-a-thumbnail"></a><span data-ttu-id="8cda0-102">방법: 이미지를 축소판으로 로드</span><span class="sxs-lookup"><span data-stu-id="8cda0-102">How to: Load an Image as a Thumbnail</span></span>
<span data-ttu-id="8cda0-103">다음 예에는 로드 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.Image> 응용 프로그램 메모리를 절약 하기 위해 축소판 그림으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cda0-103">The following examples show how to load an <xref:System.Windows.Controls.Image> as a thumbnail to conserve application memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8cda0-104">예</span><span class="sxs-lookup"><span data-stu-id="8cda0-104">Example</span></span>  
 <span data-ttu-id="8cda0-105">다음 예제에서는 <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> 속성은 <xref:System.Windows.Media.Imaging.BitmapImage> 에 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 이미지를 로드 하는 데 필요한 메모리를 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cda0-105">The following example sets the <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> property of a <xref:System.Windows.Media.Imaging.BitmapImage> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to reduce the memory required to load the image.</span></span>  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a><span data-ttu-id="8cda0-106">예</span><span class="sxs-lookup"><span data-stu-id="8cda0-106">Example</span></span>  
 <span data-ttu-id="8cda0-107">다음 예제에서는 <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> 의 속성을 <xref:System.Windows.Media.Imaging.BitmapImage> 이미지를 로드 하는 데 필요한 메모리를 줄이기 위해 코드에서.</span><span class="sxs-lookup"><span data-stu-id="8cda0-107">The following example sets the <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> property of a <xref:System.Windows.Media.Imaging.BitmapImage> in code to reduce the memory required to load the image.</span></span>  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a><span data-ttu-id="8cda0-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8cda0-108">See Also</span></span>  
 [<span data-ttu-id="8cda0-109">이미징 개요</span><span class="sxs-lookup"><span data-stu-id="8cda0-109">Imaging Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
