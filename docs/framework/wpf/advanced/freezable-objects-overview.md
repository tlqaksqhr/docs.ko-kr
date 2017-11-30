---
title: "Freezable 개체 개요"
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
- Freezable objects [WPF], description
- unfreezing Freezable objects [WPF]
- classes [WPF], Freezable
ms.assetid: 89c71692-4f43-4057-b611-67c6a8a863a2
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 49778dc9551652ee4a4d36426b4b396652b9dcd2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="freezable-objects-overview"></a><span data-ttu-id="d0701-102">Freezable 개체 개요</span><span class="sxs-lookup"><span data-stu-id="d0701-102">Freezable Objects Overview</span></span>
<span data-ttu-id="d0701-103">이 항목에서는 효과적으로 사용 하 고 만드는 방법을 설명 <xref:System.Windows.Freezable> 응용 프로그램의 성능을 향상 시킬 수 있는 특별 한 기능을 제공 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-103">This topic describes how to effectively use and create <xref:System.Windows.Freezable> objects, which provide special features that can help improve application performance.</span></span> <span data-ttu-id="d0701-104">Freezable 개체의 예로 브러시, 펜, 변환, 기 하 도형 및 애니메이션을 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-104">Examples of freezable objects include brushes, pens, transformations, geometries, and animations.</span></span>  
  
