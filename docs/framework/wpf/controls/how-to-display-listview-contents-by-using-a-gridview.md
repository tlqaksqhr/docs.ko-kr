---
title: '방법: GridView를 사용하여 ListView 콘텐츠 표시'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], displaying contents with GridView
- GridView [WPF], displaying ListView contents
ms.assetid: 5bc1e767-ab46-4f14-bd41-3d5d39e1d000
ms.openlocfilehash: 103a439b9cee959d0077e5a759364eb9b943905d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33554053"
---
# <a name="how-to-display-listview-contents-by-using-a-gridview"></a><span data-ttu-id="16481-102">방법: GridView를 사용하여 ListView 콘텐츠 표시</span><span class="sxs-lookup"><span data-stu-id="16481-102">How to: Display ListView Contents by Using a GridView</span></span>
<span data-ttu-id="16481-103">정의 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.GridView> 에 대 한 보기 모드는 <xref:System.Windows.Controls.ListView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="16481-103">This example shows how to define a <xref:System.Windows.Controls.GridView> view mode for a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16481-104">예제</span><span class="sxs-lookup"><span data-stu-id="16481-104">Example</span></span>  
 <span data-ttu-id="16481-105">보기 모드를 정의할 수 있습니다는 <xref:System.Windows.Controls.GridView> 지정 하 여 <xref:System.Windows.Controls.GridViewColumn> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="16481-105">You can define the view mode of a <xref:System.Windows.Controls.GridView> by specifying <xref:System.Windows.Controls.GridViewColumn> objects.</span></span> <span data-ttu-id="16481-106">다음 예제에서는 정의 하는 방법을 보여 줍니다. <xref:System.Windows.Controls.GridViewColumn> 에 대해 지정 된 데이터 콘텐츠를 바인딩하는 개체는 <xref:System.Windows.Controls.ListView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="16481-106">The following example shows how to define <xref:System.Windows.Controls.GridViewColumn> objects that bind to the data content that is specified for the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="16481-107">이 <xref:System.Windows.Controls.GridView> 3을 지정 하는 예제 <xref:System.Windows.Controls.GridViewColumn> 개체에 매핑되는 `FirstName`, `LastName`, 및 `EmployeeNumber` 의 필드는 `EmployeeInfoDataSource` 로 설정 되어 있는 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 의 <xref:System.Windows.Controls.ListView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="16481-107">This <xref:System.Windows.Controls.GridView> example specifies three <xref:System.Windows.Controls.GridViewColumn> objects that map to the `FirstName`, `LastName`, and `EmployeeNumber` fields of the `EmployeeInfoDataSource` that is set as the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> of the <xref:System.Windows.Controls.ListView> control.</span></span>  
  
 [!code-xaml[ListViewCode#ListViewEmployee](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 <span data-ttu-id="16481-108">다음 그림은이 예제에서는 표시 되는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="16481-108">The following illustration shows how this example appears.</span></span>  
  
 <span data-ttu-id="16481-109">![GridView 출력이 있는 ListView](../../../../docs/framework/wpf/controls/media/listviewgridview.JPG "ListViewGridView")</span><span class="sxs-lookup"><span data-stu-id="16481-109">![ListView with GridView output](../../../../docs/framework/wpf/controls/media/listviewgridview.JPG "ListViewGridView")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16481-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="16481-110">See Also</span></span>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [<span data-ttu-id="16481-111">ListView 개요</span><span class="sxs-lookup"><span data-stu-id="16481-111">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [<span data-ttu-id="16481-112">GridView 개요</span><span class="sxs-lookup"><span data-stu-id="16481-112">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)  
 [<span data-ttu-id="16481-113">방법 항목</span><span class="sxs-lookup"><span data-stu-id="16481-113">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)
