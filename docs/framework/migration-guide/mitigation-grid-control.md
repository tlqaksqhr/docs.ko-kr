---
title: "완화: Grid 컨트롤의 별 열 공간 할당"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retargeting changes
- .NET Framework 4.7 retargeting changes
- WPF retargeting changes
- Grid control retargeting changes
ms.assetid: 707c064d-85e9-4ea1-aefb-e42b60b88679
caps.latest.revision: 4
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 54391538ac0b2daf307cba2f7ceff1984d26b0ce
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-grid-control39s-space-allocation-to-star-columns"></a><span data-ttu-id="1bcfe-102">완화: Grid 컨트롤의 별 열 공간 할당</span><span class="sxs-lookup"><span data-stu-id="1bcfe-102">Mitigation: Grid Control&#39;s Space Allocation to Star-columns</span></span>

<span data-ttu-id="1bcfe-103">.NET Framework 4.7부터는 <xref:System.Windows.Controls.Grid> 컨트롤이 \* 열에 공간을 할당하는 데 사용하는 알고리즘 대신 WPF가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bcfe-103">Starting with applications that the .NET Framework 4.7, WPF replaces the algorithm that the <xref:System.Windows.Controls.Grid> control uses to allocate space to \*-columns.</span></span> 

## <a name="whats-changed"></a><span data-ttu-id="1bcfe-104">변경된 내용</span><span class="sxs-lookup"><span data-stu-id="1bcfe-104">What's changed</span></span>

<span data-ttu-id="1bcfe-105">새 알고리즘은 이전 알고리즘의 다음과 같은 여러 버그를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="1bcfe-105">The new algorithm fixes several bugs present in the old algorithm:</span></span>

1. <span data-ttu-id="1bcfe-106">열에 대한 전체 할당이 그리드 너비를 초과할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bcfe-106">Total allocation to columns can exceed the Grid's width.</span></span> <span data-ttu-id="1bcfe-107">비례 공유 크기가 최소 크기보다 작은 열에 공간을 할당하면 이 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bcfe-107">This can occur when allocating space to a column whose proportional share is less than its minimum size.</span></span> <span data-ttu-id="1bcfe-108">이 알고리즘은 최소 크기를 할당하여 다른 열에서 사용할 수 있는 공간 크기를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="1bcfe-108">The algorithm allocates the minimum size, which decreases the space available to other columns.</span></span> <span data-ttu-id="1bcfe-109">할당할 \* 열이 남아 있지 않은 경우 전체 할당이 너무 커집니다.</span><span class="sxs-lookup"><span data-stu-id="1bcfe-109">If there are no \*-columns left to allocate, the total allocation will be too large.</span></span>

1. <span data-ttu-id="1bcfe-110">전체 할당은 그리드 너비보다 작을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bcfe-110">Total allocation can fall short of the Grid's width.</span></span> <span data-ttu-id="1bcfe-111">이것은 여유 공간을 차지할 \* 열이 남아 있지 않을 때 비례 공유가 최대 크기보다 큰 열에 할당하는 경우에 발생하는 #1에 대한 이중 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="1bcfe-111">This is the dual problem to #1, arising when allocating to a column whose proportional share is greater than its maximum size, with no \*-columns left to take up the slack.</span></span>

1. <span data-ttu-id="1bcfe-112">두 \* 열은 가중치에 비례하지 않는 할당을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bcfe-112">Two \*-columns can receive allocations not proportional to their -weights.</span></span> <span data-ttu-id="1bcfe-113">이것은 * 열 A, B 및 C(해당 순서대로)에 할당할 때 B의 비례 공유가 최소(또는 최대) 제약 조건을 위반할 때 발생하는 #1/#2보다 좀 더 경미한 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="1bcfe-113">This is a milder version of #1/#2, arising when allocating to *-columns A, B, and C (in that order), where B's proportional share violates its min (or max) constraint.</span></span> <span data-ttu-id="1bcfe-114">이와 같이 열 C에서 사용할 수 있는 공간이 줄어들고 A보다 더 작은(또는 더 많은) 비례 할당을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bcfe-114">As above, this changes the space available to column C, who gets less (or more) proportional allocation than A did,</span></span>

1. <span data-ttu-id="1bcfe-115">매우 큰 가중치(>10^298)가 적용된 열은 마치 가중치가 10^298인 것처럼 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bcfe-115">Columns with extremely large weights (> 10^298) are all treated as if they had weight 10^298.</span></span> <span data-ttu-id="1bcfe-116">둘 열(및 가중치가 약간 더 작은 열) 간의 비례 차이는 유지되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1bcfe-116">Proportional differences between them (and between columns with slightly smaller weights) are not honored.</span></span>

