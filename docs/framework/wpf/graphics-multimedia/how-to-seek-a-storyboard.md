---
title: '방법: Storyboard 검색'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], seeking
- seeking Storyboards [WPF]
ms.assetid: 887bb39a-0c2a-4ae8-956d-1d9f6f8ebbfc
ms.openlocfilehash: 656a5cb38461f71698a312e6382a3a9c29158cc5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560287"
---
# <a name="how-to-seek-a-storyboard"></a><span data-ttu-id="24ed8-102">방법: Storyboard 검색</span><span class="sxs-lookup"><span data-stu-id="24ed8-102">How to: Seek a Storyboard</span></span>
<span data-ttu-id="24ed8-103">사용 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> 의 메서드는 <xref:System.Windows.Media.Animation.Storyboard> 스토리 보드 애니메이션에서 모든 위치로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24ed8-103">The following example shows how to use the <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> method of a <xref:System.Windows.Media.Animation.Storyboard> to jump to any position in a storyboard animation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24ed8-104">예제</span><span class="sxs-lookup"><span data-stu-id="24ed8-104">Example</span></span>  
 <span data-ttu-id="24ed8-105">다음은 샘플에 대한 XAML 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="24ed8-105">Below is the XAML markup for the sample.</span></span>  
  
 [!code-xaml[SeekStoryboard_snip#SeekStoryboardExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardExample.xaml#seekstoryboardexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="24ed8-106">예제</span><span class="sxs-lookup"><span data-stu-id="24ed8-106">Example</span></span>  
 <span data-ttu-id="24ed8-107">다음은 위의 XAML 코드와 함께 사용되는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="24ed8-107">Below is the code used with the XAML code above.</span></span>  
  
 [!code-csharp[SeekStoryboard_snip#SeekStoryboardCodeBehindExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardExample.xaml.cs#seekstoryboardcodebehindexamplewholepage)]
 [!code-vb[SeekStoryboard_snip#SeekStoryboardCodeBehindExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SeekStoryboard_snip/VisualBasic/SeekStoryboardExample.xaml.vb#seekstoryboardcodebehindexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="24ed8-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="24ed8-108">See Also</span></span>  
 [<span data-ttu-id="24ed8-109">동기적으로 Storyboard 검색</span><span class="sxs-lookup"><span data-stu-id="24ed8-109">Seek a Storyboard Synchronously</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-seek-a-storyboard-synchronously.md)
