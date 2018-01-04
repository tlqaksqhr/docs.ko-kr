---
title: "SoundPlayer 클래스 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- playing sounds [Windows Forms], SoundPlayer class
- SoundPlayer class [Windows Forms], about SoundPlayer class
- sounds [Windows Forms], playing
ms.assetid: fcebb938-62b9-4677-9cbe-6465bc863e22
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3dc355fbe0d8262cb24779b99375d6075f758bbc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="soundplayer-class-overview"></a><span data-ttu-id="f03ee-102">SoundPlayer 클래스 개요</span><span class="sxs-lookup"><span data-stu-id="f03ee-102">SoundPlayer Class Overview</span></span>
<span data-ttu-id="f03ee-103"><xref:System.Media.SoundPlayer> 클래스를 사용하여 응용 프로그램에 소리를 쉽게 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f03ee-103">The <xref:System.Media.SoundPlayer> class enables you to easily include sounds in your applications.</span></span>  
  
 <span data-ttu-id="f03ee-104"><xref:System.Media.SoundPlayer> 클래스.wav 형식으로 또는 리소스에서 HTTP 또는 UNC 위치에서 사운드 파일을 재생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f03ee-104">The <xref:System.Media.SoundPlayer> class can play sound files in the .wav format, either from a resource or from UNC or HTTP locations.</span></span> <span data-ttu-id="f03ee-105">또한는 <xref:System.Media.SoundPlayer> 클래스를 사용 하면 비동기적으로 소리를 재생 하거나 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f03ee-105">Additionally, the <xref:System.Media.SoundPlayer> class enables you to load or play sounds asynchronously.</span></span>  
  
 <span data-ttu-id="f03ee-106"><xref:System.Media.SystemSounds> 클래스를 사용하여 경고음을 포함한 일반적인 시스템 소리를 재생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f03ee-106">You can also use the <xref:System.Media.SystemSounds> class to play common system sounds, including a beep.</span></span>  
  
## <a name="commonly-used-properties-methods-and-events"></a><span data-ttu-id="f03ee-107">일반적으로 사용되는 속성, 메서드 및 이벤트</span><span class="sxs-lookup"><span data-stu-id="f03ee-107">Commonly Used Properties, Methods, and Events</span></span>  
  
