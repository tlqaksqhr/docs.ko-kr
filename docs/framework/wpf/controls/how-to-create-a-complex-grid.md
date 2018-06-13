---
title: '방법: 복잡한 모눈 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- calendar [WPF], creating
- monthly calendar [WPF], creating
- Grid control [WPF], creating [WPF], complex grid
ms.assetid: 4ce3040a-a156-4364-9596-98ca1eca5550
ms.openlocfilehash: 49bf9781d56b93fd4529f3c9b62deb171e69155f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33553597"
---
# <a name="how-to-create-a-complex-grid"></a><span data-ttu-id="f5246-102">방법: 복잡한 모눈 만들기</span><span class="sxs-lookup"><span data-stu-id="f5246-102">How to: Create a Complex Grid</span></span>
<span data-ttu-id="f5246-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Grid> 월별 달력 처럼 보이는 레이아웃을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5246-103">This example shows how to use a <xref:System.Windows.Controls.Grid> to create layout that looks like a monthly calendar.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5246-104">예제</span><span class="sxs-lookup"><span data-stu-id="f5246-104">Example</span></span>  
 <span data-ttu-id="f5246-105">다음 예제는 8 개의 행과 열이 8 개를 사용 하 여 정의 <xref:System.Windows.Controls.RowDefinition> 및 <xref:System.Windows.Controls.ColumnDefinition> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="f5246-105">The following example defines eight rows and eight columns by using the <xref:System.Windows.Controls.RowDefinition> and <xref:System.Windows.Controls.ColumnDefinition> classes.</span></span> <span data-ttu-id="f5246-106">사용 하 여는 <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType> 및 <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType> 와 함께 연결 된 속성을 <xref:System.Windows.Shapes.Rectangle> 요소에는 다양 한 열과 행의 배경을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="f5246-106">It uses the <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType> and <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType> attached properties, together with <xref:System.Windows.Shapes.Rectangle> elements, which fill the backgrounds of various columns and rows.</span></span> <span data-ttu-id="f5246-107">각 셀에 요소가 둘 이상 있을 수 있으므로이 디자인은 가능한 한 <xref:System.Windows.Controls.Grid>, 원칙 차이 <xref:System.Windows.Controls.Grid> 및 <xref:System.Windows.Documents.Table>합니다.</span><span class="sxs-lookup"><span data-stu-id="f5246-107">This design is possible because more than one element can exist in each cell in a <xref:System.Windows.Controls.Grid>, a principle difference between <xref:System.Windows.Controls.Grid> and <xref:System.Windows.Documents.Table>.</span></span>  
  
 <span data-ttu-id="f5246-108">이 예에서는 사용 하는 세로 그라데이션을 <xref:System.Windows.Shapes.Shape.Fill%2A> 열과 행이 시각적 표현 및 달력의 가독성을 높이기 위해.</span><span class="sxs-lookup"><span data-stu-id="f5246-108">The example uses vertical gradients to <xref:System.Windows.Shapes.Shape.Fill%2A> the columns and rows in order to improve the visual presentation and readability of the calendar.</span></span> <span data-ttu-id="f5246-109">스타일의 <xref:System.Windows.Controls.TextBlock> 요소는 날짜와 요일을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f5246-109">Styled <xref:System.Windows.Controls.TextBlock> elements represent the dates and days of the week.</span></span> <span data-ttu-id="f5246-110"><xref:System.Windows.Controls.TextBlock> 요소를 사용 하 여 배치 셀 내에서 반드시는 <xref:System.Windows.FrameworkElement.Margin%2A> 속성 및 응용 프로그램에 대 한 스타일 내에 정의 된 맞춤 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="f5246-110"><xref:System.Windows.Controls.TextBlock> elements are absolutely positioned within their cells by using the <xref:System.Windows.FrameworkElement.Margin%2A> property and alignment properties that are defined within the style for the application.</span></span>  
  
 [!code-xaml[GridComplex#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridComplex/CS/default.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="f5246-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f5246-111">See Also</span></span>  
 <xref:System.Windows.Controls.Grid>  
 <xref:System.Windows.Documents.TableCell>  
 [<span data-ttu-id="f5246-112">단색 및 그라데이션을 사용한 그리기 개요</span><span class="sxs-lookup"><span data-stu-id="f5246-112">Painting with Solid Colors and Gradients Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [<span data-ttu-id="f5246-113">패널 개요</span><span class="sxs-lookup"><span data-stu-id="f5246-113">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="f5246-114">테이블 개요</span><span class="sxs-lookup"><span data-stu-id="f5246-114">Table Overview</span></span>](../../../../docs/framework/wpf/advanced/table-overview.md)
