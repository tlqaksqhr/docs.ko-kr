---
title: "Windows Forms Timer 구성 & # 39의 제한 사항; s Interval 속성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- timers [Windows Forms], event intervals
- Interval property [Windows Forms], limitations
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], limitations of Interval property
ms.assetid: 7e5fb513-77e7-4046-a8e8-aab94e61ca0f
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e9c42a0946cf29415f7bb12345da6784e0c276d5
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="limitations-of-the-windows-forms-timer-component39s-interval-property"></a><span data-ttu-id="e3810-102">Windows Forms Timer 구성 & # 39의 제한 사항; s Interval 속성</span><span class="sxs-lookup"><span data-stu-id="e3810-102">Limitations of the Windows Forms Timer Component&#39;s Interval Property</span></span>
<span data-ttu-id="e3810-103">Windows Forms <xref:System.Windows.Forms.Timer> 구성 요소에는 <xref:System.Windows.Forms.Timer.Interval%2A> 타이머 이벤트와 다음 사이 경과 하는 시간 (밀리초)의 수를 지정 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="e3810-103">The Windows Forms <xref:System.Windows.Forms.Timer> component has an <xref:System.Windows.Forms.Timer.Interval%2A> property that specifies the number of milliseconds that pass between one timer event and the next.</span></span> <span data-ttu-id="e3810-104">타이머를 계속 수신 하는 구성 요소 비활성화 되어 있지 않으면는 <xref:System.Windows.Forms.Timer.Tick> 거의 같은 시간 간격으로 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="e3810-104">Unless the component is disabled, a timer continues to receive the <xref:System.Windows.Forms.Timer.Tick> event at roughly equal intervals of time.</span></span>  
  
 <span data-ttu-id="e3810-105">이 구성 요소는 Windows Forms 환경에 맞게 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e3810-105">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="e3810-106">서버 환경에 적합한 타이머가 필요한 경우 [서버 기반 타이머 소개](http://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e3810-106">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](http://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).</span></span>  
  
## <a name="the-interval-property"></a><span data-ttu-id="e3810-107">간격 속성</span><span class="sxs-lookup"><span data-stu-id="e3810-107">The Interval Property</span></span>  
 <span data-ttu-id="e3810-108"><xref:System.Windows.Forms.Timer.Interval%2A> 속성이 프로그래밍할 때 고려해 야 할 몇 가지 제한이 <xref:System.Windows.Forms.Timer> 구성 요소:</span><span class="sxs-lookup"><span data-stu-id="e3810-108">The <xref:System.Windows.Forms.Timer.Interval%2A> property has a few limitations to consider when you are programming a <xref:System.Windows.Forms.Timer> component:</span></span>  
  
-   <span data-ttu-id="e3810-109">응용 프로그램 또는 다른 응용 프로그램은 시스템에 많은 요청을 할 경우-긴 루프, 과도 한 계산 또는 드라이브, 네트워크, 포트 액세스 등-응용 프로그램으로 타이머 이벤트를 자주 받지는 <xref:System.Windows.Forms.Timer.Interval%2A> 속성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3810-109">If your application or another application is making heavy demands on the system — such as long loops, intensive calculations, or drive, network, or port access — your application may not get timer events as often as the <xref:System.Windows.Forms.Timer.Interval%2A> property specifies.</span></span>  
  
-   <span data-ttu-id="e3810-110">간격 시간에서 경과 보장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e3810-110">The interval is not guaranteed to elapse exactly on time.</span></span> <span data-ttu-id="e3810-111">정확성을 보장 하려면 타이머 필요에 따라 시스템 시간을 확인 하기 보다는 해야 추적 하기 위해 누적 된 시간 내부적으로 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3810-111">To ensure accuracy, the timer should check the system clock as needed, rather than try to keep track of accumulated time internally.</span></span>  
  
-   <span data-ttu-id="e3810-112">전체 자릿수는 <xref:System.Windows.Forms.Timer.Interval%2A> 속성은 밀리초에서 단위입니다.</span><span class="sxs-lookup"><span data-stu-id="e3810-112">The precision of the <xref:System.Windows.Forms.Timer.Interval%2A> property is in milliseconds.</span></span> <span data-ttu-id="e3810-113">일부 컴퓨터는 밀리초 보다 더 높은 해상도 고해상도 카운터를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3810-113">Some computers provide a high-resolution counter that has a resolution higher than milliseconds.</span></span> <span data-ttu-id="e3810-114">이러한 카운터의 가용성을 컴퓨터의 프로세서 하드웨어에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="e3810-114">The availability of such a counter depends on the processor hardware of your computer.</span></span> <span data-ttu-id="e3810-115">자세한 내용은 http://support.microsoft.com에서 Microsoft 기술 자료에서 문서 172338, "어떻게를 사용 하 여 QueryPerformanceCounter에 시간 코드를"를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3810-115">For more information, see article 172338, "How To Use QueryPerformanceCounter to Time Code," in the Microsoft Knowledge Base at http://support.microsoft.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3810-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e3810-116">See Also</span></span>  
 <xref:System.Windows.Forms.Timer>  
 [<span data-ttu-id="e3810-117">Timer 구성 요소</span><span class="sxs-lookup"><span data-stu-id="e3810-117">Timer Component</span></span>](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)  
 [<span data-ttu-id="e3810-118">Timer 구성 요소 개요</span><span class="sxs-lookup"><span data-stu-id="e3810-118">Timer Component Overview</span></span>](../../../../docs/framework/winforms/controls/timer-component-overview-windows-forms.md)
