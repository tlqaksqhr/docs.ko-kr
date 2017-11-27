---
title: "방법: GridViewRowPresenter를 사용하여 데이터 표시"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- displaying data with GridViewRowPresenter [WPF]
- GridViewRowPresenter [WPF]
ms.assetid: bdb785a5-a262-44d5-a517-ea14383e5f70
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ebe0a47d38a2cfda2a7d150b4a3886d9f63ee190
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-data-by-using-gridviewrowpresenter"></a><span data-ttu-id="940b8-102">방법: GridViewRowPresenter를 사용하여 데이터 표시</span><span class="sxs-lookup"><span data-stu-id="940b8-102">How to: Display Data by Using GridViewRowPresenter</span></span>
<span data-ttu-id="940b8-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.GridViewRowPresenter> 및 <xref:System.Windows.Controls.GridViewHeaderRowPresenter> 개체 열에 데이터를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="940b8-103">This example shows how to use the <xref:System.Windows.Controls.GridViewRowPresenter> and <xref:System.Windows.Controls.GridViewHeaderRowPresenter> objects to display data in columns.</span></span>  
  
## <a name="example"></a><span data-ttu-id="940b8-104">예제</span><span class="sxs-lookup"><span data-stu-id="940b8-104">Example</span></span>  
 <span data-ttu-id="940b8-105">다음 예제에서는 지정 하는 방법을 보여 줍니다.는 <xref:System.Windows.Controls.GridViewColumnCollection> 표시 하는 <xref:System.DateTime.DayOfWeek%2A> 및 <xref:System.DateTime.Year%2A> 의 <xref:System.DateTime> 개체를 사용 하 여 <xref:System.Windows.Controls.GridViewRowPresenter> 및 <xref:System.Windows.Controls.GridViewHeaderRowPresenter> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="940b8-105">The following example shows how to specify a <xref:System.Windows.Controls.GridViewColumnCollection> that displays the <xref:System.DateTime.DayOfWeek%2A> and <xref:System.DateTime.Year%2A> of a <xref:System.DateTime> object by using <xref:System.Windows.Controls.GridViewRowPresenter> and <xref:System.Windows.Controls.GridViewHeaderRowPresenter> objects.</span></span> <span data-ttu-id="940b8-106">이 예제에서는 또한 정의 <xref:System.Windows.Style> 에 대 한는 <xref:System.Windows.Controls.GridViewColumn.Header%2A> 의 <xref:System.Windows.Controls.GridViewColumn>합니다.</span><span class="sxs-lookup"><span data-stu-id="940b8-106">The example also defines a <xref:System.Windows.Style> for the <xref:System.Windows.Controls.GridViewColumn.Header%2A> of a <xref:System.Windows.Controls.GridViewColumn>.</span></span>  
  
 [!code-xaml[GridViewRowPresenterSample#GridViewRowPresenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewRowPresenterSample/CS/Window1.xaml#gridviewrowpresenter)]  
  
## <a name="see-also"></a><span data-ttu-id="940b8-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="940b8-107">See Also</span></span>  
 <xref:System.Windows.Controls.GridViewHeaderRowPresenter>  
 <xref:System.Windows.Controls.GridViewRowPresenter>  
 <xref:System.Windows.Controls.GridViewColumnCollection>  
 [<span data-ttu-id="940b8-108">GridView 개요</span><span class="sxs-lookup"><span data-stu-id="940b8-108">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)
