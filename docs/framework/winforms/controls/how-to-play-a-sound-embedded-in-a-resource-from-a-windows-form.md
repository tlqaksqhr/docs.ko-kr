---
title: "방법: Windows Form에서 리소스에 포함된 소리 재생"
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
- sounds [Windows Forms], playing from resources
- resources [Windows Forms], playing sounds
- playing sounds [Windows Forms], from resources
- SoundPlayer class [Windows Forms], playing sounds from resources
ms.assetid: 7d148bb6-8a1e-47d7-a08d-35828d2e688f
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 90b0c2748960443c0d63d22b33566ebcb2b4545b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-play-a-sound-embedded-in-a-resource-from-a-windows-form"></a><span data-ttu-id="43d9f-102">방법: Windows Form에서 리소스에 포함된 소리 재생</span><span class="sxs-lookup"><span data-stu-id="43d9f-102">How to: Play a Sound Embedded in a Resource from a Windows Form</span></span>
<span data-ttu-id="43d9f-103">사용할 수는 <xref:System.Media.SoundPlayer> 포함된 리소스에서 소리를 재생 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="43d9f-103">You can use the <xref:System.Media.SoundPlayer> class to play a sound from an embedded resource.</span></span>  
  
## <a name="example"></a><span data-ttu-id="43d9f-104">예</span><span class="sxs-lookup"><span data-stu-id="43d9f-104">Example</span></span>  
 [!code-csharp[System.Windows.Forms.Sound#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Sound/CS/soundtestform.cs#10)]
 [!code-vb[System.Windows.Forms.Sound#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Sound/VB/soundtestform.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="43d9f-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="43d9f-105">Compiling the Code</span></span>  
 <span data-ttu-id="43d9f-106">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="43d9f-106">This example requires:</span></span>  
  
 <span data-ttu-id="43d9f-107">가져오기는 <xref:System.Media?displayProperty=nameWithType> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="43d9f-107">Importing the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>  
  
 <span data-ttu-id="43d9f-108">프로젝트에 사운드 파일을 포함된 리소스로 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="43d9f-108">Including the sound file as an embedded resource in your project.</span></span>  
  
 <span data-ttu-id="43d9f-109">"\<AssemblyName>"을 사운드 파일이 포함된 어셈블리의 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="43d9f-109">Replacing "\<AssemblyName>" with the name of the assembly in which the sound file is embedded.</span></span> <span data-ttu-id="43d9f-110">".dll" 접미사는 포함하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="43d9f-110">Do not include the ".dll" suffix.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43d9f-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="43d9f-111">See Also</span></span>  
 <xref:System.Media.SoundPlayer>  
 [<span data-ttu-id="43d9f-112">방법: Windows Form에서 소리 재생</span><span class="sxs-lookup"><span data-stu-id="43d9f-112">How to: Play a Sound from a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)  
 [<span data-ttu-id="43d9f-113">방법: Windows Form에서 소리 재생 반복</span><span class="sxs-lookup"><span data-stu-id="43d9f-113">How to: Loop a Sound Playing on a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-loop-a-sound-playing-on-a-windows-form.md)