1. <span data-ttu-id="1bcfe-117">무한 가중치를 갖는 열은 올바르게 처리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1bcfe-117">Columns with infinite weights are not handled correctly.</span></span> <span data-ttu-id="1bcfe-118">[실제로 가중치를 무한대로 설정할 수 있지만 인위적으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bcfe-118">[Actually you can't set a weight to Infinity, but this is an artificial restriction.</span></span> <span data-ttu-id="1bcfe-119">할당 코드가 처리하려고 했으나 잘못된 작업이 수행되었습니다.]</span><span class="sxs-lookup"><span data-stu-id="1bcfe-119">The allocation code was trying to handle it, but doing a bad job.]</span></span>

1. <span data-ttu-id="1bcfe-120">오버플로, 언더플로, 전체 자릿수 손실 및 비슷한 부동 소수점 문제를 방지할 때 나타나는 몇 가지 경미한 문제</span><span class="sxs-lookup"><span data-stu-id="1bcfe-120">Several minor problems while avoiding overflow, underflow, loss of precision and similar floating-point issues.</span></span>

1. <span data-ttu-id="1bcfe-121">레이아웃 조정이 충분히 높은 DPI에서 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1bcfe-121">Adjustments for layout rounding are incorrect at sufficiently high DPI.</span></span>

<span data-ttu-id="1bcfe-122">새 알고리즘은 다음 조건을 충족하는 결과를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="1bcfe-122">The new algorithm produces results that meet the following criteria:</span></span>

<span data-ttu-id="1bcfe-123">대답:</span><span class="sxs-lookup"><span data-stu-id="1bcfe-123">A.</span></span> <span data-ttu-id="1bcfe-124">* 열에 할당된 실제 너비는 최소 너비보다 작지도 않고 최대 너비보다 크지도 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1bcfe-124">The actual width assigned to a *-column is never less than its minimum width nor greater than its maximum width.</span></span>

<span data-ttu-id="1bcfe-125">B.</span><span class="sxs-lookup"><span data-stu-id="1bcfe-125">B.</span></span> <span data-ttu-id="1bcfe-126">최소 또는 최대 너비가 할당되지 않은 각 열에는 해당 가중치에 비례하는 너비가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bcfe-126">Each -column that is not assigned its minimum or maximum width is assigned a width proportional to its -weight.</span></span> <span data-ttu-id="1bcfe-127">정확히 말해서 두 열을 각각 너비 x 및 y로 선언하며 어떤 열에도 최소 또는 최대 너비가 수신되지 않으면 열에 할당된 실제 너비 v 및 w는 동일한 비율 v / w == x / y가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bcfe-127">To be precise, if two columns are declared with width x and y respectively, and if neither column receives its minimum or maximum width, the actual widths v and w assigned to the columns are in the same proportion: v / w == x / y.</span></span>

<span data-ttu-id="1bcfe-128">C.</span><span class="sxs-lookup"><span data-stu-id="1bcfe-128">C.</span></span> <span data-ttu-id="1bcfe-129">제한된 열(최소 또는 최대 너비가 할당된 고정, 자동 및 \* 열)에 할당된 후에는 "비례적" \* 열에 할당된 총 너비가 사용 가능한 공간과 같아집니다.</span><span class="sxs-lookup"><span data-stu-id="1bcfe-129">The total width allocated to "proportional" \*-columns is equal to the space available after allocating to the constrained columns (fixed, auto, and \*-columns that are allocated their min or max width).</span></span> <span data-ttu-id="1bcfe-130">예를 들어 최소 너비의 합계가 그리드의 사용 가능한 너비를 초과하면 이 크기는 0이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bcfe-130">This might be zero, for instance if the sum of the minimum widths exceeds the Grid's availbable width.</span></span>

<span data-ttu-id="1bcfe-131">D.</span><span class="sxs-lookup"><span data-stu-id="1bcfe-131">D.</span></span> <span data-ttu-id="1bcfe-132">이러한 모든 설명은 "이상적" 레이아웃과 관련된 것으로 해석될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bcfe-132">All these statements are to be interpreted with respect to the "ideal" layout.</span></span> <span data-ttu-id="1bcfe-133">레이아웃 조정이 적용되면 실제 너비는 픽세 크기만큼 이상적 너비와 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bcfe-133">When layout rounding is in effect, the actual widths can differ from the ideal widths by as much as one pixel.</span></span>

<span data-ttu-id="1bcfe-134">위에 설명된 경우에서 이전 알고리즘이 적용되었으나(A) 다른 조건을 충족하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="1bcfe-134">The old algorithm honored (A) but failed to honor the other criteria in the cases outlined above.</span></span>

<span data-ttu-id="1bcfe-135">이 항목에서 열 및 너비에 대한 모든 내용은 행 및 높이에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bcfe-135">Everything said about columns and widths in this topic applies as well to rows and heights.</span></span>

## <a name="impact"></a><span data-ttu-id="1bcfe-136">영향</span><span class="sxs-lookup"><span data-stu-id="1bcfe-136">Impact</span></span>

<span data-ttu-id="1bcfe-137">새 알고리즘은 다음과 같은 많은 경우에 \* 열에 할당되는 실제 너비를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="1bcfe-137">The new algorithm changes the actual width assigned to \*-columns in a number of cases:</span></span>

- <span data-ttu-id="1bcfe-138">하나 이상의 \* 열이 해당 열에 대한 비례 할당을 재정의하는 최소 또는 최대 너비를 가지는 경우</span><span class="sxs-lookup"><span data-stu-id="1bcfe-138">When one or more \*-columns also have a minimum or maximum width that overrides the proportional allocation for that column.</span></span> <span data-ttu-id="1bcfe-139">최소 너비는 명시적인 <xref:System.Windows.FrameworkElement.MinWidth%2A> 선언 또는 열 콘텐츠에서 가져온 암시적 최소값에서 파생될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bcfe-139">(The minimum width can derive from an explicit <xref:System.Windows.FrameworkElement.MinWidth%2A> declaration, or from an implicit minimum obtained from the column's content.</span></span> <span data-ttu-id="1bcfe-140">최대 너비는 <xref:System.Windows.FrameworkElement.MaxWidth%2A> 선언에서 명시적으로 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bcfe-140">The maximum width can only be defined explicitly, from a <xref:System.Windows.FrameworkElement.MaxWidth%2A> declaration.)</span></span>

