---
title: "완화: Grid 컨트롤의 별 열 공간 할당 | Microsoft Docs"
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
translationtype: Human Translation
ms.sourcegitcommit: 9460c8b6ca8db927af4064e3567eca34c1bf5c91
ms.openlocfilehash: c7acce9d41af7e72b04b89751a7b186c9581dfea
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-grid-control39s-space-allocation-to-star-columns"></a>완화: Grid 컨트롤의 별 열 공간 할당

.NET Framework 4.7부터 WPF는 <xref:System.Windows.Controls.Grid> 컨트롤이 \* 열에 공간을 할당하는 데 사용하는 알고리즘을 대신합니다. 

## <a name="whats-changed"></a>변경된 내용

새 알고리즘은 이전 알고리즘의 다음과 같은 여러 버그를 해결합니다.

1. 열에 대한 전체 할당이 그리드 너비를 초과할 수 있습니다. 비례 공유 크기가 최소 크기보다 작은 열에 공간을 할당하면 이 문제가 발생할 수 있습니다. 이 알고리즘은 최소 크기를 할당하여 다른 열에서 사용할 수 있는 공간 크기를 줄입니다. 할당할 \* 열이 남아 있지 않은 경우 전체 할당이 너무 커집니다.

1. 전체 할당은 그리드 너비보다 작을 수 있습니다. 이것은 여유 공간을 차지할 \* 열이 남아 있지 않을 때 비례 공유가 최대 크기보다 큰 열에 할당하는 경우에 발생하는 #1에 대한 이중 문제입니다.

1. 두 \* 열은 가중치에 비례하지 않는 할당을 받을 수 있습니다. 이것은 * 열 A, B 및 C(해당 순서대로)에 할당할 때 B의 비례 공유가 최소(또는 최대) 제약 조건을 위반할 때 발생하는 #1/#2보다 좀 더 경미한 문제입니다. 이와 같이 열 C에서 사용할 수 있는 공간이 줄어들고 A보다 더 작은(또는 더 많은) 비례 할당을 얻게 됩니다.

1. 매우 큰 가중치(>10^298)가 적용된 열은 마치 가중치가 10^298인 것처럼 처리됩니다. 둘 열(및 가중치가 약간 더 작은 열) 간의 비례 차이는 유지되지 않습니다.

1. 무한 가중치를 갖는 열은 올바르게 처리되지 않습니다. [실제로 가중치를 무한대로 설정할 수 있지만 인위적으로 제한됩니다. 할당 코드가 처리하려고 했으나 잘못된 작업이 수행되었습니다.]

1. 오버플로, 언더플로, 전체 자릿수 손실 및 비슷한 부동 소수점 문제를 방지할 때 나타나는 몇 가지 경미한 문제

1. 레이아웃 조정이 충분히 높은 DPI에서 올바르지 않습니다.

새 알고리즘은 다음 조건을 충족하는 결과를 생성합니다.

대답: * 열에 할당된 실제 너비는 최소 너비보다 작지도 않고 최대 너비보다 크지도 않습니다.

B. 최소 또는 최대 너비가 할당되지 않은 각 열에는 해당 가중치에 비례하는 너비가 할당됩니다. 정확히 말해서 두 열을 각각 너비 x 및 y로 선언하며 어떤 열에도 최소 또는 최대 너비가 수신되지 않으면 열에 할당된 실제 너비 v 및 w는 동일한 비율 v / w == x / y가 됩니다.

C. 제한된 열(최소 또는 최대 너비가 할당된 고정, 자동 및 \* 열)에 할당된 후에는 "비례적" \* 열에 할당된 총 너비가 사용 가능한 공간과 같아집니다. 예를 들어 최소 너비의 합계가 그리드의 사용 가능한 너비를 초과하면 이 크기는 0이 될 수 있습니다.

D. 이러한 모든 설명은 "이상적" 레이아웃과 관련된 것으로 해석될 수 있습니다. 레이아웃 조정이 적용되면 실제 너비는 픽세 크기만큼 이상적 너비와 달라질 수 있습니다.

위에 설명된 경우에서 이전 알고리즘이 적용되었으나(A) 다른 조건을 충족하지 못했습니다.

이 항목에서 열 및 너비에 대한 모든 내용은 행 및 높이에도 적용됩니다.

## <a name="impact"></a>영향

새 알고리즘은 다음과 같은 많은 경우에 \* 열에 할당되는 실제 너비를 변경합니다.

- 하나 이상의 \* 열이 해당 열에 대한 비례 할당을 재정의하는 최소 또는 최대 너비를 가지는 경우 (최소 너비는 명시적인 <xref:System.Windows.FrameworkElement.MinWidth%2A> 선언 또는 열 콘텐츠에서 가져온 암시적 최소값에서 파생될 수 있습니다. 최대 너비는 <xref:System.Windows.FrameworkElement.MaxWidth%2A> 선언에서 명시적으로 정의할 수만 있습니다.

- 하나 이상의 \* 열 선언이 10^298보다 큰 훨씬 큰 \* 가중치를 선언하는 경우

- \* 가중치가 부동 소수점 불안정성(오버플로, 언더플로, 전체 자릿수 손실)을 야기할만큼 다른 경우

- 레이아웃 조정이 사용되도록 설정되고 결과 디스플레이 DPI가 충분히 높은 경우

처음 두 경우에서 새 알고리즘에 의해 생성되는 너비는 이전 알고리즘에 의해 생성된 너비와 크게 다를 수 있습니다. 마지막 경우에서는 그 차이가 최대 하나 또는 두 개의 픽셀 정도입니다.

## <a name="mitigation"></a>완화

기본적으로 .NET Framework 4.6.2 또는 이전 버전을 대상으로 하는 앱은 이전 알고리즘을 사용하지만 .NET Framework 4.7 이상 버전을 대상으로 하는 앱은 새 알고리즘을 사용합니다.

기본값을 재정의하려면 다음 구성 설정을 사용합니다.

```xml
<runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=true" /> 
</runtime>
```

'True' 값은 이전 알고리즘을 선택하고 'false'는 새 알고리즘을 선택합니다.

## <a name="see-also"></a>참고 항목
[.NET Framework 4.7.1의 대상 다시 지정 변경 내용](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md)

