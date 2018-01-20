---
title: "방법: 이미지 잘라내기"
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
- images [WPF], cropping
- cropping images [WPF]
ms.assetid: c6bba109-c6e7-4cf8-bfe6-9cf8d01bb4fc
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 11f5b280635d2fe7b83d8c4496606ed02bc44149
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-crop-an-image"></a><span data-ttu-id="835d9-102">방법: 이미지 잘라내기</span><span class="sxs-lookup"><span data-stu-id="835d9-102">How to: Crop an Image</span></span>
<span data-ttu-id="835d9-103">이 예제에서는을 사용 하 여 이미지를 자를 <xref:System.Windows.Media.Imaging.CroppedBitmap>합니다.</span><span class="sxs-lookup"><span data-stu-id="835d9-103">This example shows how to crop an image using <xref:System.Windows.Media.Imaging.CroppedBitmap>.</span></span>  
  
 <span data-ttu-id="835d9-104"><xref:System.Windows.Media.Imaging.CroppedBitmap>주로 자른된 이미지의 버전을 인코딩하는 경우 파일에 저장할 합니다.</span><span class="sxs-lookup"><span data-stu-id="835d9-104"><xref:System.Windows.Media.Imaging.CroppedBitmap> is primarily used when encoding a cropped version of an image to save out to a file.</span></span> <span data-ttu-id="835d9-105">이미지 표시 목적으로 참조를 자르려면는 [클립 영역을 만들](http://msdn.microsoft.com/library/56e4bed6-78d7-4292-b917-d72d0b3e4376) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="835d9-105">To crop an image for display purposes see the [Create a Clip Region](http://msdn.microsoft.com/library/56e4bed6-78d7-4292-b917-d72d0b3e4376) topic.</span></span>  
  
## <a name="example"></a><span data-ttu-id="835d9-106">예</span><span class="sxs-lookup"><span data-stu-id="835d9-106">Example</span></span>  
 <span data-ttu-id="835d9-107">다음 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 아래의 샘플에 사용 되는 리소스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="835d9-107">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] defines resources used within the samples below.</span></span>  
  
 [!code-xaml[imageelementexample#CroppedXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml1)]  
  
 <span data-ttu-id="835d9-108">다음 예제에서는 사용 하 여 이미지는 <xref:System.Windows.Media.Imaging.CroppedBitmap> 소스로 합니다.</span><span class="sxs-lookup"><span data-stu-id="835d9-108">The following example creates an image using a <xref:System.Windows.Media.Imaging.CroppedBitmap> as its source.</span></span>  
  
 [!code-xaml[imageelementexample#CroppedXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml2)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp1)]
 [!code-vb[imageelementexample#CroppedCSharp1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp1)]  
  
 <span data-ttu-id="835d9-109"><xref:System.Windows.Media.Imaging.CroppedBitmap> 다른 원본으로 사용할 수도 있습니다 <xref:System.Windows.Media.Imaging.CroppedBitmap>, 자르기 체인입니다.</span><span class="sxs-lookup"><span data-stu-id="835d9-109">The <xref:System.Windows.Media.Imaging.CroppedBitmap> can also be used as the source of another <xref:System.Windows.Media.Imaging.CroppedBitmap>, chaining the cropping.</span></span> <span data-ttu-id="835d9-110"><xref:System.Windows.Media.Imaging.CroppedBitmap.SourceRect%2A> 소스 비트맵과 원래 이미지가 아니라 잘라 기준으로 하는 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="835d9-110">Note that the <xref:System.Windows.Media.Imaging.CroppedBitmap.SourceRect%2A> uses values that are relative to the source cropped bitmap and not the initial image.</span></span>  
  
 [!code-xaml[imageelementexample#CroppedXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml3)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp2)]
 [!code-vb[imageelementexample#CroppedCSharp2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp2)]  
  
## <a name="see-also"></a><span data-ttu-id="835d9-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="835d9-111">See Also</span></span>  
 [<span data-ttu-id="835d9-112">클립 영역 만들기</span><span class="sxs-lookup"><span data-stu-id="835d9-112">Create a Clip Region</span></span>](http://msdn.microsoft.com/library/56e4bed6-78d7-4292-b917-d72d0b3e4376)
