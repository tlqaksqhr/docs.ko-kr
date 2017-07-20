---
title: "완화: 가로 스크롤 및 가상화 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d5bafd9b-a3b3-4f92-8241-2aad254fb1a9
caps.latest.revision: 6
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 37c60fd8a3e3e4e44dc00e278f6edafcdd766c03
ms.contentlocale: ko-kr
ms.lasthandoff: 05/22/2017

---
# <a name="mitigation-horizontal-scrolling-and-virtualization"></a>완화: 가로 스크롤 및 가상화
이 변경 내용은 주 스크롤 방향의 직각 방향으로 자체 가상화를 수행하는 <xref:System.Windows.Controls.ItemsControl>에 적용됩니다. 이러한 가상화의 주요 예제는 <xref:System.Windows.Controls.DataGrid.EnableColumnVirtualization%2A>이 `true`로 설정된 <xref:System.Windows.Controls.DataGrid> 컨트롤에서 확인할 수 있습니다.  특정 가로 스크롤 작업의 결과는 보다 직관적이고 비교 가능한 세로 작업의 결과와 좀 더 유사한 결과를 생성하도록 변경되었습니다.  구체적인 작업으로는 가로 스크롤 막대를 마우스 오른쪽 단추로 클릭할 때 표시되는 메뉴의 이름을 사용하기 위한 **여기로 스크롤** 및 **오른쪽 가장자리**가 있습니다.  이 두 작업에서는 모두 후보 오프셋을 계산하고 <xref:System.Windows.Controls.Primitives.IScrollInfo.SetHorizontalOffset%2A?displayProperty=fullName>을 호출합니다.  새롭게 가상화가 취소된 콘텐츠에서는 <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth%2A?displayProperty=fullName>의 값이 변경되었으므로 새 오프셋으로 스크롤한 후에 "여기" 또는 "오른쪽 가장자리"의 정의가 변경되었을 수 있습니다.  
  
## <a name="description-of-the-change"></a>변경에 대한 설명  
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 이전에는 “여기" 또는 “오른쪽 가장자리"는 더 이상 아닐 수 있지만 스크롤 작업을 수행하면 후보 오프셋이 사용됩니다.  결과적으로 그림과 같은 스크롤 상자 "바운스"와 같은 결과가 나타납니다.  <xref:System.Windows.Controls.DataGrid> 컨트롤의 <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth%2A>는 1000으로, <xref:System.Windows.FrameworkElement.Width%2A>는 200으로 설정되어 있다고 가정해 보겠습니다.  "오른쪽 가장자리"로 스크롤하면 후보 오프셋 1000 - 200 = 800이 사용됩니다.  해당 오프셋으로 스크롤하는 동안 새 열의 가상화가 취소됩니다. 열이 매우 넓어서 <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth%2A>가 2000으로 변경된다고 가정하겠습니다.  스크롤은 <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset%2A>=800에서 종료되며 엄지는 스크롤 막대 가운데 근처로 다시 "바운스"됩니다. 이 위치에 해당하는 값은 800/2000=40%입니다.  
  
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]부터 이러한 상황이 발생하는 경우 새 후보 오프셋이 다시계산 됩니다. (세로 스크롤도 이미 이와 같이 작동합니다.)  
  
## <a name="impact"></a>영향  
 이 변경으로 인해 최종 사용자가 오프셋을 더욱 쉽게 예측할 수 있는 직관적인 환경이 생성됩니다. 하지만 가로 스크롤 이후 <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset%2A?displayProperty=fullName>(최종 사용자가 호출하거나 명시적 <xref:System.Windows.Controls.Primitives.IScrollInfo.SetHorizontalOffset%2A?displayProperty=fullName> 호출을 통해 호출됨)의 정확한 값에 따라 동작이 달라지는 앱에도 영향을 줄 수 있습니다.  
  
## <a name="mitigation"></a>완화  
 <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset%2A?displayProperty=fullName>의 예측 값을 사용하는 앱의 경우 가상화 취소로 인해 <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth%2A>가 변경될 수 있는 가로 스크롤 이후 실제 값과 <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth%2A>의 값을 검색하도록 변경해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [런타임 변경 내용](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6-2.md)
