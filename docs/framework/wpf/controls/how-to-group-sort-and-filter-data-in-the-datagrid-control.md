---
title: "방법: DataGrid 컨트롤에서 데이터 그룹화, 정렬 및 필터링"
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
- DataGrid [WPF], sort
- DataGrid [WPF], group
- DataGrid [WPF], filter
ms.assetid: 03345e85-89e3-4aec-9ed0-3b80759df770
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b3c8afacfafbe14794bf17a4e9a4df7c175a3668
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-group-sort-and-filter-data-in-the-datagrid-control"></a><span data-ttu-id="5980f-102">방법: DataGrid 컨트롤에서 데이터 그룹화, 정렬 및 필터링</span><span class="sxs-lookup"><span data-stu-id="5980f-102">How to: Group, Sort, and Filter Data in the DataGrid Control</span></span>
<span data-ttu-id="5980f-103">데이터를 종종 유용는 <xref:System.Windows.Controls.DataGrid> 그룹화, 정렬 및 데이터를 필터링 하 여 다양 한 방식에서입니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-103">It is often useful to view data in a <xref:System.Windows.Controls.DataGrid> in different ways by grouping, sorting, and filtering the data.</span></span> <span data-ttu-id="5980f-104">그룹화, 정렬 및 데이터를 필터링 하는 <xref:System.Windows.Controls.DataGrid>에 바인딩할는 <xref:System.Windows.Data.CollectionView> 이러한 함수를 지 원하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-104">To group, sort, and filter the data in a <xref:System.Windows.Controls.DataGrid>, you bind it to a <xref:System.Windows.Data.CollectionView> that supports these functions.</span></span> <span data-ttu-id="5980f-105">데이터로 작업할 수 있습니다는 <xref:System.Windows.Data.CollectionView> 원본 데이터에 영향을 주지 않고 합니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-105">You can then work with the data in the <xref:System.Windows.Data.CollectionView> without affecting the underlying source data.</span></span> <span data-ttu-id="5980f-106">컬렉션 뷰에서의 변경에 반영 된 <xref:System.Windows.Controls.DataGrid> UI (사용자 인터페이스).</span><span class="sxs-lookup"><span data-stu-id="5980f-106">The changes in the collection view are reflected in the <xref:System.Windows.Controls.DataGrid> user interface (UI).</span></span>  
  
 <span data-ttu-id="5980f-107"><xref:System.Windows.Data.CollectionView> 그룹화 및 정렬 구현 하는 데이터 원본에 대 한 기능을 제공 하는 클래스는 <xref:System.Collections.IEnumerable> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-107">The <xref:System.Windows.Data.CollectionView> class provides grouping and sorting functionality for a data source that implements the <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="5980f-108"><xref:System.Windows.Data.CollectionViewSource> 클래스의 속성을 설정할 수 있습니다는 <xref:System.Windows.Data.CollectionView> XAML에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-108">The <xref:System.Windows.Data.CollectionViewSource> class enables you to set the properties of a <xref:System.Windows.Data.CollectionView> from XAML.</span></span>  
  
 <span data-ttu-id="5980f-109">이 예제에서는 컬렉션을 `Task` 에 바인딩된 개체는 <xref:System.Windows.Data.CollectionViewSource>합니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-109">In this example, a collection of `Task` objects is bound to a <xref:System.Windows.Data.CollectionViewSource>.</span></span> <span data-ttu-id="5980f-110"><xref:System.Windows.Data.CollectionViewSource> 로 사용 되는 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 에 대 한는 <xref:System.Windows.Controls.DataGrid>합니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-110">The <xref:System.Windows.Data.CollectionViewSource> is used as the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> for the <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="5980f-111">그룹화, 정렬 및 필터링에서 수행 되는 <xref:System.Windows.Data.CollectionViewSource> 에 표시 됩니다는 <xref:System.Windows.Controls.DataGrid> UI입니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-111">Grouping, sorting, and filtering are performed on the <xref:System.Windows.Data.CollectionViewSource> and are displayed in the <xref:System.Windows.Controls.DataGrid> UI.</span></span>  
  
 <span data-ttu-id="5980f-112">![DataGrid의 데이터 그룹화](../../../../docs/framework/wpf/controls/media/wpf-datagridgroups.png "WPF_DataGridGroups")</span><span class="sxs-lookup"><span data-stu-id="5980f-112">![Grouped data in a DataGrid](../../../../docs/framework/wpf/controls/media/wpf-datagridgroups.png "WPF_DataGridGroups")</span></span>  
