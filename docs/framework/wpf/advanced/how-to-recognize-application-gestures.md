---
title: '방법: 응용 프로그램 제스처 인식'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application gestures [WPF], recognizing
- gestures [WPF], recognizing
ms.assetid: d58b740f-5192-4a3e-af59-7aa162e6ca15
ms.openlocfilehash: 82ca91fc9e3745012d82357991b67f398079f1f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543695"
---
# <a name="how-to-recognize-application-gestures"></a><span data-ttu-id="6f9ca-102">방법: 응용 프로그램 제스처 인식</span><span class="sxs-lookup"><span data-stu-id="6f9ca-102">How To: Recognize Application Gestures</span></span>
<span data-ttu-id="6f9ca-103">다음 예제에서는 사용자가 때 잉크를 지울 수는 <xref:System.Windows.Ink.ApplicationGesture.ScratchOut> 제스처는 <xref:System.Windows.Controls.InkCanvas>합니다.</span><span class="sxs-lookup"><span data-stu-id="6f9ca-103">The following example demonstrates how to erase ink when a user makes a <xref:System.Windows.Ink.ApplicationGesture.ScratchOut> gesture on an <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="6f9ca-104">이 예에서는 가정는 <xref:System.Windows.Controls.InkCanvas>라는 `inkCanvas1`, XAML 파일에서 선언 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f9ca-104">This example assumes an <xref:System.Windows.Controls.InkCanvas>, called `inkCanvas1`, is declared in the XAML file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f9ca-105">예제</span><span class="sxs-lookup"><span data-stu-id="6f9ca-105">Example</span></span>  
 [!code-csharp[HowToRecognizeGestures#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToRecognizeGestures/CSharp/Window1.xaml.cs#1)]
 [!code-vb[HowToRecognizeGestures#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToRecognizeGestures/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="6f9ca-106">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6f9ca-106">See Also</span></span>  
 <xref:System.Windows.Ink.ApplicationGesture>  
 <xref:System.Windows.Controls.InkCanvas>  
 <xref:System.Windows.Controls.InkCanvas.Gesture>
