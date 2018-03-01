---
title: "방법: 캔버스 위치 지정 속성 가져오기 또는 설정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Canvas control [WPF], setting positioning properties
ms.assetid: 1636b950-2b5a-4507-8a10-c5034cc58b1c
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d2b01657088c388ad09037716278dc0788de2abb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-get-or-set-canvas-positioning-properties"></a><span data-ttu-id="fae8d-102">방법: 캔버스 위치 지정 속성 가져오기 또는 설정</span><span class="sxs-lookup"><span data-stu-id="fae8d-102">How to: Get or Set Canvas Positioning Properties</span></span>
<span data-ttu-id="fae8d-103">위치 지정 메서드를 사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Canvas> 요소 자식 콘텐츠를 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="fae8d-103">This example shows how to use the positioning methods of the <xref:System.Windows.Controls.Canvas> element to position child content.</span></span> <span data-ttu-id="fae8d-104">콘텐츠를 사용 하 여이 예제는 <xref:System.Windows.Controls.ListBoxItem> 를 나타내는 값을 값의 인스턴스로 변환 위치 지정 <xref:System.Double>, 위치 지정에 대 한 필수 인수는 합니다.</span><span class="sxs-lookup"><span data-stu-id="fae8d-104">This example uses content in a <xref:System.Windows.Controls.ListBoxItem> to represent positioning values and converts the values into instances of <xref:System.Double>, which is a required argument for positioning.</span></span> <span data-ttu-id="fae8d-105">값 한 다음 다시 문자열로 변환 되어에 텍스트로 표시 되는 <xref:System.Windows.Controls.TextBlock> 사용 하 여 요소는 <xref:System.Windows.Controls.Canvas.GetLeft%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="fae8d-105">The values are then converted back into strings and displayed as text in a <xref:System.Windows.Controls.TextBlock> element by using the <xref:System.Windows.Controls.Canvas.GetLeft%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fae8d-106">예</span><span class="sxs-lookup"><span data-stu-id="fae8d-106">Example</span></span>  
 <span data-ttu-id="fae8d-107">다음 예제에서는 한 <xref:System.Windows.Controls.ListBox> 11 개의 선택 가능한 요소 <xref:System.Windows.Controls.ListBoxItem> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="fae8d-107">The following example creates a <xref:System.Windows.Controls.ListBox> element that has eleven selectable <xref:System.Windows.Controls.ListBoxItem> elements.</span></span> <span data-ttu-id="fae8d-108"><xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> 이벤트 트리거는 `ChangeLeft` 이후 코드 블록이 정의 하는 사용자 지정 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="fae8d-108">The <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event triggers the `ChangeLeft` custom method, which the subsequent code block defines.</span></span>  
  
 <span data-ttu-id="fae8d-109">각 <xref:System.Windows.Controls.ListBoxItem> 나타냅니다는 <xref:System.Double> 인수 중 하나는 값을 하는 <xref:System.Windows.Controls.Canvas.SetLeft%2A> 방식의 <xref:System.Windows.Controls.Canvas> 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fae8d-109">Each <xref:System.Windows.Controls.ListBoxItem> represents a <xref:System.Double> value, which is one of the arguments that the <xref:System.Windows.Controls.Canvas.SetLeft%2A> method of <xref:System.Windows.Controls.Canvas> accepts.</span></span> <span data-ttu-id="fae8d-110">사용 하려면는 <xref:System.Windows.Controls.ListBoxItem> 의 인스턴스를 나타내는 <xref:System.Double>를 먼저 변환 해야는 <xref:System.Windows.Controls.ListBoxItem> 을 올바른 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="fae8d-110">In order to use a <xref:System.Windows.Controls.ListBoxItem> to represent an instance of <xref:System.Double>, you must first convert the <xref:System.Windows.Controls.ListBoxItem> to the correct data type.</span></span>  
  
 [!code-xaml[CanvasPositioningProperties#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="fae8d-111">사용자는 <xref:System.Windows.Controls.ListBox> 호출 선택 항목을는 `ChangeLeft` 사용자 지정 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="fae8d-111">When a user changes the <xref:System.Windows.Controls.ListBox> selection, it invokes the `ChangeLeft` custom method.</span></span> <span data-ttu-id="fae8d-112">이 메서드는 전달는 <xref:System.Windows.Controls.ListBoxItem> 에 <xref:System.Windows.LengthConverter> 을 변환 하는 개체는 <xref:System.Windows.Controls.ContentControl.Content%2A> 의 <xref:System.Windows.Controls.ListBoxItem> 의 인스턴스로 <xref:System.Double> (이 값으로 변환 된 이미 사라졌는지는 <xref:System.String> 를 사용 하 여는 <xref:System.Windows.Controls.Control.ToString%2A> 방법)입니다.</span><span class="sxs-lookup"><span data-stu-id="fae8d-112">This method passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.LengthConverter> object, which converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Double> (notice that this value has already been converted to a <xref:System.String> by using the <xref:System.Windows.Controls.Control.ToString%2A> method).</span></span> <span data-ttu-id="fae8d-113">이 값은 다음에 다시 전달 되는 <xref:System.Windows.Controls.Canvas.SetLeft%2A> 및 <xref:System.Windows.Controls.Canvas.GetLeft%2A> 의 메서드 <xref:System.Windows.Controls.Canvas> 의 위치를 변경 하기 위해는 `text1` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="fae8d-113">This value is then passed back to the <xref:System.Windows.Controls.Canvas.SetLeft%2A> and <xref:System.Windows.Controls.Canvas.GetLeft%2A> methods of <xref:System.Windows.Controls.Canvas> in order to change the position of the `text1` object.</span></span>  
  
 [!code-csharp[CanvasPositioningProperties#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml.cs#2)]
 [!code-vb[CanvasPositioningProperties#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasPositioningProperties/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="fae8d-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fae8d-114">See Also</span></span>  
 <xref:System.Windows.Controls.Canvas>  
 <xref:System.Windows.Controls.ListBoxItem>  
 <xref:System.Windows.LengthConverter>  
 [<span data-ttu-id="fae8d-115">패널 개요</span><span class="sxs-lookup"><span data-stu-id="fae8d-115">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
