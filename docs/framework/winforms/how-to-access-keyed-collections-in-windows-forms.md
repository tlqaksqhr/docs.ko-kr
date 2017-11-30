---
title: "방법: Windows Forms에서 키 컬렉션 액세스"
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
- keyed collections [Windows Forms]
- collections [Windows Forms], accessing with keys
ms.assetid: b9b79b8b-d9bf-4f8c-b9d6-9578bc3219d3
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2bca9b56f37c815bfa9f1520467ae0ae864c14ac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-keyed-collections-in-windows-forms"></a><span data-ttu-id="ef3fc-102">방법: Windows Forms에서 키 컬렉션 액세스</span><span class="sxs-lookup"><span data-stu-id="ef3fc-102">How to: Access Keyed Collections in Windows Forms</span></span>
-   <span data-ttu-id="ef3fc-103">키로 개별 컬렉션 항목에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef3fc-103">You can access individual collection items by key.</span></span> <span data-ttu-id="ef3fc-104">이 기능은 Windows Forms 응용 프로그램에서 일반적으로 사용 되는 많은 컬렉션 클래스에 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ef3fc-104">This functionality has been added to many collection classes that are typically used by Windows Forms applications.</span></span> <span data-ttu-id="ef3fc-105">다음 목록에서는 액세스할 수 있는 키 컬렉션에 있는 컬렉션 클래스 중 일부를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ef3fc-105">The following list shows some of the collection classes that have accessible keyed collections:</span></span>  
  
-   <xref:System.Windows.Forms.ListView.ListViewItemCollection>  
  
-   <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection>  
  
-   <xref:System.Windows.Forms.Control.ControlCollection>  
  
-   <xref:System.Windows.Forms.TabControl.TabPageCollection>  
  
-   <xref:System.Windows.Forms.TreeNodeCollection>  
  
 <span data-ttu-id="ef3fc-106">컬렉션의 항목에 연결 된 키 일반적으로 항목의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ef3fc-106">The key associated with an item in a collection is typically the name of the item.</span></span> <span data-ttu-id="ef3fc-107">다음 절차는 일반적인 작업을 수행할 컬렉션 클래스를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ef3fc-107">The following procedures show you how to use collection classes to perform common tasks.</span></span>  
  
### <a name="to-find-and-give-focus-to-a-nested-control-in-a-control-collection"></a><span data-ttu-id="ef3fc-108">찾아 컨트롤 컬렉션에서 중첩 된 컨트롤에 포커스를 이동</span><span class="sxs-lookup"><span data-stu-id="ef3fc-108">To find and give focus to a nested control in a control collection</span></span>  
  
-   <span data-ttu-id="ef3fc-109">사용 하 여는 <xref:System.Windows.Forms.Control.ControlCollection.Find%2A> 및 <xref:System.Windows.Forms.Control.Focus%2A> 를 찾아 포커스를 컨트롤의 이름을 지정 하는 메서드.</span><span class="sxs-lookup"><span data-stu-id="ef3fc-109">Use the <xref:System.Windows.Forms.Control.ControlCollection.Find%2A> and <xref:System.Windows.Forms.Control.Focus%2A> methods to specify the name of the control to find and give focus to.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#1)]  
  
### <a name="to-access-an-image-in-an-image-collection"></a><span data-ttu-id="ef3fc-110">이미지는 이미지 컬렉션에 액세스 하려면</span><span class="sxs-lookup"><span data-stu-id="ef3fc-110">To access an image in an image collection</span></span>  
  
-   <span data-ttu-id="ef3fc-111">사용 하 여는 <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> 속성을 통해 액세스 하려는 이미지의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef3fc-111">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> property to specify the name of the image you want to access.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#2)]  
  
### <a name="to-set-a-tab-page-as-the-selected-tab"></a><span data-ttu-id="ef3fc-112">선택된 된 탭으로 탭 페이지를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="ef3fc-112">To set a tab page as the selected tab</span></span>  
  
-   <span data-ttu-id="ef3fc-113">사용 하 여는 <xref:System.Windows.Forms.TabControl.SelectedTab%2A> 속성과 함께 <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> 속성을 통해 선택된 된 탭으로 설정 하는 탭 페이지의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef3fc-113">Use the <xref:System.Windows.Forms.TabControl.SelectedTab%2A> property together with the <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> property to specify the name of the tab page to set as the selected tab.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="ef3fc-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ef3fc-114">See Also</span></span>  
 [<span data-ttu-id="ef3fc-115">Windows Forms 시작</span><span class="sxs-lookup"><span data-stu-id="ef3fc-115">Getting Started with Windows Forms</span></span>](../../../docs/framework/winforms/getting-started-with-windows-forms.md)  
 [<span data-ttu-id="ef3fc-116">방법: Windows Forms ImageList 구성 요소를 사용하여 이미지 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="ef3fc-116">How to: Add or Remove Images with the Windows Forms ImageList Component</span></span>](../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)
