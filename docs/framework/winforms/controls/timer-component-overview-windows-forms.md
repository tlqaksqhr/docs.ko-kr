---
title: "Timer 구성 요소 개요(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Timer
helpviewer_keywords:
- Timer component [Windows Forms], about Timer components
- timers [Windows Forms], about timers
ms.assetid: e672c05b-a8b6-4b26-9e4d-9223aa9e3873
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 90296d2741a96e8788bf7a9b18bf3ea303ad2bae
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="timer-component-overview-windows-forms"></a><span data-ttu-id="f9e87-102">Timer 구성 요소 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="f9e87-102">Timer Component Overview (Windows Forms)</span></span>
<span data-ttu-id="f9e87-103">Windows Forms <xref:System.Windows.Forms.Timer>는 일정한 간격마다 이벤트를 발생시키는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e87-103">The Windows Forms <xref:System.Windows.Forms.Timer> is a component that raises an event at regular intervals.</span></span> <span data-ttu-id="f9e87-104">이 구성 요소는 Windows Forms 환경에 맞게 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e87-104">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="f9e87-105">서버 환경에 적합한 타이머가 필요한 경우 [서버 기반 타이머 소개](http://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f9e87-105">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](http://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).</span></span>  
  
## <a name="key-properties-methods-and-events"></a><span data-ttu-id="f9e87-106">키 속성, 메서드 및 이벤트</span><span class="sxs-lookup"><span data-stu-id="f9e87-106">Key Properties, Methods, and Events</span></span>  
 <span data-ttu-id="f9e87-107">간격의 길이 정의한는 <xref:System.Windows.Forms.Timer.Interval%2A> 속성, 값 (밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e87-107">The length of the intervals is defined by the <xref:System.Windows.Forms.Timer.Interval%2A> property, whose value is in milliseconds.</span></span> <span data-ttu-id="f9e87-108">구성 요소를 사용 하는 경우는 <xref:System.Windows.Forms.Timer.Tick> 이벤트가 간격 마다.</span><span class="sxs-lookup"><span data-stu-id="f9e87-108">When the component is enabled, the <xref:System.Windows.Forms.Timer.Tick> event is raised every interval.</span></span> <span data-ttu-id="f9e87-109">코드 실행을 추가할 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e87-109">This is where you would add code to be executed.</span></span> <span data-ttu-id="f9e87-110">자세한 내용은 참조 [하는 방법: Windows Forms Timer 구성 된 설정 간격 프로시저 실행](../../../../docs/framework/winforms/controls/run-procedures-at-set-intervals-with-wf-timer-component.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f9e87-110">For more information, see [How to: Run Procedures at Set Intervals with the Windows Forms Timer Component](../../../../docs/framework/winforms/controls/run-procedures-at-set-intervals-with-wf-timer-component.md).</span></span> <span data-ttu-id="f9e87-111">주요 메서드는 <xref:System.Windows.Forms.Timer> 구성 요소는 <xref:System.Windows.Forms.Timer.Start%2A> 및 <xref:System.Windows.Forms.Timer.Stop%2A>, 타이머를 켜고 끄려면입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e87-111">The key methods of the <xref:System.Windows.Forms.Timer> component are <xref:System.Windows.Forms.Timer.Start%2A> and <xref:System.Windows.Forms.Timer.Stop%2A>, which turn the timer on and off.</span></span> <span data-ttu-id="f9e87-112">타이머 꺼진 다시 설정 합니다. 일시 중지 하는 방법이 있으면는 <xref:System.Windows.Forms.Timer> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e87-112">When the timer is switched off, it resets; there is no way to pause a <xref:System.Windows.Forms.Timer> component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9e87-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f9e87-113">See Also</span></span>  
 <xref:System.Windows.Forms.Timer>  
 [<span data-ttu-id="f9e87-114">Timer 구성 요소</span><span class="sxs-lookup"><span data-stu-id="f9e87-114">Timer Component</span></span>](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)  
 [<span data-ttu-id="f9e87-115">Windows Forms Timer 구성 요소의 Interval 속성에 대한 제한 사항</span><span class="sxs-lookup"><span data-stu-id="f9e87-115">Limitations of the Windows Forms Timer Component's Interval Property</span></span>](../../../../docs/framework/winforms/controls/limitations-of-the-timer-component-interval-property.md)
