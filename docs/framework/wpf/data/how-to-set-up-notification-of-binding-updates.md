---
title: '방법: 바인딩 업데이트 알림 설정'
ms.date: 03/30/2017
helpviewer_keywords:
- notifications [WPF], binding updates
- data binding [WPF], notification of binding updates
- binding [WPF], updates [WPF], notifications of
ms.assetid: 5673073e-dbe1-49da-980a-484a88f9595a
ms.openlocfilehash: 896ce103361590dceecccf8534fd330aabe18086
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33555844"
---
# <a name="how-to-set-up-notification-of-binding-updates"></a><span data-ttu-id="6b445-102">방법: 바인딩 업데이트 알림 설정</span><span class="sxs-lookup"><span data-stu-id="6b445-102">How to: Set Up Notification of Binding Updates</span></span>
<span data-ttu-id="6b445-103">이 예제에서는 바인딩의 바인딩 대상(대상) 또는 바인딩 소스(소스) 속성이 업데이트될 경우 알림을 받도록 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6b445-103">This example shows how to set up to be notified when the binding target (target) or the binding source (source) property of a binding has been updated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b445-104">예제</span><span class="sxs-lookup"><span data-stu-id="6b445-104">Example</span></span>  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="6b445-105">은 바인딩 소스 또는 대상이 업데이트될 때마다 데이터 업데이트 이벤트를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="6b445-105"> raises a data update event each time that the binding source or target has been updated.</span></span> <span data-ttu-id="6b445-106">내부적으로 이 이벤트는 바인딩된 데이터가 변경되었기 때문에 업데이트 작업을 수행해야 함을 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]에 알리는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b445-106">Internally, this event is used to inform the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] that it should update, because the bound data has changed.</span></span> <span data-ttu-id="6b445-107">작동 하도록 하는 이러한 이벤트에 대 한 한도 제대로 작동 하려면 단방향 또는 양방향 바인딩이, 할 경우 사용 하 여 데이터 클래스를 구현 하는 참고는 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="6b445-107">Note that for these events to work, and also for one-way or two-way binding to work properly, you need to implement your data class using the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="6b445-108">자세한 내용은 [속성 변경 알림 구현](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6b445-108">For more information, see [Implement Property Change Notification](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).</span></span>  
  
 <span data-ttu-id="6b445-109">설정의 <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A> 또는 <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A> 를 속성 (또는 둘 다) `true` 바인딩에 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b445-109">Set the <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A> or <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A> property (or both) to `true` in the binding.</span></span> <span data-ttu-id="6b445-110">이 이벤트를 수신하기 위해 제공하는 처리기는 변경 내용에 대한 알림을 받을 요소에 직접 연결하거나, 컨텍스트의 내용이 변경되었는지 여부를 알고 싶은 경우 전체 데이터 컨텍스트에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b445-110">The handler you provide to listen for this event must be attached directly to the element where you want to be informed of changes, or to the overall data context if you want to be aware that anything in the context has changed.</span></span>  
  
 <span data-ttu-id="6b445-111">다음 예제에서는 대상 속성이 업데이트될 경우 알림을 받도록 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6b445-111">Here is an example that shows how to set up for notification when a target property has been updated.</span></span>  
  
 [!code-xaml[DirectionalBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#2)]  
  
 <span data-ttu-id="6b445-112">그런 다음 EventHandler\<T> 대리자(이 예제에서는 *OnTargetUpdated*)를 기반으로 처리기를 할당하여 이벤트를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b445-112">You can then assign a handler based on the EventHandler\<T> delegate, *OnTargetUpdated* in this example, to handle the event:</span></span>  
  
 [!code-csharp[DirectionalBinding#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml.cs#3)]  
[!code-csharp[DirectionalBinding#EndEvent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml.cs#endevent)]  
  
 <span data-ttu-id="6b445-113">이벤트의 매개 변수를 사용하여 변경된 속성에 대한 정보(둘 이상의 요소에 같은 처리기가 연결된 경우 형식 또는 특정 요소)를 확인할 수 있습니다. 이는 단일 요소에 바인딩된 속성이 여러 개 있는 경우 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b445-113">Parameters of the event can be used to determine details about the property that changed (such as the type or the specific element if the same handler is attached to more than one element), which can be useful if there are multiple bound properties on a single element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b445-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6b445-114">See Also</span></span>  
 [<span data-ttu-id="6b445-115">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="6b445-115">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="6b445-116">방법 항목</span><span class="sxs-lookup"><span data-stu-id="6b445-116">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