<span data-ttu-id="5980f-113">DataGrid의 그룹화 된 데이터</span><span class="sxs-lookup"><span data-stu-id="5980f-113">Grouped Data in a DataGrid</span></span>  
  
## <a name="using-a-collectionviewsource-as-an-itemssource"></a><span data-ttu-id="5980f-114">CollectionViewSource는 ItemsSource로 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="5980f-114">Using a CollectionViewSource as an ItemsSource</span></span>  
 <span data-ttu-id="5980f-115">그룹, 정렬 및 데이터를 필터링 하는 <xref:System.Windows.Controls.DataGrid> 컨트롤을 바인딩하는 <xref:System.Windows.Controls.DataGrid> 에 <xref:System.Windows.Data.CollectionView> 이러한 함수를 지 원하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-115">To group, sort, and filter data in a <xref:System.Windows.Controls.DataGrid> control, you bind the <xref:System.Windows.Controls.DataGrid> to a <xref:System.Windows.Data.CollectionView> that supports these functions.</span></span> <span data-ttu-id="5980f-116">이 예제에서는 <xref:System.Windows.Controls.DataGrid> 바인딩되는 <xref:System.Windows.Data.CollectionViewSource> 에 대 한 이러한 함수를 제공 하는 <xref:System.Collections.Generic.List%601> 의 `Task` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-116">In this example, the <xref:System.Windows.Controls.DataGrid> is bound to a <xref:System.Windows.Data.CollectionViewSource> that provides these functions for a <xref:System.Collections.Generic.List%601> of `Task` objects.</span></span>  
  
#### <a name="to-bind-a-datagrid-to-a-collectionviewsource"></a><span data-ttu-id="5980f-117">DataGrid는 CollectionViewSource에 바인딩하려면</span><span class="sxs-lookup"><span data-stu-id="5980f-117">To bind a DataGrid to a CollectionViewSource</span></span>  
  
