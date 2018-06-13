---
title: '방법: ColumnDefinitionsCollections 및 RowDefinitionsCollections를 사용하여 열 및 행 조작'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Grid class
- Grid control [WPF], ColumnDefinitionCollection class
- Grid control [WPF], RowDefinitionCollection class
ms.assetid: bfc7160a-45f2-4e17-9961-df414dfb13c5
ms.openlocfilehash: 6ff5ad4825bd9f683d895341dd084c00f68aa27b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33553077"
---
# <a name="how-to-manipulate-columns-and-rows-by-using-columndefinitionscollections-and-rowdefinitionscollections"></a><span data-ttu-id="5b20a-102">방법: ColumnDefinitionsCollections 및 RowDefinitionsCollections를 사용하여 열 및 행 조작</span><span class="sxs-lookup"><span data-stu-id="5b20a-102">How to: Manipulate Columns and Rows by Using ColumnDefinitionsCollections and RowDefinitionsCollections</span></span>
<span data-ttu-id="5b20a-103">메서드를 사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.ColumnDefinitionCollection> 및 <xref:System.Windows.Controls.RowDefinitionCollection> 추가, 지우기 또는 행 또는 열의 내용을 계산과 같은 동작을 수행 하는 클래스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b20a-103">This example shows how to use the methods in the <xref:System.Windows.Controls.ColumnDefinitionCollection> and <xref:System.Windows.Controls.RowDefinitionCollection> classes to perform actions like adding, clearing, or counting the contents of rows or columns.</span></span> <span data-ttu-id="5b20a-104">예를 들어, <xref:System.Windows.Controls.ColumnDefinitionCollection.Add%2A>, <xref:System.Windows.Controls.ColumnDefinitionCollection.Clear%2A>, 또는 <xref:System.Windows.Controls.ColumnDefinitionCollection.Count%2A> 에 포함 된 항목을 <xref:System.Windows.Controls.ColumnDefinition> 또는 <xref:System.Windows.Controls.RowDefinition>합니다.</span><span class="sxs-lookup"><span data-stu-id="5b20a-104">For example, you can <xref:System.Windows.Controls.ColumnDefinitionCollection.Add%2A>, <xref:System.Windows.Controls.ColumnDefinitionCollection.Clear%2A>, or <xref:System.Windows.Controls.ColumnDefinitionCollection.Count%2A> the items that are included in a <xref:System.Windows.Controls.ColumnDefinition> or <xref:System.Windows.Controls.RowDefinition>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b20a-105">예제</span><span class="sxs-lookup"><span data-stu-id="5b20a-105">Example</span></span>  
 <span data-ttu-id="5b20a-106">다음 예제에서는 한 <xref:System.Windows.Controls.Grid> 인 요소는 <xref:System.Windows.FrameworkElement.Name%2A> 의 `grid1`합니다.</span><span class="sxs-lookup"><span data-stu-id="5b20a-106">The following example creates a <xref:System.Windows.Controls.Grid> element with a <xref:System.Windows.FrameworkElement.Name%2A> of `grid1`.</span></span> <span data-ttu-id="5b20a-107"><xref:System.Windows.Controls.Grid> 포함 한 <xref:System.Windows.Controls.StackPanel> 를 보유 하는 <xref:System.Windows.Controls.Button> 다른 수집 방법으로 제어 각 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5b20a-107">The <xref:System.Windows.Controls.Grid> contains a <xref:System.Windows.Controls.StackPanel> that holds <xref:System.Windows.Controls.Button> elements, each controlled by a different collection method.</span></span> <span data-ttu-id="5b20a-108">클릭는 <xref:System.Windows.Controls.Button>, 코드 숨김 파일에서 메서드 호출을 활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b20a-108">When you click a <xref:System.Windows.Controls.Button>, it activates a method call in the code-behind file.</span></span>  
  
 [!code-xaml[ColumnDefinitionsGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ColumnDefinitionsGrid/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="5b20a-109">일련의 각에 해당 하는 사용자 지정 메서드를 정의 하는이 예제는 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트에는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="5b20a-109">This example defines a series of custom methods, each corresponding to a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event in the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file.</span></span> <span data-ttu-id="5b20a-110">열과 행의 수를 변경할 수는 <xref:System.Windows.Controls.Grid> 에서 여러 가지 방법으로, 포함 또는 추가 하 고, 행 및 열을 제거 하 고, 행과 열의 총 수를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b20a-110">You can change the number of columns and rows in the <xref:System.Windows.Controls.Grid> in several ways, which includes adding or removing rows and columns; and counting the total number of rows and columns.</span></span> <span data-ttu-id="5b20a-111">방지 하기 위해 <xref:System.ArgumentOutOfRangeException> 및 <xref:System.ArgumentException> 예외를 오류 검사 기능을 사용할 수 있는 <xref:System.Windows.Controls.ColumnDefinitionCollection.RemoveRange%2A> 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b20a-111">To prevent <xref:System.ArgumentOutOfRangeException> and <xref:System.ArgumentException> exceptions, you can use the error-checking functionality that the <xref:System.Windows.Controls.ColumnDefinitionCollection.RemoveRange%2A> method provides.</span></span>  
  
 [!code-csharp[ColumnDefinitionsGrid#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ColumnDefinitionsGrid/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ColumnDefinitionsGrid#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ColumnDefinitionsGrid/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="5b20a-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5b20a-112">See Also</span></span>  
 <xref:System.Windows.Controls.Grid>  
 <xref:System.Windows.Controls.ColumnDefinitionCollection>  
 <xref:System.Windows.Controls.RowDefinitionCollection>
