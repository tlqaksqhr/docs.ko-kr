---
title: '방법: ADO.NET 데이터 소스 바인딩'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], binding to ADO.NET data sources
- ADO.NET data sources [WPF], binding to
- binding [WPF], to ADO.NET data sources
ms.assetid: a70c6d7b-7b38-4fdf-b655-4804db7c8315
ms.openlocfilehash: c9e16b9fd100eb9aec7bee2f94307aa80371d5ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556863"
---
# <a name="how-to-bind-to-an-adonet-data-source"></a><span data-ttu-id="762c0-102">방법: ADO.NET 데이터 소스 바인딩</span><span class="sxs-lookup"><span data-stu-id="762c0-102">How to: Bind to an ADO.NET Data Source</span></span>
<span data-ttu-id="762c0-103">바인딩하는 방법을 보여 주는이 예제는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.ListBox> 컨트롤을 한 [!INCLUDE[TLA#tla_adonet](../../../../includes/tlasharptla-adonet-md.md)] `DataSet`합니다.</span><span class="sxs-lookup"><span data-stu-id="762c0-103">This example shows how to bind a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.ListBox> control to an [!INCLUDE[TLA#tla_adonet](../../../../includes/tlasharptla-adonet-md.md)] `DataSet`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="762c0-104">예제</span><span class="sxs-lookup"><span data-stu-id="762c0-104">Example</span></span>  
 <span data-ttu-id="762c0-105">이 예에서는 `OleDbConnection` 개체를 사용하여 연결 문자열에 지정된 `Access MDB` 파일인 데이터 소스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="762c0-105">In this example, an `OleDbConnection` object is used to connect to the data source which is an `Access MDB` file that is specified in the connection string.</span></span> <span data-ttu-id="762c0-106">연결이 설정되고 나면 `OleDbDataAdpater` 개체가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="762c0-106">After the connection is established, an `OleDbDataAdpater` object is created.</span></span> <span data-ttu-id="762c0-107">`OleDbDataAdpater` 개체는 select [!INCLUDE[TLA#tla_sql](../../../../includes/tlasharptla-sql-md.md)] 명령문을 실행하여 데이터베이스에서 레코드 집합을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="762c0-107">The `OleDbDataAdpater` object executes a select [!INCLUDE[TLA#tla_sql](../../../../includes/tlasharptla-sql-md.md)] statement to retrieve the recordset from the database.</span></span> <span data-ttu-id="762c0-108">[!INCLUDE[TLA2#tla_sql](../../../../includes/tla2sharptla-sql-md.md)] 명령의 결과는 `OleDbDataAdapter`의 `Fill` 메서드를 호출하여 `DataSet`의 `DataTable`에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="762c0-108">The results from the [!INCLUDE[TLA2#tla_sql](../../../../includes/tla2sharptla-sql-md.md)] command are stored in a `DataTable` of the `DataSet` by calling the `Fill` method of the `OleDbDataAdapter`.</span></span> <span data-ttu-id="762c0-109">이 예에서 `DataTable`은 `BookTable`로 이름이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="762c0-109">The `DataTable` in this example is named `BookTable`.</span></span> <span data-ttu-id="762c0-110">설정한 후는 <xref:System.Windows.FrameworkElement.DataContext%2A> 의 속성은 <xref:System.Windows.Controls.ListBox> 에 `DataSet` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="762c0-110">The example then sets the <xref:System.Windows.FrameworkElement.DataContext%2A> property of the <xref:System.Windows.Controls.ListBox> to the `DataSet` object.</span></span>  
  
 [!code-csharp[ADODataSet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 <span data-ttu-id="762c0-111">그런 다음 바인딩할 수는 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 의 속성은 <xref:System.Windows.Controls.ListBox> 를 `BookTable` 의 `DataSet`:</span><span class="sxs-lookup"><span data-stu-id="762c0-111">We can then bind the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to `BookTable` of the `DataSet`:</span></span>  
  
 [!code-xaml[ADODataSet#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="762c0-112">`BookItemTemplate` 이 <xref:System.Windows.DataTemplate> 데이터가 표시 되는 방식을 정의 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="762c0-112">`BookItemTemplate` is the <xref:System.Windows.DataTemplate> that defines how the data appears:</span></span>  
  
 [!code-xaml[ADODataSet#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#3)]  
  
 <span data-ttu-id="762c0-113">`IntColorConverter`는 `int`를 색상으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="762c0-113">The `IntColorConverter` converts an `int` to a color.</span></span> <span data-ttu-id="762c0-114">이 변환기를 사용 하 여는 <xref:System.Windows.Controls.TextBlock.Background%2A> 의 <xref:System.Windows.Controls.TextBlock> 녹색 표시 하는 경우의 값 `NumPages` 는 보다 작은 350 하 고 빨간색 그렇지 않으면입니다.</span><span class="sxs-lookup"><span data-stu-id="762c0-114">With the use of this converter, the <xref:System.Windows.Controls.TextBlock.Background%2A> color of the third <xref:System.Windows.Controls.TextBlock> appears green if the value of `NumPages` is less than 350 and red otherwise.</span></span> <span data-ttu-id="762c0-115">변환기의 구현은 여기에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="762c0-115">The implementation of the converter is not shown here.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="762c0-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="762c0-116">See Also</span></span>  
 <xref:System.Windows.Data.BindingListCollectionView>  
 [<span data-ttu-id="762c0-117">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="762c0-117">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="762c0-118">방법 항목</span><span class="sxs-lookup"><span data-stu-id="762c0-118">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