1.  <span data-ttu-id="5980f-118">구현 하는 데이터 컬렉션을 만들기는 <xref:System.Collections.IEnumerable> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-118">Create a data collection that implements the <xref:System.Collections.IEnumerable> interface.</span></span>  
  
     <span data-ttu-id="5980f-119">사용 하는 경우 <xref:System.Collections.Generic.List%601> 사용자 컬렉션을 만들려면에서 상속 되는 새 클래스를 만들어야 <xref:System.Collections.Generic.List%601> 의 인스턴스를 인스턴스화하는 대신 <xref:System.Collections.Generic.List%601>합니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-119">If you use <xref:System.Collections.Generic.List%601> to create your collection, you should create a new class that inherits from <xref:System.Collections.Generic.List%601> instead of instantiating an instance of <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="5980f-120">XAML의 컬렉션에 데이터를 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-120">This enables you to data bind to the collection in XAML.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5980f-121">컬렉션의 개체를 구현 해야 합니다는 <xref:System.ComponentModel.INotifyPropertyChanged> 변경 된 인터페이스와 <xref:System.ComponentModel.IEditableObject> 인터페이스에 대 한 순서 대로 <xref:System.Windows.Controls.DataGrid> 속성 변경 및 편집에 올바르게 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-121">The objects in the collection must implement the <xref:System.ComponentModel.INotifyPropertyChanged> changed interface and the <xref:System.ComponentModel.IEditableObject> interface in order for the <xref:System.Windows.Controls.DataGrid> to respond correctly to property changes and edits.</span></span> <span data-ttu-id="5980f-122">자세한 내용은 [속성 변경 알림 구현](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5980f-122">For more information, see [Implement Property Change Notification](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).</span></span>  
  
     [!code-csharp[DataGrid_GroupSortFilter#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#101)]
     [!code-vb[DataGrid_GroupSortFilter#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#101)]  
  
2.  <span data-ttu-id="5980f-123">Xaml에서는 컬렉션 클래스의 인스턴스를 만들고 설정 된 [X:key 지시문](../../../../docs/framework/xaml-services/x-key-directive.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-123">In XAML, create an instance of the collection class and set the [x:Key Directive](../../../../docs/framework/xaml-services/x-key-directive.md).</span></span>  
  
3.  <span data-ttu-id="5980f-124">XAML의 인스턴스를 만들고는 <xref:System.Windows.Data.CollectionViewSource> 클래스, 설정는 [X:key 지시문](../../../../docs/framework/xaml-services/x-key-directive.md),으로 컬렉션 클래스의 인스턴스를 설정 하 고는 <xref:System.Windows.Data.CollectionViewSource.Source%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-124">In XAML, create an instance of the <xref:System.Windows.Data.CollectionViewSource> class, set the [x:Key Directive](../../../../docs/framework/xaml-services/x-key-directive.md), and set the instance of your collection class as the <xref:System.Windows.Data.CollectionViewSource.Source%2A>.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#201](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml#201)]  
  
4.  <span data-ttu-id="5980f-125">인스턴스를 만들고는 <xref:System.Windows.Controls.DataGrid> 클래스는 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 속성을는 <xref:System.Windows.Data.CollectionViewSource>합니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-125">Create an instance of the <xref:System.Windows.Controls.DataGrid> class, and set the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property to the <xref:System.Windows.Data.CollectionViewSource>.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#002](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#002)]  
  
5.  <span data-ttu-id="5980f-126">에 액세스 하려면는 <xref:System.Windows.Data.CollectionViewSource> 사용자 코드에서 사용 하 여는 <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> 에 대 한 참조를 얻으려고 하는 메서드는 <xref:System.Windows.Data.CollectionViewSource>합니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-126">To access the <xref:System.Windows.Data.CollectionViewSource> from your code, use the <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> method to get a reference to the <xref:System.Windows.Data.CollectionViewSource>.</span></span>  
  
     [!code-csharp[DataGrid_GroupSortFilter#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#102)]
     [!code-vb[DataGrid_GroupSortFilter#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#102)]  
  
## <a name="grouping-items-in-a-datagrid"></a><span data-ttu-id="5980f-127">DataGrid의 항목을 그룹화</span><span class="sxs-lookup"><span data-stu-id="5980f-127">Grouping items in a DataGrid</span></span>  
 <span data-ttu-id="5980f-128">항목이 그룹화 되는 방법을 지정 하는 <xref:System.Windows.Controls.DataGrid>를 사용 하면는 <xref:System.Windows.Data.PropertyGroupDescription> 형식 소스 뷰에서 항목을 그룹화 합니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-128">To specify how items are grouped in a <xref:System.Windows.Controls.DataGrid>, you use the <xref:System.Windows.Data.PropertyGroupDescription> type to group the items in the source view.</span></span>  
  
#### <a name="to-group-items-in-a-datagrid-using-xaml"></a><span data-ttu-id="5980f-129">XAML을 사용 하 여 DataGrid의 항목을 그룹</span><span class="sxs-lookup"><span data-stu-id="5980f-129">To group items in a DataGrid using XAML</span></span>  
  
1.  <span data-ttu-id="5980f-130">만들기는 <xref:System.Windows.Data.PropertyGroupDescription> 그룹화 할 속성을 지정 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-130">Create a <xref:System.Windows.Data.PropertyGroupDescription> that specifies the property to group by.</span></span> <span data-ttu-id="5980f-131">XAML 또는 코드에서 속성을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-131">You can specify the property in XAML or in code.</span></span>  
  
    1.  <span data-ttu-id="5980f-132">XAML에서 설정 된 <xref:System.Windows.Data.PropertyGroupDescription.PropertyName%2A> 그룹화 할 속성의 이름으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-132">In XAML, set the <xref:System.Windows.Data.PropertyGroupDescription.PropertyName%2A> to the name of the property to group by.</span></span>  
  
    2.  <span data-ttu-id="5980f-133">코드에서 생성자로 그룹화 할 속성의 이름을 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-133">In code, pass the name of the property to group by to the constructor.</span></span>  
  
2.  <span data-ttu-id="5980f-134">추가 <xref:System.Windows.Data.PropertyGroupDescription> 에 <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A?displayProperty=nameWithType> 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-134">Add the <xref:System.Windows.Data.PropertyGroupDescription> to the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A?displayProperty=nameWithType> collection.</span></span>  
  
3.  <span data-ttu-id="5980f-135">추가 인스턴스 <xref:System.Windows.Data.PropertyGroupDescription> 에 <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> 더 많은 수준의 그룹화를 추가할 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-135">Add additional instances of <xref:System.Windows.Data.PropertyGroupDescription> to the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> collection to add more levels of grouping.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#012](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#012)]  
  
     [!code-csharp[DataGrid_GroupSortFilter#112](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#112)]
     [!code-vb[DataGrid_GroupSortFilter#112](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#112)]  
  
4.  <span data-ttu-id="5980f-136">그룹을 제거 하려면 제거의 <xref:System.Windows.Data.PropertyGroupDescription> 에서 <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-136">To remove a group, remove the <xref:System.Windows.Data.PropertyGroupDescription> from the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> collection.</span></span>  
  
5.  <span data-ttu-id="5980f-137">모든 그룹을 제거 하려면 호출는 <xref:System.Collections.ObjectModel.Collection%601.Clear%2A> 의 메서드는 <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-137">To remove all groups, call the <xref:System.Collections.ObjectModel.Collection%601.Clear%2A> method of the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> collection.</span></span>  
  
     [!code-csharp[DataGrid_GroupSortFilter#114](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#114)]
     [!code-vb[DataGrid_GroupSortFilter#114](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#114)]  
  
 <span data-ttu-id="5980f-138">항목이 그룹화 되는 경우는 <xref:System.Windows.Controls.DataGrid>를 정의할 수 있습니다는 <xref:System.Windows.Controls.GroupStyle> 각 그룹의 모양을 지정 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-138">When items are grouped in the <xref:System.Windows.Controls.DataGrid>, you can define a <xref:System.Windows.Controls.GroupStyle> that specifies the appearance of each group.</span></span> <span data-ttu-id="5980f-139">적용 된 <xref:System.Windows.Controls.GroupStyle> 추가 하 여는 <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> DataGrid의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-139">You apply the <xref:System.Windows.Controls.GroupStyle> by adding it to the <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> collection of the DataGrid.</span></span> <span data-ttu-id="5980f-140">여러 가지 수준의 그룹화를 설정한 경우에 각 그룹 수준으로 다양 한 스타일을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-140">If you have multiple levels of grouping, you can apply different styles to each group level.</span></span> <span data-ttu-id="5980f-141">스타일 정의 된 순서에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-141">Styles are applied in the order in which they are defined.</span></span> <span data-ttu-id="5980f-142">예를 들어 두 개의 스타일을 정의 하는 경우 첫 번째 최상위 행 그룹에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-142">For example, if you define two styles, the first will be applied to top level row groups.</span></span> <span data-ttu-id="5980f-143">두 번째 스타일 및 하 한 두 번째 수준에서 모든 행 그룹에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-143">The second style will be applied to all row groups at the second level and lower.</span></span> <span data-ttu-id="5980f-144"><xref:System.Windows.FrameworkElement.DataContext%2A> 의 <xref:System.Windows.Controls.GroupStyle> 는 <xref:System.Windows.Data.CollectionViewGroup> 그룹을 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-144">The <xref:System.Windows.FrameworkElement.DataContext%2A> of the <xref:System.Windows.Controls.GroupStyle> is the <xref:System.Windows.Data.CollectionViewGroup> that the group represents.</span></span>  
  
#### <a name="to-change-the-appearance-of-row-group-headers"></a><span data-ttu-id="5980f-145">행 그룹 머리글의 모양을 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="5980f-145">To change the appearance of row group headers</span></span>  
  
1.  <span data-ttu-id="5980f-146">만들기는 <xref:System.Windows.Controls.GroupStyle> 행 그룹의 모양을 정의 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-146">Create a <xref:System.Windows.Controls.GroupStyle> that defines the appearance of the row group.</span></span>  
  
2.  <span data-ttu-id="5980f-147">배치는 <xref:System.Windows.Controls.GroupStyle> 내에서 `<DataGrid.GroupStyle>` 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-147">Put the <xref:System.Windows.Controls.GroupStyle> inside the `<DataGrid.GroupStyle>` tags.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#003](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#003)]  
  
## <a name="sorting-items-in-a-datagrid"></a><span data-ttu-id="5980f-148">DataGrid의 항목 정렬</span><span class="sxs-lookup"><span data-stu-id="5980f-148">Sorting items in a DataGrid</span></span>  
 <span data-ttu-id="5980f-149">항목이 정렬 되는 방법을 지정 하는 <xref:System.Windows.Controls.DataGrid>를 사용 하면는 <xref:System.ComponentModel.SortDescription> 소스 뷰에서 항목을 정렬 하는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-149">To specify how items are sorted in a <xref:System.Windows.Controls.DataGrid>, you use the <xref:System.ComponentModel.SortDescription> type to sort the items in the source view.</span></span>  
  
#### <a name="to-sort-items-in-a-datagrid"></a><span data-ttu-id="5980f-150">DataGrid의 항목을 정렬 하려면</span><span class="sxs-lookup"><span data-stu-id="5980f-150">To sort items in a DataGrid</span></span>  
  
1.  <span data-ttu-id="5980f-151">만들기는 <xref:System.ComponentModel.SortDescription> 정렬 기준 속성을 지정 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-151">Create a <xref:System.ComponentModel.SortDescription> that specifies the property to sort by.</span></span> <span data-ttu-id="5980f-152">XAML 또는 코드에서 속성을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-152">You can specify the property in XAML or in code.</span></span>  
  
    1.  <span data-ttu-id="5980f-153">XAML에서 설정 된 <xref:System.ComponentModel.SortDescription.PropertyName%2A> 기준으로 정렬 하려면 속성의 이름으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-153">In XAML, set the <xref:System.ComponentModel.SortDescription.PropertyName%2A> to the name of the property to sort by.</span></span>  
  
    2.  <span data-ttu-id="5980f-154">코드에서는 정렬 기준 속성의 이름을 전달 하 고 <xref:System.ComponentModel.ListSortDirection> 생성자에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-154">In code, pass the name of the property to sort by and the <xref:System.ComponentModel.ListSortDirection> to the constructor.</span></span>  
  
2.  <span data-ttu-id="5980f-155">추가 <xref:System.ComponentModel.SortDescription> 에 <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A?displayProperty=nameWithType> 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-155">Add the <xref:System.ComponentModel.SortDescription> to the <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A?displayProperty=nameWithType> collection.</span></span>  
  
3.  <span data-ttu-id="5980f-156">추가 인스턴스 <xref:System.ComponentModel.SortDescription> 에 <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A> 컬렉션 추가 속성을 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-156">Add additional instances of <xref:System.ComponentModel.SortDescription> to the <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A> collection to sort by additional properties.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#011](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#011)]  
  
     [!code-csharp[DataGrid_GroupSortFilter#211](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml.cs#211)]
     [!code-vb[DataGrid_GroupSortFilter#211](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#211)]  
  
## <a name="filtering-items-in-a-datagrid"></a><span data-ttu-id="5980f-157">DataGrid의 항목 필터링</span><span class="sxs-lookup"><span data-stu-id="5980f-157">Filtering items in a DataGrid</span></span>  
 <span data-ttu-id="5980f-158">항목을 필터링 하는 <xref:System.Windows.Controls.DataGrid> 를 사용 하 여는 <xref:System.Windows.Data.CollectionViewSource>, 이벤트의 처리기에서 필터링 논리를 제공 하는 <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-158">To filter items in a <xref:System.Windows.Controls.DataGrid> using a <xref:System.Windows.Data.CollectionViewSource>, you provide the filtering logic in the handler for the <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> event.</span></span>  
  
#### <a name="to-filter-items-in-a-datagrid"></a><span data-ttu-id="5980f-159">DataGrid의 항목을 필터링 하려면</span><span class="sxs-lookup"><span data-stu-id="5980f-159">To filter items in a DataGrid</span></span>  
  
1.  <span data-ttu-id="5980f-160">에 대 한 처리기를 추가 <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-160">Add a handler for the <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> event.</span></span>  
  
2.  <span data-ttu-id="5980f-161">에 <xref:System.Windows.Data.CollectionViewSource.Filter> 이벤트 처리기 필터링 논리를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-161">In the <xref:System.Windows.Data.CollectionViewSource.Filter> event handler, define the filtering logic.</span></span>  
  
     <span data-ttu-id="5980f-162">필터는 뷰를 새로 고칠 때마다 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-162">The filter will be applied every time the view is refreshed.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#013](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#013)]  
  
     [!code-csharp[DataGrid_GroupSortFilter#113](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#113)]
     [!code-vb[DataGrid_GroupSortFilter#113](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#113)]  
  
 <span data-ttu-id="5980f-163">또는의 항목을 필터링 할 수 있습니다는 <xref:System.Windows.Controls.DataGrid> 필터링 논리를 설정 하는 메서드를 만들어서는 <xref:System.Windows.Data.CollectionView.Filter%2A?displayProperty=nameWithType> 속성을 필터를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-163">Alternatively, you can filter items in a <xref:System.Windows.Controls.DataGrid> by creating a method that provides the filtering logic and setting the <xref:System.Windows.Data.CollectionView.Filter%2A?displayProperty=nameWithType> property to apply the filter.</span></span> <span data-ttu-id="5980f-164">이 방법의 예를 보려면 [보기에서 필터 데이터](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-164">To see an example of this method, see [Filter Data in a View](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5980f-165">예제</span><span class="sxs-lookup"><span data-stu-id="5980f-165">Example</span></span>  
 <span data-ttu-id="5980f-166">다음 예제에서는 그룹화, 정렬 및 필터링 `Task` 의 데이터는 <xref:System.Windows.Data.CollectionViewSource> 정렬, 필터링 및 그룹화, 표시 및 `Task` 의 데이터는 <xref:System.Windows.Controls.DataGrid>합니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-166">The following example demonstrates grouping, sorting, and filtering `Task` data in a <xref:System.Windows.Data.CollectionViewSource> and displaying the grouped, sorted, and filtered `Task` data in a <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="5980f-167"><xref:System.Windows.Data.CollectionViewSource> 로 사용 되는 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 에 대 한는 <xref:System.Windows.Controls.DataGrid>합니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-167">The <xref:System.Windows.Data.CollectionViewSource> is used as the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> for the <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="5980f-168">그룹화, 정렬 및 필터링에서 수행 되는 <xref:System.Windows.Data.CollectionViewSource> 에 표시 됩니다는 <xref:System.Windows.Controls.DataGrid> UI입니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-168">Grouping, sorting, and filtering are performed on the <xref:System.Windows.Data.CollectionViewSource> and are displayed in the <xref:System.Windows.Controls.DataGrid> UI.</span></span>  
  
 <span data-ttu-id="5980f-169">이 예제를 테스트 하려면 DGGroupSortFilterExample 이름을 프로젝트 이름과 일치 하도록 조정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-169">To test this example, you will need to adjust the DGGroupSortFilterExample name to match your project name.</span></span> <span data-ttu-id="5980f-170">Visual Basic을 사용 하는 경우에 대 한 클래스 이름을 변경 해야 합니다 <xref:System.Windows.Window> 다음과 합니다.</span><span class="sxs-lookup"><span data-stu-id="5980f-170">If you are using Visual Basic, you will need to change the class name for <xref:System.Windows.Window> to the following.</span></span>  
  
 `<Window x:Class="MainWindow"`  
  
 [!code-xaml[DataGrid_GroupSortFilter#000](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#000)]  
  
 [!code-csharp[DataGrid_GroupSortFilter#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#100)]
 [!code-vb[DataGrid_GroupSortFilter#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#100)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5980f-171">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="5980f-171">Compiling the Code</span></span>  
  
-  
  
## <a name="robust-programming"></a><span data-ttu-id="5980f-172">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="5980f-172">Robust Programming</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="5980f-173">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="5980f-173">.NET Framework Security</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5980f-174">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5980f-174">See Also</span></span>  
 [<span data-ttu-id="5980f-175">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="5980f-175">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="5980f-176">ObservableCollection 만들기 및 바인딩</span><span class="sxs-lookup"><span data-stu-id="5980f-176">Create and Bind to an ObservableCollection</span></span>](../../../../docs/framework/wpf/data/how-to-create-and-bind-to-an-observablecollection.md)  
 [<span data-ttu-id="5980f-177">뷰에서 데이터 필터링</span><span class="sxs-lookup"><span data-stu-id="5980f-177">Filter Data in a View</span></span>](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)  
 [<span data-ttu-id="5980f-178">뷰의 데이터 정렬</span><span class="sxs-lookup"><span data-stu-id="5980f-178">Sort Data in a View</span></span>](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)  
 [<span data-ttu-id="5980f-179">XAML 데이터 정렬 및 그룹화</span><span class="sxs-lookup"><span data-stu-id="5980f-179">Sort and Group Data Using a View in XAML</span></span>](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)
