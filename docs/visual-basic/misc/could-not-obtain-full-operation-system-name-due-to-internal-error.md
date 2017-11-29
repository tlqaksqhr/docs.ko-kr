---
title: "내부 오류로 인해 전체 작업 시스템 이름을 가져올 수 없습니다."
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrDiagnosticInfo_FullOSName
ms.assetid: f69da02b-eb9a-4284-bb9e-3025517ae6c1
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 65796c41d2a9fbd03517e7b15bc6b566ba4364fb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="could-not-obtain-full-operation-system-name-due-to-internal-error"></a><span data-ttu-id="841d9-102">내부 오류로 인해 전체 작업 시스템 이름을 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="841d9-102">Could not obtain full operation system name due to internal error</span></span>
<span data-ttu-id="841d9-103">내부 오류로 인해 전체 작업 시스템 이름을 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="841d9-103">Could not obtain full operation system name due to internal error.</span></span> <span data-ttu-id="841d9-104">이는 현재 컴퓨터에 존재하지 않는 WMI에 의해 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="841d9-104">This might be caused by WMI not existing on the current machine.</span></span>  
  
 <span data-ttu-id="841d9-105">`My.Computer.Info.OSFullName` 속성 호출이 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="841d9-105">A call to the `My.Computer.Info.OSFullName` property failed.</span></span> <span data-ttu-id="841d9-106">현재 컴퓨터에 WMI(Windows Management Instrumentation)가 설치되지 않아서 이 오류가 발생했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="841d9-106">A possible cause for this failure is if Windows Management Instrumentation (WMI) is not installed on the current computer.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="841d9-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="841d9-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="841d9-108">`Try...Catch` 속성을 호출하는 주변에 `My.Computer.Info.OSFullName` 블록을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="841d9-108">Add a `Try...Catch` block around the call to the `My.Computer.Info.OSFullName` property.</span></span>  
  
2.  <span data-ttu-id="841d9-109">WMI 및 설치 하는 방법에 대 한 자세한 내용은으로 이동한 다음 "Windows Management Instrumentation Core"를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="841d9-109">For more information about WMI and how to install it, go to  and search for "Windows Management Instrumentation Core".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="841d9-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="841d9-110">See Also</span></span>  
 [<span data-ttu-id="841d9-111">My.Computer.Info.OSFullName 속성</span><span class="sxs-lookup"><span data-stu-id="841d9-111">My.Computer.Info.OSFullName Property</span></span>](http://msdn.microsoft.com/en-us/b3b0fbd1-4dc5-428a-ad04-0d9fc9c2a9be)  
 [<span data-ttu-id="841d9-112">예외 및 Visual Basic에서의 오류 처리</span><span class="sxs-lookup"><span data-stu-id="841d9-112">Exception and Error Handling in Visual Basic</span></span>](http://msdn.microsoft.com/en-us/3e351e73-cf23-40ab-8b60-05794160529e)  
 [<span data-ttu-id="841d9-113">Try...Catch...Finally 문</span><span class="sxs-lookup"><span data-stu-id="841d9-113">Try...Catch...Finally Statement</span></span>](../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