|<span data-ttu-id="f03ee-108">이름</span><span class="sxs-lookup"><span data-stu-id="f03ee-108">Name</span></span>|<span data-ttu-id="f03ee-109">설명</span><span class="sxs-lookup"><span data-stu-id="f03ee-109">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="f03ee-110"><xref:System.Media.SoundPlayer.SoundLocation%2A> 속성</span><span class="sxs-lookup"><span data-stu-id="f03ee-110"><xref:System.Media.SoundPlayer.SoundLocation%2A> property</span></span>|<span data-ttu-id="f03ee-111">소리의 파일 경로 또는 웹 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="f03ee-111">The file path or Web address of the sound.</span></span> <span data-ttu-id="f03ee-112">허용되는 값은 UNC 또는 HTTP일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f03ee-112">Acceptable values can be UNC or HTTP.</span></span>|  
|<span data-ttu-id="f03ee-113"><xref:System.Media.SoundPlayer.LoadTimeout%2A> 속성</span><span class="sxs-lookup"><span data-stu-id="f03ee-113"><xref:System.Media.SoundPlayer.LoadTimeout%2A> property</span></span>|<span data-ttu-id="f03ee-114">예외를 throw하기 전에 프로그램에서 소리를 로드하기 위해 대기하는 시간(밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="f03ee-114">The number of milliseconds your program will wait to load a sound before it throws an exception.</span></span> <span data-ttu-id="f03ee-115">기본값은 10초입니다.</span><span class="sxs-lookup"><span data-stu-id="f03ee-115">The default is 10 seconds.</span></span>|  
|<span data-ttu-id="f03ee-116"><xref:System.Media.SoundPlayer.IsLoadCompleted%2A> 속성</span><span class="sxs-lookup"><span data-stu-id="f03ee-116"><xref:System.Media.SoundPlayer.IsLoadCompleted%2A> property</span></span>|<span data-ttu-id="f03ee-117">소리의 로드를 완료했는지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f03ee-117">A Boolean value indicating whether the sound has finished loading.</span></span>|  
|<span data-ttu-id="f03ee-118"><xref:System.Media.SoundPlayer.Load%2A> 메서드</span><span class="sxs-lookup"><span data-stu-id="f03ee-118"><xref:System.Media.SoundPlayer.Load%2A> method</span></span>|<span data-ttu-id="f03ee-119">소리를 동기적으로 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="f03ee-119">Loads a sound synchronously.</span></span>|  
|<span data-ttu-id="f03ee-120"><xref:System.Media.SoundPlayer.LoadAsync%2A> 메서드</span><span class="sxs-lookup"><span data-stu-id="f03ee-120"><xref:System.Media.SoundPlayer.LoadAsync%2A> method</span></span>|<span data-ttu-id="f03ee-121">소리를 비동기적으로 로드하기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="f03ee-121">Begins to load a sound asynchronously.</span></span> <span data-ttu-id="f03ee-122">로드가 완료 되 면 발생는 <xref:System.Media.SoundPlayer.OnLoadCompleted%2A> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="f03ee-122">When loading is complete, it raises the <xref:System.Media.SoundPlayer.OnLoadCompleted%2A> event.</span></span>|  
|<span data-ttu-id="f03ee-123"><xref:System.Media.SoundPlayer.Play%2A> 메서드</span><span class="sxs-lookup"><span data-stu-id="f03ee-123"><xref:System.Media.SoundPlayer.Play%2A> method</span></span>|<span data-ttu-id="f03ee-124">에 지정 된 소리를 재생는 <xref:System.Media.SoundPlayer.SoundLocation%2A> 또는 <xref:System.Media.SoundPlayer.Stream%2A> 새 스레드에서 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="f03ee-124">Plays the sound specified in the <xref:System.Media.SoundPlayer.SoundLocation%2A> or <xref:System.Media.SoundPlayer.Stream%2A> property in a new thread.</span></span>|  
|<span data-ttu-id="f03ee-125"><xref:System.Media.SoundPlayer.PlaySync%2A> 메서드</span><span class="sxs-lookup"><span data-stu-id="f03ee-125"><xref:System.Media.SoundPlayer.PlaySync%2A> method</span></span>|<span data-ttu-id="f03ee-126">에 지정 된 소리를 재생는 <xref:System.Media.SoundPlayer.SoundLocation%2A> 또는 <xref:System.Media.SoundPlayer.Stream%2A> 는 현재 스레드의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="f03ee-126">Plays the sound specified in the <xref:System.Media.SoundPlayer.SoundLocation%2A> or <xref:System.Media.SoundPlayer.Stream%2A> property in the current thread.</span></span>|  
|<span data-ttu-id="f03ee-127"><xref:System.Media.SoundPlayer.Stop%2A> 메서드</span><span class="sxs-lookup"><span data-stu-id="f03ee-127"><xref:System.Media.SoundPlayer.Stop%2A> method</span></span>|<span data-ttu-id="f03ee-128">현재 재생 중인 모든 소리를 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="f03ee-128">Stops any sound currently playing.</span></span>|  
|<span data-ttu-id="f03ee-129"><xref:System.Media.SoundPlayer.LoadCompleted>이벤트</span><span class="sxs-lookup"><span data-stu-id="f03ee-129"><xref:System.Media.SoundPlayer.LoadCompleted> event</span></span>|<span data-ttu-id="f03ee-130">소리의 로드를 시도한 후에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="f03ee-130">Raised after the load of a sound is attempted.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f03ee-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f03ee-131">See Also</span></span>  
 <xref:System.Media.SoundPlayer>  
 <xref:System.Media.SystemSounds>
