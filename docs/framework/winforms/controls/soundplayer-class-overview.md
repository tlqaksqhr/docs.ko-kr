---
title: "SoundPlayer 클래스 개요 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "소리 재생, SoundPlayer 클래스"
  - "SoundPlayer 클래스에 대 한 SoundPlayer 클래스"
  - "소리 재생"
ms.assetid: fcebb938-62b9-4677-9cbe-6465bc863e22
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# SoundPlayer 클래스 개요
<xref:System.Media.SoundPlayer> 클래스를 사용 하면 응용 프로그램에 소리를 쉽게 포함할 수 있습니다.  
  
 <xref:System.Media.SoundPlayer> 클래스.wav 형식의 UNC 또는 HTTP 위치 또는 리소스에서 사운드 파일을 재생할 수 있습니다. 또한는 <xref:System.Media.SoundPlayer> 클래스를 사용 하면 비동기적으로 소리를 재생 하거나 로드할 수 있습니다.  
  
 사용할 수도 있습니다는 <xref:System.Media.SystemSounds> 경고음을 포함 한 일반적인 시스템 소리를 재생 하는 클래스입니다.  
  
## <a name="commonly-used-properties-methods-and-events"></a>일반적으로 사용 되는 속성, 메서드 및 이벤트  
  
|이름|설명|  
|----------|-----------------|  
|<xref:System.Media.SoundPlayer.SoundLocation%2A> 속성|파일 경로 또는 소리의 웹 주소입니다. 허용 되는 값은 UNC 또는 HTTP 수 있습니다.|  
|<xref:System.Media.SoundPlayer.LoadTimeout%2A> 속성|예외를 throw 하는 프로그램을 대기 하기 전에 소리를 로드 하는 밀리초 수입니다. 기본값은 10초입니다.|  
|<xref:System.Media.SoundPlayer.IsLoadCompleted%2A> 속성|소리 로드 완료 되었는지 여부를 나타내는 부울 값입니다.|  
|<xref:System.Media.SoundPlayer.Load%2A> 메서드|소리를 동기적으로 로드합니다.|  
|<xref:System.Media.SoundPlayer.LoadAsync%2A> 메서드|소리를 비동기적으로 로드 하기 시작 합니다. 로드 완료 되 면 발생 시킵니다는 <xref:System.Media.SoundPlayer.OnLoadCompleted%2A> 이벤트입니다.|  
|<xref:System.Media.SoundPlayer.Play%2A> 메서드|에 지정 된 소리를 재생는 <xref:System.Media.SoundPlayer.SoundLocation%2A> 또는 <xref:System.Media.SoundPlayer.Stream%2A> 새 스레드의 속성입니다.|  
|<xref:System.Media.SoundPlayer.PlaySync%2A> 메서드|에 지정 된 소리를 재생는 <xref:System.Media.SoundPlayer.SoundLocation%2A> 또는 <xref:System.Media.SoundPlayer.Stream%2A> 에서 현재 스레드의 속성입니다.|  
|<xref:System.Media.SoundPlayer.Stop%2A> 메서드|현재 재생 되는 모든 소리가 중지 됩니다.|  
|<xref:System.Media.SoundPlayer.LoadCompleted> 이벤트|사운드의 로드를 시도 후에 발생 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Media.SoundPlayer>   
 <xref:System.Media.SystemSounds>