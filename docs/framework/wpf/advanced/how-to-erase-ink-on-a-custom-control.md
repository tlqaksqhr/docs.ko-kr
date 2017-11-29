---
title: "방법: 사용자 지정 컨트롤에서 잉크 지우기"
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
- custom controls [WPF], erasing ink on
- ink [WPF], erasing on custom control
ms.assetid: d88c50f9-b4d8-4962-a28b-67d6a15a5fe0
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 23d234d97d6b25394df87016f0671d86b10a2853
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-erase-ink-on-a-custom-control"></a><span data-ttu-id="d4263-102">방법: 사용자 지정 컨트롤에서 잉크 지우기</span><span class="sxs-lookup"><span data-stu-id="d4263-102">How to: Erase Ink on a Custom Control</span></span>
<span data-ttu-id="d4263-103"><xref:System.Windows.Ink.IncrementalStrokeHitTester> 현재 그려진된 스트로크에 다른 획 교차 하는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4263-103">The <xref:System.Windows.Ink.IncrementalStrokeHitTester> determines whether the currently drawn stroke intersects another stroke.</span></span>  <span data-ttu-id="d4263-104">앱을 통해 컨트롤을 만드는 사용자가 스트로크 일부를 지울 수 유용, 방식에서 할 수 있는 사용자는 <xref:System.Windows.Controls.InkCanvas> 때는 <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> 로 설정 된 <xref:System.Windows.Controls.InkCanvasEditingMode.EraseByPoint>합니다.</span><span class="sxs-lookup"><span data-stu-id="d4263-104">This is useful for creating a control that enables a user to erase parts of a stroke, the way a user can on an <xref:System.Windows.Controls.InkCanvas> when the <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> is set to <xref:System.Windows.Controls.InkCanvasEditingMode.EraseByPoint>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4263-105">예제</span><span class="sxs-lookup"><span data-stu-id="d4263-105">Example</span></span>  
 <span data-ttu-id="d4263-106">다음 예제에서는 일부 스트로크를 지울 수 있는 사용자 지정 컨트롤을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d4263-106">The following example creates a custom control that enables the user to erase parts of strokes.</span></span>  <span data-ttu-id="d4263-107">이 예제는 초기화 될 때 잉크를 포함 하는 컨트롤을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d4263-107">This example creates a control that contains ink when it is initialized.</span></span>  <span data-ttu-id="d4263-108">잉크를 수집 하는 컨트롤을 만들려면 참조 [잉크 입력 컨트롤을 만드는](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d4263-108">To create a control that collects ink, see [Creating an Ink Input Control](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md).</span></span>  
  
 [!code-csharp[HowToEraseInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToEraseInk/CSharp/InkEraser.cs#1)]
 [!code-vb[HowToEraseInk#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToEraseInk/VisualBasic/InkEraser.vb#1)]
