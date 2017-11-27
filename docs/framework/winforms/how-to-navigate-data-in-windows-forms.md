---
title: "방법: Windows Forms에서 데이터 탐색"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cursors [Windows Forms], data sources
- data sources [Windows Forms], Windows Forms
- Windows Forms, navigating
- CurrencyManager class [Windows Forms], navigating Windows Forms data
- data [Windows Forms], navigating
ms.assetid: 97360f7b-b181-4084-966a-4c62518f735b
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7c754bba18e93f63306701381f66af04b593c473
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-navigate-data-in-windows-forms"></a><span data-ttu-id="482d9-102">방법: Windows Forms에서 데이터 탐색</span><span class="sxs-lookup"><span data-stu-id="482d9-102">How to: Navigate Data in Windows Forms</span></span>
<span data-ttu-id="482d9-103">Windows 응용 프로그램에서 데이터 원본의 레코드를 탐색 하는 가장 쉬운 방법은에 바인딩하는 것을 <xref:System.Windows.Forms.BindingSource> 구성 요소는 데이터 소스를 바인딩한 다음 컨트롤에는 <xref:System.Windows.Forms.BindingSource>합니다.</span><span class="sxs-lookup"><span data-stu-id="482d9-103">In a Windows application, the easiest way to navigate through records in a data source is to bind a <xref:System.Windows.Forms.BindingSource> component to the data source and then bind controls to the <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="482d9-104">다음 기본 제공 탐색 메서드를 사용할 수 있습니다는 <xref:System.Windows.Forms.BindingSource> 이러한는 <xref:System.Windows.Forms.BindingSource.MoveNext%2A>, <xref:System.Windows.Forms.BindingSource.MoveLast%2A>, <xref:System.Windows.Forms.BindingSource.MovePrevious%2A> 및 <xref:System.Windows.Forms.BindingSource.MoveFirst%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="482d9-104">You can then use the built-in navigation method on the <xref:System.Windows.Forms.BindingSource> such a <xref:System.Windows.Forms.BindingSource.MoveNext%2A>, <xref:System.Windows.Forms.BindingSource.MoveLast%2A>, <xref:System.Windows.Forms.BindingSource.MovePrevious%2A> and <xref:System.Windows.Forms.BindingSource.MoveFirst%2A>.</span></span> <span data-ttu-id="482d9-105">이러한 메서드를 사용 하는 조정는 <xref:System.Windows.Forms.BindingSource.Position%2A> 및 <xref:System.Windows.Forms.BindingSource.Current%2A> 의 속성은 <xref:System.Windows.Forms.BindingSource> 적절 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="482d9-105">Using these methods will adjust the <xref:System.Windows.Forms.BindingSource.Position%2A> and <xref:System.Windows.Forms.BindingSource.Current%2A> properties of the <xref:System.Windows.Forms.BindingSource> appropriately.</span></span> <span data-ttu-id="482d9-106">항목을 찾을 수 있고 설정 하 여 현재 항목으로 설정 하면는 <xref:System.Windows.Forms.BindingSource.Position%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="482d9-106">You can also find an item and set it as the current item by setting the <xref:System.Windows.Forms.BindingSource.Position%2A> property.</span></span>  
  
### <a name="to-increment-the-position-in-a-data-source"></a><span data-ttu-id="482d9-107">데이터 소스에서 위치를 증가 시키기</span><span class="sxs-lookup"><span data-stu-id="482d9-107">To increment the position in a data source</span></span>  
  
1.  <span data-ttu-id="482d9-108">설정의 <xref:System.Windows.Forms.BindingSource.Position%2A> 의 속성은 <xref:System.Windows.Forms.BindingSource> 돌아가려면 레코드 위치에 바인딩된 데이터에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="482d9-108">Set the <xref:System.Windows.Forms.BindingSource.Position%2A> property of the <xref:System.Windows.Forms.BindingSource> for your bound data to the record position to go to.</span></span> <span data-ttu-id="482d9-109">다음 예제에서는 사용 하 여는 <xref:System.Windows.Forms.BindingSource.MoveNext%2A> 의 메서드는 <xref:System.Windows.Forms.BindingSource> 증가 하는 <xref:System.Windows.Forms.BindingSource.Position%2A> 속성 때는 `nextButton` 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="482d9-109">The following example illustrates using the <xref:System.Windows.Forms.BindingSource.MoveNext%2A> method of the <xref:System.Windows.Forms.BindingSource> to increment the <xref:System.Windows.Forms.BindingSource.Position%2A> property when the `nextButton` is clicked.</span></span> <span data-ttu-id="482d9-110"><xref:System.Windows.Forms.BindingSource> 과 연관 된 `Customers` 데이터 집합의 테이블 `Northwind`합니다.</span><span class="sxs-lookup"><span data-stu-id="482d9-110">The <xref:System.Windows.Forms.BindingSource> is associated with the `Customers` table of a dataset `Northwind`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="482d9-111">설정의 <xref:System.Windows.Forms.BindingSource.Position%2A> 첫 번째 또는 마지막 레코드를 벗어나는 값을 속성으로 하면 오류가 발생 하지 않습니다는 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 목록의 범위를 벗어난 값으로 위치를 설정할 수 있습니다를 허용 하지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="482d9-111">Setting the <xref:System.Windows.Forms.BindingSource.Position%2A> property to a value beyond the first or last record does not result in an error, as the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] will not allow you to set the position to a value outside the bounds of the list.</span></span> <span data-ttu-id="482d9-112">첫 번째 또는 마지막 레코드를 지난를 벗어났는지 여부를 알아야 응용 프로그램에서 중요 한 경우에 데이터 요소 개수를 초과 되어 있는지 여부를 테스트 논리를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="482d9-112">If it is important in your application to know whether you have gone past the first or last record, include logic to test whether you will exceed the data element count.</span></span>  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.NavigatingData#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#4)]  
  
