---
title: "방법: 시각적 요소에 텍스트 그리기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "그리기, 표시에 텍스트"
  - "텍스트, 표시에 그리기"
  - "입력 체계, 표시에 텍스트 그리기"
  - "표시, 텍스트 그리기"
ms.assetid: fee4003c-e8a6-46ec-babd-2c7f4231a101
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: 시각적 요소에 텍스트 그리기
다음 예제에서는 <xref:System.Windows.Media.DrawingContext> 개체를 사용하여 <xref:System.Windows.Media.DrawingVisual>에 텍스트를 그리는 방법을 보여 줍니다.  <xref:System.Windows.Media.DrawingVisual> 개체의 <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> 메서드를 호출하면 그리기 컨텍스트가 반환됩니다.  그리기 컨텍스트에 그래픽 및 텍스트를 그릴 수 있습니다.  
  
 그리기 컨텍스트에 텍스트를 그리려면 <xref:System.Windows.Media.DrawingContext> 개체의 <xref:System.Windows.Media.DrawingContext.DrawText%2A> 메서드를 사용하십시오.  그리기 컨텍스트에서 콘텐츠 그리기가 끝나면 <xref:System.Windows.Media.DrawingContext.Close%2A> 메서드를 호출하여 그리기 컨텍스트를 닫고 콘텐츠를 저장합니다.  
  
## 예제  
 [!code-csharp[DrawingVisualSample#110](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
>  앞의 코드 예제를 추출한 전체 코드 샘플을 보려면 [Hit Test Using DrawingVisuals 샘플](http://go.microsoft.com/fwlink/?LinkID=159994)을 참조하십시오.