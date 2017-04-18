---
title: "Timers | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "threading [.NET Framework], timers"
  - "timers, about timers"
ms.assetid: 7091500d-be18-499b-a942-95366ce185e5
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Timers
타이머는 특정 시간에 대리자가 호출되도록 지정할 수 있는 간단한 개체입니다.  스레드 풀의 스레드는 대기 작업을 수행합니다.  
  
 <xref:System.Threading.Timer?displayProperty=fullName> 클래스를 사용하는 방법은 간단합니다.  콜백 메서드, 콜백에 전달될 상태를 나타내는 개체, 초기 발생 시간, 콜백 호출 사이의 기간을 나타내는 시간에 <xref:System.Threading.TimerCallback> 대리자를 전달하여 **Timer**를 만듭니다.  보류 중인 타이머를 취소하려면 **Timer.Dispose** 함수를 호출합니다.  
  
> [!NOTE]
>  두 개의 다른 Timer 클래스가 있습니다.  <xref:System.Windows.Forms.Timer?displayProperty=fullName> 클래스는 비주얼 디자이너와 함께 작동되고 사용자 인터페이스 컨텍스트에서 사용되는 컨트롤이며 사용자 인터페이스 스레드에서 이벤트를 발생시킵니다.  <xref:System.Timers.Timer?displayProperty=fullName> 클래스는 <xref:System.ComponentModel.Component>에서 파생되므로 비주얼 디자이너와 함께 사용할 수 있고, 이벤트를 발생시키기는 하지만 <xref:System.Threading.ThreadPool> 스레드에서 발생시킵니다.  <xref:System.Threading.Timer?displayProperty=fullName> 클래스는 <xref:System.Threading.ThreadPool> 스레드에서 콜백을 만들고 이벤트 모델은 사용하지 않습니다.  또한 이 클래스는 다른 타이머와 달리 콜백 메서드에 상태 개체를 제공하며  매우 간단합니다.  
  
 다음 코드 예제에서는 **Enter** 키를 누를 때까지 1초\(1000밀리초\) 후에 시작하고 매초 작동하는 타이머를 시작합니다.  타이머에 대한 참조가 들어 있는 변수는 클래스 수준 필드로, 타이머가 실행되는 동안 가비지 수집의 영향을 받지 않도록 합니다.  적극적인 가비지 수집에 대한 자세한 내용은 <xref:System.GC.KeepAlive%2A>를 참조하십시오.  
  
 [!code-cpp[System.Threading.Timer#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.Timer/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.Timer#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.Timer/CS/source2.cs#2)]
 [!code-vb[System.Threading.Timer#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.Timer/VB/source2.vb#2)]  
  
## 참고 항목  
 <xref:System.Threading.Timer>   
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)