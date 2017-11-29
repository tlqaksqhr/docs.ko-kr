---
title: "방법: Windows Form에서 경고음 재생"
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
- sounds [Windows Forms], beep
- Windows Forms, sounds
- sounds [Windows Forms], playing
- forms [Windows Forms], sounds
- examples [Windows Forms], sounds
ms.assetid: 7ea5cded-4888-4f35-8f28-5cab1a55c973
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e214b368b65797100722cb41ad6a77ecd16424de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-play-a-beep-from-a-windows-form"></a><span data-ttu-id="8be49-102">방법: Windows Form에서 경고음 재생</span><span class="sxs-lookup"><span data-stu-id="8be49-102">How to: Play a Beep from a Windows Form</span></span>
<span data-ttu-id="8be49-103">이 예제에서는 런타임에 경고음을 재생합니다.</span><span class="sxs-lookup"><span data-stu-id="8be49-103">This example plays a beep at run time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8be49-104">예제</span><span class="sxs-lookup"><span data-stu-id="8be49-104">Example</span></span>  
  
```vb  
Public Sub OnePing()  
    Beep()  
End Sub  
```  
  
```csharp  
public void onePing()  
{  
    SystemSounds.Beep.Play();  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="8be49-105">C# 코드 샘플에서 재생할 소리에 의해 결정 됩니다는 <xref:System.Media.SystemSounds.Beep%2A> 시스템 소리 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8be49-105">The sound played in the C# code sample is determined by the <xref:System.Media.SystemSounds.Beep%2A> system sound setting.</span></span> <span data-ttu-id="8be49-106">자세한 내용은 <xref:System.Media.SystemSounds>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8be49-106">For more information, see <xref:System.Media.SystemSounds>.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8be49-107">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="8be49-107">Compiling the Code</span></span>  
 <span data-ttu-id="8be49-108">이 예제에 대 한 참조를 C#의 경우는 <xref:System.Media?displayProperty=nameWithType> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="8be49-108">For C#, this example requires  a reference to the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8be49-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8be49-109">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Interaction.Beep%2A>  
 <xref:System.Media.SoundPlayer>  
 [<span data-ttu-id="8be49-110">방법: Windows Form에서 시스템 소리 재생</span><span class="sxs-lookup"><span data-stu-id="8be49-110">How to: Play a System Sound from a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-play-a-system-sound-from-a-windows-form.md)  
 [<span data-ttu-id="8be49-111">방법: Windows Form에서 소리 재생</span><span class="sxs-lookup"><span data-stu-id="8be49-111">How to: Play a Sound from a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)
