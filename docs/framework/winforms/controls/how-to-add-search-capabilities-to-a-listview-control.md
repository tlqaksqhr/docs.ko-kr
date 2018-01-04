---
title: "방법: ListView 컨트롤에 검색 기능 추가"
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
- cpp
helpviewer_keywords:
- lists [Windows Forms], enabling searching
- list views [Windows Forms], enabling searching
- ListView control [Windows Forms], adding search capabilities
- searching [Windows Forms], adding search capabilities to ListView control
ms.assetid: 557782d9-b705-4bab-b496-9938afddac82
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 111fc6e4945998c99e63560afab6104f4daf89e8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-search-capabilities-to-a-listview-control"></a><span data-ttu-id="99736-102">방법: ListView 컨트롤에 검색 기능 추가</span><span class="sxs-lookup"><span data-stu-id="99736-102">How to: Add Search Capabilities to a ListView Control</span></span>
<span data-ttu-id="99736-103">에 있는 항목의 큰 목록으로 작업 하는 경우에 종종는 <xref:System.Windows.Forms.ListView> 사용자에 게 검색 기능을 제공 하려는 컨트롤을 합니다.</span><span class="sxs-lookup"><span data-stu-id="99736-103">Oftentimes when working with a large list of items in a <xref:System.Windows.Forms.ListView> control, you want to offer search capabilities to the user.</span></span> <span data-ttu-id="99736-104"><xref:System.Windows.Forms.ListView> 제어는 두 가지 방법으로이 기능을 제공: 텍스트 일치 및 위치를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="99736-104">The <xref:System.Windows.Forms.ListView> control offers this capability in two different ways: text matching and location searching.</span></span>  
  
 <span data-ttu-id="99736-105"><xref:System.Windows.Forms.ListView.FindItemWithText%2A> 메서드를 사용 하면에서 텍스트 검색을 수행 하는 <xref:System.Windows.Forms.ListView> 검색 문자열 및 선택적 시작 및 끝 인덱스가 지정 된 목록 또는 자세히 보기에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="99736-105">The <xref:System.Windows.Forms.ListView.FindItemWithText%2A> method allows you to perform a text search on a <xref:System.Windows.Forms.ListView> in list or details view, given a search string and an optional starting and ending index.</span></span> <span data-ttu-id="99736-106">반면,는 <xref:System.Windows.Forms.ListView.FindNearestItem%2A> 메서드에서 항목을 찾을 수 있습니다는 <xref:System.Windows.Forms.ListView> 아이콘 또는 tile 보기에서 x 및 y 좌표와 검색 방향을 집합이 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="99736-106">In contrast, the <xref:System.Windows.Forms.ListView.FindNearestItem%2A> method allows you to find an item in a <xref:System.Windows.Forms.ListView> in icon or tile view, given a set of x- and y-coordinates and a direction to search.</span></span>  
  
### <a name="to-find-an-item-using-text"></a><span data-ttu-id="99736-107">텍스트를 사용 하는 항목을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="99736-107">To find an item using text</span></span>  
  
1.  <span data-ttu-id="99736-108">만들기는 <xref:System.Windows.Forms.ListView> 와 <xref:System.Windows.Forms.ListView.View%2A> 속성이로 설정 <xref:System.Windows.Forms.View.Details> 또는 <xref:System.Windows.Forms.View.List>, 다음 채웁니다는 <xref:System.Windows.Forms.ListView> 항목과 합니다.</span><span class="sxs-lookup"><span data-stu-id="99736-108">Create a <xref:System.Windows.Forms.ListView> with the <xref:System.Windows.Forms.ListView.View%2A> property set to <xref:System.Windows.Forms.View.Details> or <xref:System.Windows.Forms.View.List>, and then populate the <xref:System.Windows.Forms.ListView> with items.</span></span>  
  
2.  <span data-ttu-id="99736-109">호출의 <xref:System.Windows.Forms.ListView.FindItemWithText%2A> 메서드를 찾을 하려는 항목의 텍스트를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="99736-109">Call the <xref:System.Windows.Forms.ListView.FindItemWithText%2A> method, passing the text of the item you would like to find.</span></span>  
  
3.  <span data-ttu-id="99736-110">다음 코드 예제에는 기본을 만드는 방법을 보여 줍니다 <xref:System.Windows.Forms.ListView>고 항목을 채우고, 사용자가 입력 한 텍스트를 사용 하 여 목록의 항목을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="99736-110">The following code example demonstrates how to create a basic <xref:System.Windows.Forms.ListView>, populate it with items, and use text input from the user to find an item in the list.</span></span>  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#1)]  
  
### <a name="to-find-an-item-using-x--and-y-coordinates"></a><span data-ttu-id="99736-111">X 및 y 좌표를 사용 하는 항목을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="99736-111">To find an item using x- and y-coordinates</span></span>  
  
1.  <span data-ttu-id="99736-112">만들기는 <xref:System.Windows.Forms.ListView> 와 <xref:System.Windows.Forms.View> 속성이로 설정 <xref:System.Windows.Forms.View.SmallIcon> 또는 <xref:System.Windows.Forms.View.LargeIcon>, 다음 채웁니다는 <xref:System.Windows.Forms.ListView> 항목과 합니다.</span><span class="sxs-lookup"><span data-stu-id="99736-112">Create a <xref:System.Windows.Forms.ListView> with the <xref:System.Windows.Forms.View> property set to <xref:System.Windows.Forms.View.SmallIcon> or <xref:System.Windows.Forms.View.LargeIcon>, and then populate the <xref:System.Windows.Forms.ListView> with items.</span></span>  
  
2.  <span data-ttu-id="99736-113">호출 된 <xref:System.Windows.Forms.ListView.FindNearestItem%2A> 메서드를 원하는 x 및 y-좌표 및 방향을 검색 하 시겠습니까 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="99736-113">Call the <xref:System.Windows.Forms.ListView.FindNearestItem%2A> method, passing the desired x- and y-coordinates and the direction you would like to search.</span></span>  
  
3.  <span data-ttu-id="99736-114">다음 코드 예제에서는 기본 아이콘을 만드는 방법을 보여 줍니다. <xref:System.Windows.Forms.ListView>, 항목 및 캡처를 채웁니다는 <xref:System.Windows.Forms.Control.MouseDown> 이벤트 위쪽 방향에서 가장 가까운 항목을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="99736-114">The following code example demonstrates how to create a basic icon <xref:System.Windows.Forms.ListView>, populate it with items, and capture the <xref:System.Windows.Forms.Control.MouseDown> event to find the nearest item in the up direction.</span></span>  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#2)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#2)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="99736-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="99736-115">See Also</span></span>  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListView.FindItemWithText%2A>  
 <xref:System.Windows.Forms.ListView.FindNearestItem%2A>  
 [<span data-ttu-id="99736-116">ListView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="99736-116">ListView Control</span></span>](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [<span data-ttu-id="99736-117">ListView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="99736-117">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [<span data-ttu-id="99736-118">방법: Windows Forms ListView 컨트롤을 사용하여 항목 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="99736-118">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
