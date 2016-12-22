---
title: "Playing Sounds (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "system sounds, playing"
  - "system sounds"
  - "playing sounds, Visual Basic"
  - "sound loops"
  - "My.Computer.Audio object, tasks"
  - "sounds, playing"
  - "sounds, background"
  - "playing sounds"
ms.assetid: f0d9e4ab-57c7-47b6-86d3-99ff07078040
caps.latest.revision: 21
caps.handback.revision: 21
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Playing Sounds (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

`My.Computer.Audio` 개체는 소리를 재생하기 위한 메서드를 제공합니다.  
  
## 소리 재생  
 백그라운드 재생을 하면 소리가 재생되는 동안 응용 프로그램에서 다른 코드를 실행할 수 있습니다.  `My.Computer.Audio.Play` 메서드를 사용하면 응용 프로그램에서 한 번에 하나의 백그라운드 소리만 재생할 수 있습니다. 응용 프로그램에서 새 백그라운드 소리를 재생하면 이전 백그라운드 소리는 중지됩니다.  소리를 재생하고 끝날 때까지 기다리려도 됩니다.  
  
 다음 예제에서는 `My.Computer.Audio.Play` 메서드는 소리를 재생 합니다.  `AudioPlayMode.WaitToComplete`이 지정된 경우 `My.Computer.Audio.Play`는 호출 코드를 계속 실행하기 전에 소리 재생이 완료될 때까지 기다립니다.  이 예제를 사용 하는 경우 파일 이름을 컴퓨터에 있는.wav 사운드 파일을 참조 하도록 확인 해야  
  
 [!code-vb[VbVbalrMyComputer#15](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_1.vb)]  
  
 다음 예제에서는 `My.Computer.Audio.Play` 메서드는 소리를 재생 합니다.  이 예제를 사용 하는 경우 응용 프로그램 리소스 폭포 라는 이름의.wav 사운드 파일을 포함 해야 합니다.  
  
 [!code-vb[VbVbalrMyComputer#16](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_2.vb)]  
  
## 소리 반복 재생  
 다음 예제에서는 `My.Computer.Audio.Play` 메서드는 백그라운드에서 지정한 사운드 재생 때 `PlayMode.BackgroundLoop` 지정 됩니다.  이 예제를 사용 하는 경우 파일 이름을 컴퓨터에 있는.wav 사운드 파일을 참조 하도록 해야 합니다.  
  
 [!code-vb[VbVbalrMyComputer#11](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_3.vb)]  
  
 다음 예제에서는 `My.Computer.Audio.Play` 메서드는 백그라운드에서 지정한 사운드 재생 때 `PlayMode.BackgroundLoop` 지정 됩니다.  이 예제를 사용 하는 경우 응용 프로그램 리소스 폭포 라는 이름의.wav 사운드 파일을 포함 해야 합니다.  
  
 [!code-vb[VbVbalrMyComputer#12](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_4.vb)]  
  
 앞의 코드 예제는 IntelliSense 코드 조각으로 사용할 수도 있습니다.  이 코드 조각은 코드 조각 선택기의 **Windows Forms 응용 프로그램 \> 사운드**에 있습니다.  자세한 내용은 [코드 조각](/visual-studio/ide/code-snippets)를 참조하십시오.  
  
 일반적으로 응용 프로그램에서 소리를 반복 재생할 때는 언젠가는 소리를 중지해야 합니다.  
  
## 백그라운드에서 소리 재생 중지  
 응용 프로그램에서 현재 재생 중인 백그라운드 또는 반복 재생 소리를 중지하려면 `My.Computer.Audio.Stop` 메서드를 사용합니다.  
  
 일반적으로 응용 프로그램에서 소리가 반복 재생될 때는 언젠가는 소리를 중지해야 합니다.  
  
 다음 예제에서는 백그라운드에서 재생 되는 소리를 중지 합니다.  
  
 [!code-vb[VbVbalrMyComputer#18](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_5.vb)]  
  
 앞의 코드 예제는 IntelliSense 코드 조각으로 사용할 수도 있습니다.  이 코드 조각은 코드 조각 선택기의 **Windows Forms 응용 프로그램 \> 사운드**에 있습니다.  자세한 내용은 [코드 조각](/visual-studio/ide/code-snippets)를 참조하십시오.  
  
## 시스템 소리 재생  
 `My.Computer.Audio.PlaySystemSound` 메서드를 사용하여 지정된 시스템 소리를 재생합니다.  
  
 `My.Computer.Audio.PlaySystemSound` 메서드는 <xref:System.Media.SystemSound> 클래스의 공유 멤버 중 하나를 매개 변수로 사용합니다.  시스템 소리 <xref:System.Media.SystemSounds.Asterisk%2A>는 일반적으로 오류를 나타냅니다.  
  
 다음 예제는 `My.Computer.Audio.PlaySystemSound` 시스템 소리를 재생 하는 방법.  
  
 [!code-vb[VbVbalrMyComputer#17](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_6.vb)]  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.Devices.Audio>   
 <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A>   
 <xref:Microsoft.VisualBasic.Devices.Audio.PlaySystemSound%2A>   
 <xref:Microsoft.VisualBasic.Devices.Audio.Stop%2A>   
 <xref:Microsoft.VisualBasic.AudioPlayMode>