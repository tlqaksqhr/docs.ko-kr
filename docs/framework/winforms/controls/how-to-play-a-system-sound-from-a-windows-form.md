---
title: "방법: Windows Form에서 시스템 소리 재생"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sounds [Windows Forms], playing for system events
- playing sounds [Windows Forms], Windows Forms
- system sounds [Windows Forms], playing from Windows Forms
- playing sounds [Windows Forms], system
- SoundPlayer class [Windows Forms], system sounds
- sounds [Windows Forms], playing
- examples [Windows Forms], sounds
ms.assetid: afb206ff-4824-4804-a8d4-185bf5ad8e7c
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7b620b7386752e531a8d5252159c5f172176890a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-play-a-system-sound-from-a-windows-form"></a>방법: Windows Form에서 시스템 소리 재생
다음 코드 예제에서는 런타임에 `Exclamation` 시스템 소리를 재생합니다. 시스템 소리에 대 한 자세한 내용은 참조 하십시오. <xref:System.Media.SystemSounds>합니다.  
  
## <a name="example"></a>예  
  
```vb  
Public Sub PlayExclamation()  
    SystemSounds.Exclamation.Play()  
End Sub  
```  
  
```csharp  
public void playExclamation()  
{  
    SystemSounds.Exclamation.Play();  
}  
```  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   <xref:System.Media?displayProperty=nameWithType> 네임스페이스에 대한 참조  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Media.SoundPlayer>  
 <xref:System.Media.SystemSounds>  
 [방법: Windows Form에서 경고음 재생](../../../../docs/framework/winforms/controls/how-to-play-a-beep-from-a-windows-form.md)  
 [방법: Windows Form에서 소리 재생](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)
