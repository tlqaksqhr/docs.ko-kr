---
title: "방법: 동기적으로 시계 검색"
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
- clocks [WPF], seeking synchronously
- seeking clocks synchronously [WPF]
ms.assetid: e5b7529b-b7d0-40d2-9e1d-fa4b5e736e96
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 90611e0b18e58e4c24b44e7c87cba56e4b0b01ad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-seek-a-clock-synchronously"></a>방법: 동기적으로 시계 검색
사용 된 <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> 메서드를 특정 시점으로 시계를 동기적으로 검색 합니다. 다음 예제에서는 모두는 <xref:System.Windows.Media.Animation.ClockController.Seek%2A> 및 <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> 의 메서드는 <xref:System.Windows.Media.Animation.ClockController>합니다.  
  
 검색 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Animation.Clock>seek 스토리 보드를 참조 하는 방법을 보여 주는 예제에 대 한; [동기적 스토리 보드 Seek](../../../../docs/framework/wpf/graphics-multimedia/how-to-seek-a-storyboard-synchronously.md) 합니다.  
  
## <a name="example"></a>예  
 [!code-csharp[ClockController_procedural_snip#ClockControllerSeekExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClockController_procedural_snip/CSharp/SeekAlignedToLastTickExample.cs#clockcontrollerseekexample)]
 [!code-vb[ClockController_procedural_snip#ClockControllerSeekExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClockController_procedural_snip/visualbasic/seekalignedtolasttickexample.vb#clockcontrollerseekexample)]