<a name="whatisafreezable"></a>   
## <a name="what-is-a-freezable"></a><span data-ttu-id="d0701-105">Freezable 이란?</span><span class="sxs-lookup"><span data-stu-id="d0701-105">What Is a Freezable?</span></span>  
 <span data-ttu-id="d0701-106">A <xref:System.Windows.Freezable> 는 특수 한 유형의 두 가지 상태를 가진 개체를: 고정 해제 하 고 고정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-106">A <xref:System.Windows.Freezable> is a special type of object that has two states: unfrozen and frozen.</span></span> <span data-ttu-id="d0701-107">고정 되지 않은 한 <xref:System.Windows.Freezable> 다른 개체 처럼 동작 하 게 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-107">When unfrozen, a <xref:System.Windows.Freezable> appears to behave like any other object.</span></span> <span data-ttu-id="d0701-108">고정 경우는 <xref:System.Windows.Freezable> 더 이상 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-108">When frozen, a <xref:System.Windows.Freezable> can no longer be modified.</span></span>  
  
 <span data-ttu-id="d0701-109">A <xref:System.Windows.Freezable> 제공는 <xref:System.Windows.Freezable.Changed> 관찰자는 개체에 대 한 수정에 알리는 이벤트를 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-109">A <xref:System.Windows.Freezable> provides a <xref:System.Windows.Freezable.Changed> event to notify observers of any modifications to the object.</span></span> <span data-ttu-id="d0701-110">고정 된 <xref:System.Windows.Freezable> 하기 때문에 더 이상 변경 알림을에 리소스를 소비 성능을 향상 시킬 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-110">Freezing a <xref:System.Windows.Freezable> can improve its performance, because it no longer needs to spend resources on change notifications.</span></span> <span data-ttu-id="d0701-111">고정 된 <xref:System.Windows.Freezable> 고정 되지 않은 동안 스레드 간에 공유할 수도 <xref:System.Windows.Freezable> 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-111">A frozen <xref:System.Windows.Freezable> can also be shared across threads, while an unfrozen <xref:System.Windows.Freezable> cannot.</span></span>  
  
 <span data-ttu-id="d0701-112">하지만 <xref:System.Windows.Freezable> 클래스는 다양 한 용도로 가장 <xref:System.Windows.Freezable> 개체 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 그래픽 하위 시스템과 관련 된 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-112">Although the <xref:System.Windows.Freezable> class has many applications, most <xref:System.Windows.Freezable> objects in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] are related to the graphics sub-system.</span></span>  
  
 <span data-ttu-id="d0701-113"><xref:System.Windows.Freezable> 클래스 쉽게 특정 그래픽 시스템 개체를 사용 하 고 응용 프로그램의 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-113">The <xref:System.Windows.Freezable> class makes it easier to use certain graphics system objects and can help improve application performance.</span></span> <span data-ttu-id="d0701-114">상속 하는 형식의 예 <xref:System.Windows.Freezable> 포함는 <xref:System.Windows.Media.Brush>, <xref:System.Windows.Media.Transform>, 및 <xref:System.Windows.Media.Geometry> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-114">Examples of types that inherit from <xref:System.Windows.Freezable> include the <xref:System.Windows.Media.Brush>, <xref:System.Windows.Media.Transform>, and <xref:System.Windows.Media.Geometry> classes.</span></span> <span data-ttu-id="d0701-115">관리 되지 않는 리소스를 포함 하기 때문에 시스템의 수정 사항 이러한 개체를 모니터링 하 고 원래 개체에 변경 될 때 해당 관리 되지 않는 리소스를 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-115">Because they contain unmanaged resources, the system must monitor these objects for modifications, and then update their corresponding unmanaged resources when there is a change to the original object.</span></span> <span data-ttu-id="d0701-116">그래픽 시스템 개체를 실제로 수정 하지 않는 경우에 시스템을 계속 사용 해야 일부 리소스 모니터링 개체를 변경 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="d0701-116">Even if you don't actually modify a graphics system object, the system must still spend some of its resources monitoring the object, in case you do change it.</span></span>  
  
 <span data-ttu-id="d0701-117">예를 들어 다음과 같이 가정는 <xref:System.Windows.Media.SolidColorBrush> 브러시 및 단추의 배경을 칠하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-117">For example, suppose you create a <xref:System.Windows.Media.SolidColorBrush> brush and use it to paint the background of a button.</span></span>  
  
 [!code-csharp[freezablesample_procedural#FrozenExamplePart1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart1)]
 [!code-vb[freezablesample_procedural#FrozenExamplePart1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart1)]  
  
 <span data-ttu-id="d0701-118">단추를 렌더링할 때는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 그래픽 하위 시스템 그룹 단추의 모양을 형성 하는 픽셀을 그립니다 사용자가 제공한 정보를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-118">When the button is rendered, the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] graphics sub-system uses the information you provided to paint a group of pixels to create the appearance of a button.</span></span> <span data-ttu-id="d0701-119">단색 브러시를 사용 하는 단추를 그리는 방법을 설명 하기 위해 있지만 단색 브러시 실제로 그리기를 수행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-119">Although you used a solid color brush to describe how the button should be painted, your solid color brush doesn't actually do the painting.</span></span> <span data-ttu-id="d0701-120">단추와 브러시를 신속 하 고 하위 수준 개체를 생성 하는 그래픽 시스템 아니며 개체는 실제로 화면에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-120">The graphics system generates fast, low-level objects for the button and the brush, and it is those objects that actually appear on the screen.</span></span>  
  
 <span data-ttu-id="d0701-121">브러시를 수정 하는 경우, 이러한 하위 수준 개체를 다시 생성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-121">If you were to modify the brush, those low-level objects would have to be regenerated.</span></span> <span data-ttu-id="d0701-122">Freezable 클래스는 해당 생성 된, 하위 수준 개체를 찾을 수 고를 변경할 때이 정보도 업데이트 권한을 브러시를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-122">The freezable class is what gives a brush the ability to find its corresponding generated, low-level objects and to update them when it changes.</span></span> <span data-ttu-id="d0701-123">이 기능을 사용 하는 경우 브러시 라고 없습니다 "고정" 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-123">When this ability is enabled, the brush is said to be "unfrozen."</span></span>  
  
 <span data-ttu-id="d0701-124">Freezable의 <xref:System.Windows.Freezable.Freeze%2A> 메서드를 사용 하면 이러한 자동 업데이트 기능을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-124">A freezable's <xref:System.Windows.Freezable.Freeze%2A> method enables you to disable this self-updating ability.</span></span> <span data-ttu-id="d0701-125">"고정" 또는 수정할 수 없게 되는 브러시를 조정 하려면이 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-125">You can use this method to make the brush become "frozen," or unmodifiable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d0701-126">모든 Freezable 개체를 고정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-126">Not every Freezable object can be frozen.</span></span> <span data-ttu-id="d0701-127">Throw 되지 않도록 하려면는 <xref:System.InvalidOperationException>, Freezable 개체의 값을 확인 <xref:System.Windows.Freezable.CanFreeze%2A> 고정 하기 전에 고정 가능 여부를 결정 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-127">To avoid throwing an <xref:System.InvalidOperationException>, check the value of the Freezable object's <xref:System.Windows.Freezable.CanFreeze%2A> property to determine whether it can be frozen before attempting to freeze it.</span></span>  
  
 [!code-csharp[freezablesample_procedural#FrozenExamplePart2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart2)]
 [!code-vb[freezablesample_procedural#FrozenExamplePart2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart2)]  
  
 <span data-ttu-id="d0701-128">Freezable 수정 해야 하는 더 이상, 고정 성능 이점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-128">When you no longer need to modify a freezable, freezing it provides performance benefits.</span></span> <span data-ttu-id="d0701-129">이 예에서 브러시를 고정 하는 경우, 그래픽 시스템 변경에 대 한 모니터링은 더 이상 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-129">If you were to freeze the brush in this example, the graphics system would no longer need to monitor it for changes.</span></span> <span data-ttu-id="d0701-130">그래픽 시스템 브러시 변경 되지 않는 것을 알고 있으므로 다른 최적화를 축소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-130">The graphics system can also make other optimizations, because it knows the brush won't change.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d0701-131">편의 위해 명시적으로 고정 하지 않는 한 freezable 개체 고정 되지 않은 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-131">For convenience, freezable objects remain unfrozen unless you explicitly freeze them.</span></span>  
  
<a name="frozenfreezables"></a>   
## <a name="using-freezables"></a><span data-ttu-id="d0701-132">Freezable을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="d0701-132">Using Freezables</span></span>  
 <span data-ttu-id="d0701-133">고정 되지 않은 사용 하 여 freezable 비슷합니다 다른 형식의 개체를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-133">Using an unfrozen freezable is like using any other type of object.</span></span> <span data-ttu-id="d0701-134">다음 예제에서는 색을는 <xref:System.Windows.Media.SolidColorBrush> 단추의 배경을 칠하는 데 사용 된 후 빨간색으로 노랑에서 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-134">In the following example, the color of a <xref:System.Windows.Media.SolidColorBrush> is changed from yellow to red after it's used to paint the background of a button.</span></span> <span data-ttu-id="d0701-135">그래픽 시스템으로 자동 변경 하 고 단추 노랑에서 빨강으로 다음에 화면 새로 고칠 때 내부적으로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-135">The graphics system works behind the scenes to automatically change the button from yellow to red the next time the screen is refreshed.</span></span>  
  
 [!code-csharp[freezablesample_procedural#UnFrozenExampleShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#unfrozenexampleshort)]
 [!code-vb[freezablesample_procedural#UnFrozenExampleShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#unfrozenexampleshort)]  
  
### <a name="freezing-a-freezable"></a><span data-ttu-id="d0701-136">Freezable 고정</span><span class="sxs-lookup"><span data-stu-id="d0701-136">Freezing a Freezable</span></span>  
 <span data-ttu-id="d0701-137">있도록는 <xref:System.Windows.Freezable> 호출 수정할 수 없는, 해당 <xref:System.Windows.Freezable.Freeze%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="d0701-137">To make a <xref:System.Windows.Freezable> unmodifiable, you call its <xref:System.Windows.Freezable.Freeze%2A> method.</span></span> <span data-ttu-id="d0701-138">Freezable 개체를 포함 하는 개체를 중지 하면 해당 개체도 고정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-138">When you freeze an object that contains freezable objects, those objects are frozen as well.</span></span> <span data-ttu-id="d0701-139">예를 들어, 고정 하면는 <xref:System.Windows.Media.PathGeometry>, 그림 및 포함 된 세그먼트 고정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-139">For example, if you freeze a <xref:System.Windows.Media.PathGeometry>, the figures and segments it contains would be frozen too.</span></span>  
  
 <span data-ttu-id="d0701-140">Freezable **없습니다** 다음 중 하나에 해당할 경우 고정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-140">A Freezable **can't** be frozen if any of the following are true:</span></span>  
  
-   <span data-ttu-id="d0701-141">애니메이션이 적용 또는 데이터 바인딩된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-141">It has animated or data bound properties.</span></span>  
  
-   <span data-ttu-id="d0701-142">동적 리소스에서 설정 하는 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-142">It has properties set by a dynamic resource.</span></span> <span data-ttu-id="d0701-143">(참조는 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md) 동적 리소스에 대 한 자세한 내용은.)</span><span class="sxs-lookup"><span data-stu-id="d0701-143">(See the [XAML Resources](../../../../docs/framework/wpf/advanced/xaml-resources.md) for more information about dynamic resources.)</span></span>  
  
-   <span data-ttu-id="d0701-144">포함 된 <xref:System.Windows.Freezable> 고정할 수 없는 하위 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-144">It contains <xref:System.Windows.Freezable> sub-objects that can't be frozen.</span></span>  
  
 <span data-ttu-id="d0701-145">이러한 조건은 false 및 수정 하지 않으려는 경우는 <xref:System.Windows.Freezable>, 앞에서 설명한 성능을 향상 시키는 것을 고정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-145">If these conditions are false, and you don't intend to modify the <xref:System.Windows.Freezable>, then you should freeze it to gain the performance benefits described earlier.</span></span>  
  
 <span data-ttu-id="d0701-146">Freezable의 호출한 후 <xref:System.Windows.Freezable.Freeze%2A> 메서드를 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-146">Once you call a freezable's <xref:System.Windows.Freezable.Freeze%2A> method, it can no longer be modified.</span></span> <span data-ttu-id="d0701-147">고정 된 수정 하려고 하면 개체는 <xref:System.InvalidOperationException> throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-147">Attempting to modify a frozen object causes an <xref:System.InvalidOperationException> to be thrown.</span></span> <span data-ttu-id="d0701-148">다음 코드는 고정 된 후 브러시를 수정 하려고 하기 때문에 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-148">The following code throws an exception, because we attempt to modify the brush after it's been frozen.</span></span>  
  
 [!code-csharp[freezablesample_procedural#ExceptionExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#exceptionexample)]
 [!code-vb[freezablesample_procedural#ExceptionExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#exceptionexample)]  
  
 <span data-ttu-id="d0701-149">이 예외가 throw를 방지 하려면 사용할 수 있습니다는 <xref:System.Windows.Freezable.IsFrozen%2A> 확인 하 여부는 <xref:System.Windows.Freezable> 고정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-149">To avoid throwing this exception, you can use the <xref:System.Windows.Freezable.IsFrozen%2A> method to determine whether a <xref:System.Windows.Freezable> is frozen.</span></span>  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 <span data-ttu-id="d0701-150">이전 코드 예제에서 사용 하 여 고정 된 개체의 수정 가능한 복사본 했습니다는 <xref:System.Windows.Freezable.Clone%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="d0701-150">In the preceding code example, a modifiable copy was made of a frozen object using the <xref:System.Windows.Freezable.Clone%2A> method.</span></span> <span data-ttu-id="d0701-151">다음 섹션에서 자세히 복제를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-151">The next section discusses cloning in more detail.</span></span>  
  
 <span data-ttu-id="d0701-152">**참고** 때문에 고정 된 freezable 없습니다 애니메이션 효과 줄, 애니메이션 시스템에서의 수정 가능한 복제본을 자동으로 만듭니다 고정 <xref:System.Windows.Freezable> 를 사용 하 여 애니메이션을 적용 하려고 할 때 개체는 <xref:System.Windows.Media.Animation.Storyboard>합니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-152">**Note** Because a frozen freezable cannot be animated, the animation system will automatically create modifiable clones of frozen <xref:System.Windows.Freezable> objects when you try to animate them with a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="d0701-153">성능 복제로 인 한 오버 헤드를 방지 하려면 애니메이션을 적용 하려는 경우 고정 해제 하는 개체를 둡니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-153">To eliminate the performance overhead caused by cloning, leave an object unfrozen if you intend to animate it.</span></span> <span data-ttu-id="d0701-154">스토리 보드가 있는 애니메이션을 적용 하는 방법에 대 한 자세한 내용은 참조는 [적기](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-154">For more information about animating with storyboards, see the [Storyboards Overview](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).</span></span>  
  
### <a name="freezing-from-markup"></a><span data-ttu-id="d0701-155">태그에서 고정</span><span class="sxs-lookup"><span data-stu-id="d0701-155">Freezing from Markup</span></span>  
 <span data-ttu-id="d0701-156">고정 하려면는 <xref:System.Windows.Freezable> 사용 하면 태그에 선언 된 개체는 `PresentationOptions:Freeze` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-156">To freeze a <xref:System.Windows.Freezable> object declared in markup, you use the `PresentationOptions:Freeze` attribute.</span></span> <span data-ttu-id="d0701-157">다음 예제에서는 <xref:System.Windows.Media.SolidColorBrush> 페이지 리소스로 선언 되 고 고정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-157">In the following example, a <xref:System.Windows.Media.SolidColorBrush> is declared as a page resource and frozen.</span></span> <span data-ttu-id="d0701-158">다음 단추의 배경색을 설정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-158">It is then used to set the background of a button.</span></span>  
  
 [!code-xaml[FreezableSample#FreezeFromMarkupWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FreezableSample/CS/FreezeFromMarkupExample.xaml#freezefrommarkupwholepage)]  
  
 <span data-ttu-id="d0701-159">사용 하는 `Freeze` 특성을 매핑해야 옵션 네임 스페이스: `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`합니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-159">To use the `Freeze` attribute, you must map to the presentation options namespace: `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`.</span></span> <span data-ttu-id="d0701-160">`PresentationOptions`이 네임 스페이스를 매핑하기 위한 권장된 접두사:</span><span class="sxs-lookup"><span data-stu-id="d0701-160">`PresentationOptions` is the recommended prefix for mapping this namespace:</span></span>  
  
```  
xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"   
```  
  
 <span data-ttu-id="d0701-161">일부 XAML 판독기에서이 특성을 인식 하기 때문에 것이 좋습니다를 사용 하는 [mc: Ignorable 특성](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) 표시 하는 `Presentation:Freeze` 특성을 무시할 수:</span><span class="sxs-lookup"><span data-stu-id="d0701-161">Because not all XAML readers recognize this attribute, it's recommended that you use the [mc:Ignorable Attribute](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) to mark the `Presentation:Freeze` attribute as ignorable:</span></span>  
  
```  
xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
mc:Ignorable="PresentationOptions"  
```  
  
 <span data-ttu-id="d0701-162">자세한 내용은 참조는 [mc: Ignorable 특성](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) 페이지.</span><span class="sxs-lookup"><span data-stu-id="d0701-162">For more information, see the [mc:Ignorable Attribute](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) page.</span></span>  
  
### <a name="unfreezing-a-freezable"></a><span data-ttu-id="d0701-163">"고정 해제" Freezable</span><span class="sxs-lookup"><span data-stu-id="d0701-163">"Unfreezing" a Freezable</span></span>  
 <span data-ttu-id="d0701-164">하지만 고정 하면는 <xref:System.Windows.Freezable> 없습니다 수정 하거나 고정 해제; 수 사용 하는 고정 되지 않은 복제본을 만들 수는 <xref:System.Windows.Freezable.Clone%2A> 또는 <xref:System.Windows.Freezable.CloneCurrentValue%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="d0701-164">Once frozen, a <xref:System.Windows.Freezable> can never be modified or unfrozen; however, you can create an unfrozen clone using the <xref:System.Windows.Freezable.Clone%2A> or <xref:System.Windows.Freezable.CloneCurrentValue%2A> method.</span></span>  
  
 <span data-ttu-id="d0701-165">다음 예제에서는 단추의 배경을 브러시로 설정 되 고 고정 되는 브러시입니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-165">In the following example, the button's background is set with a brush and that brush is then frozen.</span></span> <span data-ttu-id="d0701-166">고정 되지 않은 복사본을 사용 하 여 브러시는 <xref:System.Windows.Freezable.Clone%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="d0701-166">An unfrozen copy is made of the brush using the <xref:System.Windows.Freezable.Clone%2A> method.</span></span> <span data-ttu-id="d0701-167">복제를 수정 하 고 노란색 배경이 빨강으로 변경 하는 데 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-167">The clone is modified and used to change the button's background from yellow to red.</span></span>  
  
 [!code-csharp[freezablesample_procedural#CloneExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
> [!NOTE]
>  <span data-ttu-id="d0701-168">복제 방법을 사용 하 여 애니메이션에 새 복사 되지 않습니다 <xref:System.Windows.Freezable>합니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-168">Regardless of which clone method you use, animations are never copied to the new <xref:System.Windows.Freezable>.</span></span>  
  
 <span data-ttu-id="d0701-169"><xref:System.Windows.Freezable.Clone%2A> 및 <xref:System.Windows.Freezable.CloneCurrentValue%2A> 메서드는 freezable의 전체 복사본을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-169">The <xref:System.Windows.Freezable.Clone%2A> and <xref:System.Windows.Freezable.CloneCurrentValue%2A> methods produce deep copies of the freezable.</span></span> <span data-ttu-id="d0701-170">들어 있는 경우는 freezable 다른 고정 freezable 개체도 복제 되며 수정할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-170">If the freezable contains other frozen freezable objects, they are also cloned and made modifiable.</span></span> <span data-ttu-id="d0701-171">예를 들어, 고정 된 복제 하면 <xref:System.Windows.Media.PathGeometry> 수정 가능 하 포함 된 세그먼트와도 복사 되어 수정할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-171">For example, if you clone a frozen <xref:System.Windows.Media.PathGeometry> to make it modifiable, the figures and segments it contains are also copied and made modifiable.</span></span>  
  
<a name="createyourownfreezableclass"></a>   
## <a name="creating-your-own-freezable-class"></a><span data-ttu-id="d0701-172">사용자 고유의 Freezable 클래스 만들기</span><span class="sxs-lookup"><span data-stu-id="d0701-172">Creating Your Own Freezable Class</span></span>  
 <span data-ttu-id="d0701-173">파생 되는 클래스 <xref:System.Windows.Freezable> 다음과 같은 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-173">A class that derives from <xref:System.Windows.Freezable> gains the following features.</span></span>  
  
-   <span data-ttu-id="d0701-174">특수 상태: 읽기 전용 (고정) 및 쓰기 가능 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-174">Special states: a read-only (frozen) and a writable state.</span></span>  
  
-   <span data-ttu-id="d0701-175">스레드로부터의 안전성: 고정 된 <xref:System.Windows.Freezable> 스레드 간에 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-175">Thread safety: a frozen <xref:System.Windows.Freezable> can be shared across threads.</span></span>  
  
-   <span data-ttu-id="d0701-176">자세한 변경 알림: 다릅니다 <xref:System.Windows.DependencyObject>s, Freezable 개체 변경 알림을 제공 하위 속성 값을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-176">Detailed change notification: Unlike other <xref:System.Windows.DependencyObject>s, Freezable objects provide change notifications when sub-property values change.</span></span>  
  
-   <span data-ttu-id="d0701-177">손쉬운 복제: Freezable 클래스 이미 전체 복제를 생성 하는 여러 메서드를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-177">Easy cloning: the Freezable class has already implemented several methods that produce deep clones.</span></span>  
  
 <span data-ttu-id="d0701-178">A <xref:System.Windows.Freezable> 의 형식인 <xref:System.Windows.DependencyObject>, 종속성 속성 시스템을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-178">A <xref:System.Windows.Freezable> is a type of <xref:System.Windows.DependencyObject>, and therefore uses the dependency property system.</span></span> <span data-ttu-id="d0701-179">클래스 속성이 종속성 속성을 쓸 필요가 없습니다 있지만 종속성 속성을 사용 하 여 쓰기 때문에 해야 하는 코드의 양을 줄일 됩니다는 <xref:System.Windows.Freezable> 클래스 종속성 속성을 염두에서에 두고 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-179">Your class properties don't have to be dependency properties, but using dependency properties will reduce the amount of code you have to write, because the <xref:System.Windows.Freezable> class was designed with dependency properties in mind.</span></span> <span data-ttu-id="d0701-180">종속성 속성 시스템에 대 한 자세한 내용은 참조는 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-180">For more information about the dependency property system, see the [Dependency Properties Overview](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).</span></span>  
  
 <span data-ttu-id="d0701-181">모든 <xref:System.Windows.Freezable> 하위 클래스에서 재정의 해야 합니다는 <xref:System.Windows.Freezable.CreateInstanceCore%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="d0701-181">Every <xref:System.Windows.Freezable> subclass must override the <xref:System.Windows.Freezable.CreateInstanceCore%2A> method.</span></span> <span data-ttu-id="d0701-182">모든 데이터에 대 한 종속성 속성을 사용 하는 클래스를 하는 경우 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-182">If your class uses dependency properties for all its data, you're finished.</span></span>  
  
 <span data-ttu-id="d0701-183">비 종속성 속성 데이터 멤버를 포함 하는 클래스를 하는 경우 다음 방법 재정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-183">If your class contains non-dependency property data members, you must also override the following methods:</span></span>  
  
-   <xref:System.Windows.Freezable.CloneCore%2A>  
  
-   <xref:System.Windows.Freezable.CloneCurrentValueCore%2A>  
  
-   <xref:System.Windows.Freezable.GetAsFrozenCore%2A>  
  
-   <xref:System.Windows.Freezable.GetCurrentValueAsFrozenCore%2A>  
  
-   <xref:System.Windows.Freezable.FreezeCore%2A>  
  
 <span data-ttu-id="d0701-184">또한 액세스 하 고 쓰기는 종속성 속성이 아닌 데이터 멤버에 대 한 다음 규칙을 준수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-184">You must also observe the following rules for accessing and writing to data members that are not dependency properties:</span></span>  
  
-   <span data-ttu-id="d0701-185">시작 부분에서 [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] 비 종속성 속성 데이터 멤버를 읽는, 호출 된 <xref:System.Windows.Freezable.ReadPreamble%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="d0701-185">At the beginning of any [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] that reads non-dependency property data members, call the <xref:System.Windows.Freezable.ReadPreamble%2A> method.</span></span>  
  
-   <span data-ttu-id="d0701-186">비 종속성 속성 데이터 멤버를 작성 하는 모든 API의 시작 부분에서 호출 된 <xref:System.Windows.Freezable.WritePreamble%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="d0701-186">At the beginning of any API that writes non-dependency property data members, call the <xref:System.Windows.Freezable.WritePreamble%2A> method.</span></span> <span data-ttu-id="d0701-187">(호출한 후 <xref:System.Windows.Freezable.WritePreamble%2A> 에 [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)]은 추가 호출을 확인 하지 않아도 <xref:System.Windows.Freezable.ReadPreamble%2A> 비 종속성 속성 데이터 멤버를 읽은 경우.)</span><span class="sxs-lookup"><span data-stu-id="d0701-187">(Once you've called <xref:System.Windows.Freezable.WritePreamble%2A> in an [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)], you don't need to make an additional call to <xref:System.Windows.Freezable.ReadPreamble%2A> if you also read non-dependency property data members.)</span></span>  
  
-   <span data-ttu-id="d0701-188">호출 된 <xref:System.Windows.Freezable.WritePostscript%2A> 비 종속성 속성 데이터 멤버에 작성 하는 메서드를 종료 하기 전에 메서드.</span><span class="sxs-lookup"><span data-stu-id="d0701-188">Call the <xref:System.Windows.Freezable.WritePostscript%2A> method before exiting methods that write to non-dependency property data members.</span></span>  
  
 <span data-ttu-id="d0701-189">클래스 종속성 비 속성 데이터 멤버를 포함 하는 경우 <xref:System.Windows.DependencyObject> 도 호출 해야 개체는 <xref:System.Windows.Freezable.OnFreezablePropertyChanged%2A> 메서드 컨트롤는 멤버를 설정 하는 경우에 해당 값의에서 변경할 때마다 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-189">If your class contains non-dependency-property data members that are <xref:System.Windows.DependencyObject> objects, you must also call the <xref:System.Windows.Freezable.OnFreezablePropertyChanged%2A> method each time you change on of their values, even if you're setting the member to `null`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d0701-190">각각를 시작 하는 것이 중요 <xref:System.Windows.Freezable> 메서드를 기본 구현에 대 한 호출으로 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-190">It's very important that you begin each <xref:System.Windows.Freezable> method you override with a call to the base implementation.</span></span>  
  
 <span data-ttu-id="d0701-191">사용자 지정에 대 한 예제 <xref:System.Windows.Freezable> 클래스를 참조 하십시오.는 [사용자 지정 애니메이션 샘플](http://go.microsoft.com/fwlink/?LinkID=159981)합니다.</span><span class="sxs-lookup"><span data-stu-id="d0701-191">For an example of a custom <xref:System.Windows.Freezable> class, see the [Custom Animation Sample](http://go.microsoft.com/fwlink/?LinkID=159981).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0701-192">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d0701-192">See Also</span></span>  
 <xref:System.Windows.Freezable>  
 [<span data-ttu-id="d0701-193">사용자 지정 애니메이션 샘플</span><span class="sxs-lookup"><span data-stu-id="d0701-193">Custom Animation Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159981)  
 [<span data-ttu-id="d0701-194">종속성 속성 개요</span><span class="sxs-lookup"><span data-stu-id="d0701-194">Dependency Properties Overview</span></span>](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [<span data-ttu-id="d0701-195">사용자 지정 종속성 속성</span><span class="sxs-lookup"><span data-stu-id="d0701-195">Custom Dependency Properties</span></span>](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)
