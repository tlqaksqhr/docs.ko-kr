---
title: '방법: InkCanvas에 데이터 바인딩'
ms.date: 03/30/2017
helpviewer_keywords:
- InkCanvas [WPF], binding data to
- binding data [WPF], to InkCanvas
ms.assetid: 8d6b4d9e-ea7f-4412-ba83-3feccec5a515
ms.openlocfilehash: 4081ae7dd6854934804062cfce60d10106c1e1d3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543172"
---
# <a name="how-to-data-bind-to-an-inkcanvas"></a><span data-ttu-id="cb22f-102">방법: InkCanvas에 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="cb22f-102">How to: Data Bind to an InkCanvas</span></span>
## <a name="example"></a><span data-ttu-id="cb22f-103">예제</span><span class="sxs-lookup"><span data-stu-id="cb22f-103">Example</span></span>  
 <span data-ttu-id="cb22f-104">다음 예제에서는 바인딩하는 방법을 <xref:System.Windows.Controls.InkCanvas.Strokes%2A> 속성은 <xref:System.Windows.Controls.InkCanvas> 다른 <xref:System.Windows.Controls.InkCanvas>합니다.</span><span class="sxs-lookup"><span data-stu-id="cb22f-104">The following example demonstrates how to bind the <xref:System.Windows.Controls.InkCanvas.Strokes%2A> property of an <xref:System.Windows.Controls.InkCanvas> to another <xref:System.Windows.Controls.InkCanvas>.</span></span>  
  
 [!code-xaml[InkCanvasBindingSnippet#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#2)]  
  
 <span data-ttu-id="cb22f-105">다음 예제에서는 바인딩하는 방법을 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> 속성을 데이터 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="cb22f-105">The following example demonstrates how to bind the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> property to a data source.</span></span>  
  
 [!code-xaml[InkCanvasBindingSnippet#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#3)]  
[!code-xaml[InkCanvasBindingSnippet#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#4)]  
  
 <span data-ttu-id="cb22f-106">다음 예제에서는 두 개의 선언 <xref:System.Windows.Controls.InkCanvas> XAML에서 개체를 다른 데이터 소스 간의 데이터 바인딩을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb22f-106">The following example declares two <xref:System.Windows.Controls.InkCanvas> objects in XAML and establishes data binding between them and other data sources.</span></span>  <span data-ttu-id="cb22f-107">첫 번째 <xref:System.Windows.Controls.InkCanvas>라는 `ic`, 두 데이터 소스에 바인딩되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb22f-107">The first <xref:System.Windows.Controls.InkCanvas>, called `ic`, is bound to two data sources.</span></span>  <span data-ttu-id="cb22f-108"><xref:System.Windows.Controls.InkCanvas.EditingMode%2A> 및 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> 속성에 `ic` 에 바인딩된 <xref:System.Windows.Controls.ListBox> 차례로 XAML에 정의 된 배열에 바인딩되는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="cb22f-108">The <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> and <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> properties on `ic` are bound to <xref:System.Windows.Controls.ListBox> objects, which are in turn bound to arrays defined in the XAML.</span></span>  <span data-ttu-id="cb22f-109"><xref:System.Windows.Controls.InkCanvas.EditingMode%2A>, <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, 및 <xref:System.Windows.Controls.InkCanvas.Strokes%2A> 의 두 번째 속성 <xref:System.Windows.Controls.InkCanvas> 바인딩된 첫 번째 <xref:System.Windows.Controls.InkCanvas>, `ic`합니다.</span><span class="sxs-lookup"><span data-stu-id="cb22f-109">The <xref:System.Windows.Controls.InkCanvas.EditingMode%2A>, <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, and <xref:System.Windows.Controls.InkCanvas.Strokes%2A> properties of the second <xref:System.Windows.Controls.InkCanvas> are bound to the first <xref:System.Windows.Controls.InkCanvas>, `ic`.</span></span>  
  
 [!code-xaml[InkCanvasBindingSnippet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window1.xaml#1)]