- <span data-ttu-id="1bcfe-141">하나 이상의 \* 열 선언이 10^298보다 큰 훨씬 큰 \* 가중치를 선언하는 경우</span><span class="sxs-lookup"><span data-stu-id="1bcfe-141">When one or more \*-columns declare an extremely large \*-weight, greater than 10^298.</span></span>

- <span data-ttu-id="1bcfe-142">\* 가중치가 부동 소수점 불안정성(오버플로, 언더플로, 전체 자릿수 손실)을 야기할만큼 다른 경우</span><span class="sxs-lookup"><span data-stu-id="1bcfe-142">When the \*-weights are sufficiently different to encounter floating-point instability (overflow, underflow, loss of precision).</span></span>

- <span data-ttu-id="1bcfe-143">레이아웃 조정이 사용되도록 설정되고 결과 디스플레이 DPI가 충분히 높은 경우</span><span class="sxs-lookup"><span data-stu-id="1bcfe-143">When layout rounding is enabled, and the effective display DPI is sufficiently high.</span></span>

<span data-ttu-id="1bcfe-144">처음 두 경우에서 새 알고리즘에 의해 생성되는 너비는 이전 알고리즘에 의해 생성된 너비와 크게 다를 수 있습니다. 마지막 경우에서는 그 차이가 최대 하나 또는 두 개의 픽셀 정도입니다.</span><span class="sxs-lookup"><span data-stu-id="1bcfe-144">In the first two cases, the widths produced by the new algorithm can be significantly different from those produced by the old algorithm; in the last case, the difference will be at most one or two pixels.</span></span>

## <a name="mitigation"></a><span data-ttu-id="1bcfe-145">완화</span><span class="sxs-lookup"><span data-stu-id="1bcfe-145">Mitigation</span></span>

<span data-ttu-id="1bcfe-146">기본적으로 .NET Framework 4.6.2 또는 이전 버전을 대상으로 하는 앱은 이전 알고리즘을 사용하지만 .NET Framework 4.7 이상 버전을 대상으로 하는 앱은 새 알고리즘을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1bcfe-146">By default, apps that target versions of the .NET Framework starting with the .NET Framework 4.7 will use the new algorithm, while apps that target the .NET Framework 4.6.2 or earlier versions will use the old algorithm.</span></span>

<span data-ttu-id="1bcfe-147">기본값을 재정의하려면 다음 구성 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1bcfe-147">To override the default, use the following configuration setting:</span></span>

```xml
<runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=true" /> 
</runtime>
```

<span data-ttu-id="1bcfe-148">'True' 값은 이전 알고리즘을 선택하고 'false'는 새 알고리즘을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1bcfe-148">The value 'true' selects the old algorithm, and 'false' selects the new algorithm.</span></span>

## <a name="see-also"></a><span data-ttu-id="1bcfe-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1bcfe-149">See also</span></span>
[<span data-ttu-id="1bcfe-150">.NET Framework 4.7.1의 대상 다시 지정 변경 내용</span><span class="sxs-lookup"><span data-stu-id="1bcfe-150">Retargeting Changes in the .NET Framework 4.7</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md)

