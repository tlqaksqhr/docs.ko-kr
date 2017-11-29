---
title: "방법: 동기적으로 Storyboard 검색"
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
- seeking Storyboards synchronously [WPF]
- Storyboards [WPF], seeking synchronously
ms.assetid: 03e06271-a946-4810-88ea-3fb4cfa9e0f1
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 45d71dde85ea65e45a36b4f938e1fd5135cc0e00
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-seek-a-storyboard-synchronously"></a><span data-ttu-id="7627b-102">방법: 동기적으로 Storyboard 검색</span><span class="sxs-lookup"><span data-stu-id="7627b-102">How to: Seek a Storyboard Synchronously</span></span>
<span data-ttu-id="7627b-103">사용 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A> 의 메서드는 <xref:System.Windows.Media.Animation.Storyboard> 동기적으로 검색 된 스토리 보드 애니메이션 위치 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7627b-103">The following example shows how to use the <xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A> method of a <xref:System.Windows.Media.Animation.Storyboard> to seek to any position in a storyboard animation synchronously.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7627b-104">예제</span><span class="sxs-lookup"><span data-stu-id="7627b-104">Example</span></span>  
 <span data-ttu-id="7627b-105">다음은 샘플에 대한 XAML 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="7627b-105">The following is the XAML markup for the sample.</span></span>  
  
 [!code-xaml[SeekStoryboard_snip#SeekStoryboardSynchronouslyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardSynchronouslyExample.xaml#seekstoryboardsynchronouslyexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="7627b-106">예제</span><span class="sxs-lookup"><span data-stu-id="7627b-106">Example</span></span>  
 <span data-ttu-id="7627b-107">다음은 위의 XAML 코드와 함께 사용되는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="7627b-107">The following is the code used with the XAML code above.</span></span>  
  
 [!code-csharp[SeekStoryboard_snip#SeekStoryboardSynchronouslyCodeBehindExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardSynchronouslyExample.xaml.cs#seekstoryboardsynchronouslycodebehindexamplewholepage)]
 [!code-vb[SeekStoryboard_snip#SeekStoryboardSynchronouslyCodeBehindExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SeekStoryboard_snip/VisualBasic/SeekStoryboardSynchronouslyExample.xaml.vb#seekstoryboardsynchronouslycodebehindexamplewholepage)]
