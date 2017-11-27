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
ms.openlocfilehash: 51de367f2558abfc28be740409d8a0d394065acf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-play-a-system-sound-from-a-windows-form"></a><span data-ttu-id="382ba-102">방법: Windows Form에서 시스템 소리 재생</span><span class="sxs-lookup"><span data-stu-id="382ba-102">How to: Play a System Sound from a Windows Form</span></span>
<span data-ttu-id="382ba-103">다음 코드 예제에서는 런타임에 `Exclamation` 시스템 소리를 재생합니다.</span><span class="sxs-lookup"><span data-stu-id="382ba-103">The following code example plays the `Exclamation` system sound at run time.</span></span> <span data-ttu-id="382ba-104">시스템 소리에 대 한 자세한 내용은 참조 하십시오. <xref:System.Media.SystemSounds>합니다.</span><span class="sxs-lookup"><span data-stu-id="382ba-104">For more information about system sounds, see <xref:System.Media.SystemSounds>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="382ba-105">예제</span><span class="sxs-lookup"><span data-stu-id="382ba-105">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="382ba-106">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="382ba-106">Compiling the Code</span></span>  
 <span data-ttu-id="382ba-107">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="382ba-107">This example requires:</span></span>  
  
-   <span data-ttu-id="382ba-108"><xref:System.Media?displayProperty=nameWithType> 네임스페이스에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="382ba-108">A reference to the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="382ba-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="382ba-109">See Also</span></span>  
 <xref:System.Media.SoundPlayer>  
 <xref:System.Media.SystemSounds>  
 [<span data-ttu-id="382ba-110">방법: Windows Form에서 경고음 재생</span><span class="sxs-lookup"><span data-stu-id="382ba-110">How to: Play a Beep from a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-play-a-beep-from-a-windows-form.md)  
 [<span data-ttu-id="382ba-111">방법: Windows Form에서 소리 재생</span><span class="sxs-lookup"><span data-stu-id="382ba-111">How to: Play a Sound from a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)
