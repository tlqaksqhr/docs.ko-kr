---
title: "방법: Visual Basic에서 연결 상태 확인"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Web connections [Visual Basic]
- IsAvailable property [Visual Basic], about IsAvailable
- connections [Visual Basic], checking status
- connection status [Visual Basic]
ms.assetid: 4d9ee8ab-9a6f-4279-ace4-b75afc976a74
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 31a8bb72e3b5cdc5ddee626a377c70640facb81d
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-check-connection-status-in-visual-basic"></a><span data-ttu-id="aae9f-102">방법: Visual Basic에서 연결 상태 확인</span><span class="sxs-lookup"><span data-stu-id="aae9f-102">How to: Check Connection Status in Visual Basic</span></span>
<span data-ttu-id="aae9f-103"><xref:Microsoft.VisualBasic.Devices.Network.IsAvailable> 속성은 컴퓨터에 작동하는 네트워크 또는 인터넷 연결이 있는지 확인하는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aae9f-103">The <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable> property can be used to determine whether the computer has a working network or Internet connection.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-check-whether-a-computer-has-a-working-connection"></a><span data-ttu-id="aae9f-104">컴퓨터에 작동하는 연결이 있는지 확인하려면</span><span class="sxs-lookup"><span data-stu-id="aae9f-104">To check whether a computer has a working connection</span></span>  
  
-   <span data-ttu-id="aae9f-105">`IsAvailable` 속성이 `True` 또는 `False`인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="aae9f-105">Determine whether the `IsAvailable` property is `True` or `False`.</span></span> <span data-ttu-id="aae9f-106">다음 코드에서는 속성의 상태를 확인하고 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="aae9f-106">The following code checks the property's status and reports it:</span></span>  
  
     [!code-vb[VbResourceTasks#3](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-check-connection-status_1.vb)]  
  
     <span data-ttu-id="aae9f-107">이 코드 예제는 IntelliSense 코드 조각으로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aae9f-107">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="aae9f-108">코드 조각 선택에서는 **연결 및 네트워킹**에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aae9f-108">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="aae9f-109">자세한 내용은 [코드 조각](/visualstudio/ide/code-snippets)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aae9f-109">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aae9f-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aae9f-110">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=nameWithType>  
 <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable>
