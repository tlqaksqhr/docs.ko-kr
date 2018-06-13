---
title: 타이머
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [.NET Framework], timers
- timers, about timers
ms.assetid: 7091500d-be18-499b-a942-95366ce185e5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 478484651bf839f842148f0b4164c9387db3b98a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33584959"
---
# <a name="timers"></a>타이머
타이머는 지정된 시간에 대리자가 호출되도록 지정할 수 있는 간단한 개체입니다. 스레드 풀의 스레드가 대기 작업을 수행합니다.  
  
 <xref:System.Threading.Timer?displayProperty=nameWithType> 클래스를 사용하는 것은 간단합니다. 콜백 메서드에 <xref:System.Threading.TimerCallback> 대리자를 전달하는 **타이머**, 콜백에 전달되는 상태를 나타내는 개체, 초기 발생 시간, 콜백 호출 사이의 기간을 나타내는 시간을 생성합니다. 보류 중인 타이머를 취소하려면 **Timer.Dispose** 함수를 호출하세요.  
  
> [!NOTE]
>  두 가지 다른 타이머 클래스가 있습니다. <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> 클래스는 비주얼 디자이너와 함께 작동하며 사용자 인터페이스 컨텍스트에서 사용되는 컨트롤로, 사용자 인터페이스 스레드에서 이벤트를 발생시킵니다. <xref:System.Timers.Timer?displayProperty=nameWithType> 클래스는 <xref:System.ComponentModel.Component>에서 파생되므로 비주얼 디자이너와 함께 사용할 수 있습니다. 이벤트도 발생시키지만 <xref:System.Threading.ThreadPool> 스레드에서는 발생시킵니다. <xref:System.Threading.Timer?displayProperty=nameWithType> 클래스는 <xref:System.Threading.ThreadPool> 스레드에서 콜백을 생성하며 이벤트 모델을 전혀 사용하지 않습니다. 또한 콜백 메서드에 상태 개체도 제공합니다. 다른 타이머는 이 작업을 수행하지 않습니다. 그리고 이 클래스는 매우 간단합니다.  
  
 다음 코드 예제에서는 1초(1000밀리초) 후에 시작하고 **Enter** 키를 누를 때까지 매초 틱하는 타이머를 시작합니다. 타이머에 대한 참조를 포함하는 변수는 클래스 수준 필드이므로 타이머가 여전히 실행 중인 동안 타이머가 가비지 수집되지 않도록 할 수 있습니다. 적극적인 가비지 수집에 대한 자세한 내용은 <xref:System.GC.KeepAlive%2A>를 참조하세요.  
  
 [!code-cpp[System.Threading.Timer#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.Timer/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.Timer#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.Timer/CS/source2.cs#2)]
 [!code-vb[System.Threading.Timer#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.Timer/VB/source2.vb#2)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Threading.Timer>  
 [스레딩 개체 및 기능](../../../docs/standard/threading/threading-objects-and-features.md)
