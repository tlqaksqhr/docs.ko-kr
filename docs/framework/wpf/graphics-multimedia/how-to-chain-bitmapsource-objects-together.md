---
title: '방법: 여러 BitmapSource 개체 연결'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BitmapSource objects [WPF], chaining
- graphics [WPF], chaining BitmapSource objects
- chaining BitmapSource objects [WPF]
ms.assetid: 32d88853-395b-4855-9685-51a482a3b421
ms.openlocfilehash: 5c70b6ec132234959404203fb62567ddb0acf762
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558867"
---
# <a name="how-to-chain-bitmapsource-objects-together"></a><span data-ttu-id="3a4a2-102">방법: 여러 BitmapSource 개체 연결</span><span class="sxs-lookup"><span data-stu-id="3a4a2-102">How to: Chain BitmapSource Objects Together</span></span>
<span data-ttu-id="3a4a2-103">이 예제 연결 하 여 이미지 소스를 다양 한 효과 적용 하는 방법을 여러 <xref:System.Windows.Media.Imaging.BitmapSource> 파생 개체를 함께 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4a2-103">This example shows how you can apply a variety of effects to an image source by chaining multiple <xref:System.Windows.Media.Imaging.BitmapSource> derived objects together.</span></span>  
  
 <span data-ttu-id="3a4a2-104">다음 예제에서는 연결을 사용하여 픽셀 형식의 이미지 소스를 대칭 이동하고 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="3a4a2-104">The following example uses chaining to flip and change the pixel format of the source of an image.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a4a2-105">예제</span><span class="sxs-lookup"><span data-stu-id="3a4a2-105">Example</span></span>  
 [!code-xaml[ImagingSnippetGallery_snip#ChainedBitmapSourcesXamlExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_snip/CS/ChainedBitmapSourcesExample.xaml#chainedbitmapsourcesxamlexamplewholepage)]  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#ChainedBitmapSourcesCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/ChainedBitmapSourcesExample.cs#chainedbitmapsourcescodeexamplewholepage)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#ChainedBitmapSourcesCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/ChainedBitmapSourcesExample.vb#chainedbitmapsourcescodeexamplewholepage)]
