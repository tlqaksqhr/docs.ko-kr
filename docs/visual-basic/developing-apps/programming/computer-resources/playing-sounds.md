---
title: 소리 재생(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- system sounds, playing
- system sounds
- playing sounds, Visual Basic
- sound loops
- My.Computer.Audio object, tasks
- sounds, playing
- sounds, background
- playing sounds
ms.assetid: f0d9e4ab-57c7-47b6-86d3-99ff07078040
ms.openlocfilehash: decd845fde5bd4fad702cfe05fd63fcc180b63a6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588460"
---
# <a name="playing-sounds-visual-basic"></a>소리 재생(Visual Basic)
`My.Computer.Audio` 개체는 소리 재생 메서드를 제공합니다.  
  
## <a name="playing-sounds"></a>소리 재생  
 백그라운드 재생을 사용하면 응용 프로그램이 소리가 재생되는 동안 다른 코드를 실행할 수 있습니다. `My.Computer.Audio.Play` 메서드를 사용하면 응용 프로그램이 한 번에 하나의 배경 소리만 재생할 수 있습니다. 응용 프로그램이 새 배경 소리를 재생하는 경우 이전 배경 소리의 재생을 중지합니다. 소리를 재생하고 완료될 때까지 기다릴 수도 있습니다.  
  
 다음 예제에서는 `My.Computer.Audio.Play` 메서드가 소리를 재생합니다. `AudioPlayMode.WaitToComplete`를 지정하면 `My.Computer.Audio.Play`는 호출하는 코드가 계속되기 전에 소리가 완료될 때까지 기다립니다. 이 예제를 사용하는 경우 파일 이름이 컴퓨터에 있는 .wav 사운드 파일을 가리키는지 확인해야 합니다.  
  
 [!code-vb[VbVbalrMyComputer#15](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_1.vb)]  
  
 다음 예제에서는 `My.Computer.Audio.Play` 메서드가 소리를 재생합니다. 이 예제를 사용하는 경우 응용 프로그램 리소스에 Waterfall로 이름이 지정된 .wav 사운드 파일이 포함되어 있는지 확인해야 합니다.  
  
 [!code-vb[VbVbalrMyComputer#16](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_2.vb)]  
  
## <a name="playing-looping-sounds"></a>소리 반복 재생  
 다음 예제에서 `My.Computer.Audio.Play` 메서드는 `PlayMode.BackgroundLoop`가 지정된 경우 백그라운드에서 지정한 소리를 재생합니다. 이 예제를 사용하는 경우 파일 이름이 컴퓨터에 있는 .wav 사운드 파일을 가리키는지 확인해야 합니다.  
  
 [!code-vb[VbVbalrMyComputer#11](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_3.vb)]  
  
 다음 예제에서 `My.Computer.Audio.Play` 메서드는 `PlayMode.BackgroundLoop`가 지정된 경우 백그라운드에서 지정한 소리를 재생합니다. 이 예제를 사용하는 경우 응용 프로그램 리소스에 Waterfall로 이름이 지정된 .wav 사운드 파일이 포함되어 있는지 확인해야 합니다.  
  
 [!code-vb[VbVbalrMyComputer#12](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_4.vb)]  
  
 앞의 코드 예제는 IntelliSense 코드 조각으로 사용할 수도 있습니다. 코드 조각 선택에서 **Windows Forms 응용 프로그램 > 소리**에 있습니다. 자세한 내용은 [코드 조각](/visualstudio/ide/code-snippets)을 참조하세요.  
  
 일반적으로 응용 프로그램이 소리를 반복 재생하는 경우 결국 소리가 중지됩니다.  
  
## <a name="stopping-the-playing-of-sounds-in-the-background"></a>백그라운드에서 소리 재생 중지  
 `My.Computer.Audio.Stop` 메서드를 사용하여 응용 프로그램이 백그라운드에서 현재 재생 중인 소리나 소리 반복 재생을 중지할 수 있습니다.  
  
 일반적으로 응용 프로그램이 소리를 반복 재생하는 경우 어느 시점에 소리가 중지됩니다.  
  
 다음 예제에서는 백그라운드에서 재생 중인 소리를 중지합니다.  
  
 [!code-vb[VbVbalrMyComputer#18](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_5.vb)]  
  
 앞의 코드 예제는 IntelliSense 코드 조각으로 사용할 수도 있습니다. 코드 조각 선택에서 **Windows Forms 응용 프로그램 > 소리**에 있습니다. 자세한 내용은 [코드 조각](/visualstudio/ide/code-snippets)을 참조하세요.  
  
## <a name="playing-system-sounds"></a>시스템 소리 재생  
 `My.Computer.Audio.PlaySystemSound` 메서드를 사용하여 지정된 시스템 소리를 재생할 수 있습니다.  
  
 `My.Computer.Audio.PlaySystemSound` 메서드는 <xref:System.Media.SystemSound> 클래스의 공유 멤버 중 하나를 매개 변수로 사용합니다. 시스템 소리 <xref:System.Media.SystemSounds.Asterisk%2A>는 일반적으로 오류를 나타냅니다.  
  
 다음 예제에서는 `My.Computer.Audio.PlaySystemSound` 메서드를 사용하여 시스템 소리를 재생합니다.  
  
 [!code-vb[VbVbalrMyComputer#17](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_6.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.Devices.Audio>  
 <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A>  
 <xref:Microsoft.VisualBasic.Devices.Audio.PlaySystemSound%2A>  
 <xref:Microsoft.VisualBasic.Devices.Audio.Stop%2A>  
 <xref:Microsoft.VisualBasic.AudioPlayMode>