### <a name="to-check-whether-you-have-passed-the-end-or-beginning"></a><span data-ttu-id="482d9-113">시작 또는 끝 전달한 있는지 여부를 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="482d9-113">To check whether you have passed the end or beginning</span></span>  
  
1.  <span data-ttu-id="482d9-114"><xref:System.Windows.Forms.BindingSource.PositionChanged> 이벤트에 대한 이벤트 처리기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="482d9-114">Create an event handler for the <xref:System.Windows.Forms.BindingSource.PositionChanged> event.</span></span> <span data-ttu-id="482d9-115">처리기에서 제안 된 위치 값이 실제 데이터 요소 개수를 초과 하는지 여부를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="482d9-115">In the handler, you can test whether the proposed position value has exceeded the actual data element count.</span></span>  
  
     <span data-ttu-id="482d9-116">다음 예제에서는 마지막 데이터 요소를에 도달 했는지 여부를 테스트 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="482d9-116">The following example illustrates how you can test whether you have reached the last data element.</span></span> <span data-ttu-id="482d9-117">예제에서는 마지막 요소에 있을 경우에 **다음** 폼의 단추에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="482d9-117">In the example, if you are at the last element, the **Next** button on the form is disabled.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="482d9-118">즉, 코드에서 탐색 중인 목록을 변경 하면 다시 사용 해야 유의 **다음** 단추를 사용자가 새 목록의 전체 길이 찾아볼 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="482d9-118">Be aware that, should you change the list you are navigating in code, you should re-enable the **Next** button, so that users may browse the entire length of the new list.</span></span> <span data-ttu-id="482d9-119">또한는 위의 <xref:System.Windows.Forms.BindingSource.PositionChanged> 특정에 대 한 이벤트 <xref:System.Windows.Forms.BindingSource> 해당 이벤트 처리 메서드에 연결 되도록 요구를 사용 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="482d9-119">Additionally, be aware that the above <xref:System.Windows.Forms.BindingSource.PositionChanged> event for the specific <xref:System.Windows.Forms.BindingSource> you are working with needs to be associated with its event-handling method.</span></span> <span data-ttu-id="482d9-120">다음은 처리에 대 한 방법의 예는 <xref:System.Windows.Forms.BindingSource.PositionChanged> 이벤트:</span><span class="sxs-lookup"><span data-stu-id="482d9-120">The following is an example of a method for handling the <xref:System.Windows.Forms.BindingSource.PositionChanged> event:</span></span>  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.NavigatingData#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#3)]  
  
### <a name="to-find-an-item-and-set-it-as-the-current-item"></a><span data-ttu-id="482d9-121">항목을 찾아 현재 항목으로 설정</span><span class="sxs-lookup"><span data-stu-id="482d9-121">To find an item and set it as the current item</span></span>  
  
1.  <span data-ttu-id="482d9-122">현재 항목으로 설정 하려는 레코드를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="482d9-122">Find the record you wish to set as the current item.</span></span> <span data-ttu-id="482d9-123">사용 하 여 수행할 수 있습니다는 <xref:System.Windows.Forms.BindingSource.Find%2A> 의 메서드는 <xref:System.Windows.Forms.BindingSource>데이터 원본 구현, <xref:System.ComponentModel.IBindingList>합니다.</span><span class="sxs-lookup"><span data-stu-id="482d9-123">You can do this using the <xref:System.Windows.Forms.BindingSource.Find%2A> method of the <xref:System.Windows.Forms.BindingSource>, if your data source implements <xref:System.ComponentModel.IBindingList>.</span></span> <span data-ttu-id="482d9-124">데이터의 몇 가지 예는 구현 하는 소스 <xref:System.ComponentModel.IBindingList> 는 <xref:System.ComponentModel.BindingList%601> 및 <xref:System.Data.DataView>합니다.</span><span class="sxs-lookup"><span data-stu-id="482d9-124">Some examples of data sources that implement <xref:System.ComponentModel.IBindingList> are <xref:System.ComponentModel.BindingList%601> and <xref:System.Data.DataView>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.NavigatingData#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="482d9-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="482d9-125">See Also</span></span>  
 [<span data-ttu-id="482d9-126">Windows Forms에서 지원하는 데이터 소스</span><span class="sxs-lookup"><span data-stu-id="482d9-126">Data Sources Supported by Windows Forms</span></span>](../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md)  
 [<span data-ttu-id="482d9-127">Windows Forms 데이터 바인딩의 변경 알림</span><span class="sxs-lookup"><span data-stu-id="482d9-127">Change Notification in Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 [<span data-ttu-id="482d9-128">데이터 바인딩 및 Windows Forms</span><span class="sxs-lookup"><span data-stu-id="482d9-128">Data Binding and Windows Forms</span></span>](../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 [<span data-ttu-id="482d9-129">Windows Forms 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="482d9-129">Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/windows-forms-data-binding.md)
