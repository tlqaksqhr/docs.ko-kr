---
title: "방법: 시각적 요소에 텍스트 그리기"
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
- typography [WPF], drawing text to visuals
- visuals [WPF], drawing text to
- text [WPF], drawing to visuals
- drawing [WPF], text to visuals
ms.assetid: fee4003c-e8a6-46ec-babd-2c7f4231a101
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 735a84a034587b1433403a45edc7c2f459340273
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-draw-text-to-a-visual"></a>방법: 시각적 요소에 텍스트 그리기
텍스트를 그리는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Media.DrawingVisual> 를 사용 하는 <xref:System.Windows.Media.DrawingContext> 개체입니다. 그리기 컨텍스트 호출에서 반환 되는 <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> 의 메서드는 <xref:System.Windows.Media.DrawingVisual> 개체입니다. 그리기 컨텍스트에 그래픽 및 텍스트를 그릴 수 있습니다.  
  
 텍스트를 그리는 그리기 컨텍스트에 사용 하 여는 <xref:System.Windows.Media.DrawingContext.DrawText%2A> 의 메서드는 <xref:System.Windows.Media.DrawingContext> 개체입니다. 내용을 그리기 컨텍스트에 그리기 작업을 완료 하는 경우 호출의 <xref:System.Windows.Media.DrawingContext.Close%2A> 메서드를 그리기 컨텍스트에 닫고 내용을 유지 합니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[DrawingVisualSample#110](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
>  위의 코드 예제가 발췌된 전체 코드 샘플을 보려면 [DrawingVisuals를 사용하여 적중 테스트 샘플](http://go.microsoft.com/fwlink/?LinkID=159994)을 참조하세요.
