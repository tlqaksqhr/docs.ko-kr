---
title: "방법: InkCanvas에 데이터 바인딩"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- InkCanvas [WPF], binding data to
- binding data [WPF], to InkCanvas
ms.assetid: 8d6b4d9e-ea7f-4412-ba83-3feccec5a515
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fdcd67f972dafa2de7fb74e01b4a3c22dfd848fb
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-data-bind-to-an-inkcanvas"></a>방법: InkCanvas에 데이터 바인딩
## <a name="example"></a>예제  
 다음 예제에서는 바인딩하는 방법을 <xref:System.Windows.Controls.InkCanvas.Strokes%2A> 속성은 <xref:System.Windows.Controls.InkCanvas> 다른 <xref:System.Windows.Controls.InkCanvas>합니다.  
  
 [!code-xaml[InkCanvasBindingSnippet#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#2)]  
  
 다음 예제에서는 바인딩하는 방법을 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> 속성을 데이터 소스입니다.  
  
 [!code-xaml[InkCanvasBindingSnippet#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#3)]  
[!code-xaml[InkCanvasBindingSnippet#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#4)]  
  
 다음 예제에서는 두 개의 선언 <xref:System.Windows.Controls.InkCanvas> XAML에서 개체를 다른 데이터 소스 간의 데이터 바인딩을 설정 합니다.  첫 번째 <xref:System.Windows.Controls.InkCanvas>라는 `ic`, 두 데이터 소스에 바인딩되어 있습니다.  <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> 및 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> 속성에 `ic` 에 바인딩된 <xref:System.Windows.Controls.ListBox> 차례로 XAML에 정의 된 배열에 바인딩되는 개체입니다.  <xref:System.Windows.Controls.InkCanvas.EditingMode%2A>, <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, 및 <xref:System.Windows.Controls.InkCanvas.Strokes%2A> 의 두 번째 속성 <xref:System.Windows.Controls.InkCanvas> 바인딩된 첫 번째 <xref:System.Windows.Controls.InkCanvas>, `ic`합니다.  
  
 [!code-xaml[InkCanvasBindingSnippet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window1.xaml#1)]
