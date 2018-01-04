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
# <a name="soundplayer-class-overview"></a>SoundPlayer 클래스 개요
<xref:System.Media.SoundPlayer> 클래스를 사용하여 응용 프로그램에 소리를 쉽게 포함할 수 있습니다.  
  
 <xref:System.Media.SoundPlayer> 클래스.wav 형식으로 또는 리소스에서 HTTP 또는 UNC 위치에서 사운드 파일을 재생할 수 있습니다. 또한는 <xref:System.Media.SoundPlayer> 클래스를 사용 하면 비동기적으로 소리를 재생 하거나 로드할 수 있습니다.  
  
 <xref:System.Media.SystemSounds> 클래스를 사용하여 경고음을 포함한 일반적인 시스템 소리를 재생할 수 있습니다.  
  
## <a name="commonly-used-properties-methods-and-events"></a>일반적으로 사용되는 속성, 메서드 및 이벤트  
  
|이름|설명|  
|----------|-----------------|  
|<xref:System.Media.SoundPlayer.SoundLocation%2A> 속성|소리의 파일 경로 또는 웹 주소입니다. 허용되는 값은 UNC 또는 HTTP일 수 있습니다.|  
|<xref:System.Media.SoundPlayer.LoadTimeout%2A> 속성|예외를 throw하기 전에 프로그램에서 소리를 로드하기 위해 대기하는 시간(밀리초)입니다. 기본값은 10초입니다.|  
|<xref:System.Media.SoundPlayer.IsLoadCompleted%2A> 속성|소리의 로드를 완료했는지 여부를 나타내는 부울 값입니다.|  
|<xref:System.Media.SoundPlayer.Load%2A> 메서드|소리를 동기적으로 로드합니다.|  
|<xref:System.Media.SoundPlayer.LoadAsync%2A> 메서드|소리를 비동기적으로 로드하기 시작합니다. 로드가 완료 되 면 발생는 <xref:System.Media.SoundPlayer.OnLoadCompleted%2A> 이벤트입니다.|  
|<xref:System.Media.SoundPlayer.Play%2A> 메서드|에 지정 된 소리를 재생는 <xref:System.Media.SoundPlayer.SoundLocation%2A> 또는 <xref:System.Media.SoundPlayer.Stream%2A> 새 스레드에서 속성입니다.|  
|<xref:System.Media.SoundPlayer.PlaySync%2A> 메서드|에 지정 된 소리를 재생는 <xref:System.Media.SoundPlayer.SoundLocation%2A> 또는 <xref:System.Media.SoundPlayer.Stream%2A> 는 현재 스레드의 속성입니다.|  
|<xref:System.Media.SoundPlayer.Stop%2A> 메서드|현재 재생 중인 모든 소리를 중지합니다.|  
|<xref:System.Media.SoundPlayer.LoadCompleted>이벤트|소리의 로드를 시도한 후에 발생합니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Media.SoundPlayer>  
 <xref:System.Media.SystemSounds>
