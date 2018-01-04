---
title: "방법: 잉크 회전"
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
- ink [WPF], rotating
- rotating ink [WPF]
ms.assetid: fac36cc9-dd01-41ca-9bde-9d33e3790bbe
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 45a65a8d6c7d506cf74d98667527b8b5548af038
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-rotate-ink"></a><span data-ttu-id="be1b1-102">방법: 잉크 회전</span><span class="sxs-lookup"><span data-stu-id="be1b1-102">How to: Rotate Ink</span></span>
## <a name="example"></a><span data-ttu-id="be1b1-103">예</span><span class="sxs-lookup"><span data-stu-id="be1b1-103">Example</span></span>  
 <span data-ttu-id="be1b1-104">다음 예제에서는 복사에서 잉크는 <xref:System.Windows.Controls.InkCanvas> 에 <xref:System.Windows.Controls.Canvas> 를 포함 하는 <xref:System.Windows.Controls.InkPresenter>합니다.</span><span class="sxs-lookup"><span data-stu-id="be1b1-104">The following example copies the ink from an <xref:System.Windows.Controls.InkCanvas> to a <xref:System.Windows.Controls.Canvas> that contains an <xref:System.Windows.Controls.InkPresenter>.</span></span>  <span data-ttu-id="be1b1-105">응용 프로그램은 잉크를 복사할 때 것도 회전 잉크 시계 방향으로 90도 합니다.</span><span class="sxs-lookup"><span data-stu-id="be1b1-105">When the application copies the ink, it also rotates the ink 90 degrees clockwise.</span></span>  
  
 [!code-xaml[HowToRotateInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToRotateInk/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[HowToRotateInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToRotateInk/CSharp/Window1.xaml.cs#2)]  
  
## <a name="example"></a><span data-ttu-id="be1b1-106">예</span><span class="sxs-lookup"><span data-stu-id="be1b1-106">Example</span></span>  
 <span data-ttu-id="be1b1-107">다음 예제는 사용자 지정 <xref:System.Windows.Documents.Adorner> 에 스트로크를 회전 하는 <xref:System.Windows.Controls.InkPresenter>합니다.</span><span class="sxs-lookup"><span data-stu-id="be1b1-107">The following example is a custom <xref:System.Windows.Documents.Adorner> that rotates the strokes on an <xref:System.Windows.Controls.InkPresenter>.</span></span>  
  
 [!code-csharp[AdornerForStrokes#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornerForStrokes/CSharp/RotatingAdornerForStrokes.cs#1)]
 [!code-vb[AdornerForStrokes#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornerForStrokes/VisualBasic/RotatingAdornerForStrokes.vb#1)]  
  
 <span data-ttu-id="be1b1-108">다음 예제는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 파일을 정의 하는 <xref:System.Windows.Controls.InkPresenter> 잉크도 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="be1b1-108">The following example is a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file that defines an <xref:System.Windows.Controls.InkPresenter> and populates it with ink.</span></span> <span data-ttu-id="be1b1-109">`Window_Loaded` 에 사용자 지정 표시기를 추가 하는 이벤트 처리기는 <xref:System.Windows.Controls.InkPresenter>합니다.</span><span class="sxs-lookup"><span data-stu-id="be1b1-109">The `Window_Loaded` event handler adds the custom adorner to the <xref:System.Windows.Controls.InkPresenter>.</span></span>  
  
 [!code-xaml[AdornerForStrokes#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornerForStrokes/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[AdornerForStrokes#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornerForStrokes/CSharp/Window1.xaml.cs#3)]
 [!code-vb[AdornerForStrokes#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornerForStrokes/VisualBasic/Window1.xaml.vb#3)]
