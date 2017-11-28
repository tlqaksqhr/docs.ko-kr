---
title: ".NET Framework 3.0 또는.NET Framework 3.5 활동을 사용 하 여.NET Framework 4.5 워크플로에서"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6c53fd4c-5dd0-4fb4-ab6b-111302629548
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 19638043a5070451c331e0dccfff9641aa31174e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="using-a-net-framework-30-or-net-framework-35-activity-in-a-net-framework-45-workflow"></a><span data-ttu-id="5b2a4-102">.NET Framework 3.0 또는.NET Framework 3.5 활동을 사용 하 여.NET Framework 4.5 워크플로에서</span><span class="sxs-lookup"><span data-stu-id="5b2a4-102">Using a .NET Framework 3.0 or .NET Framework 3.5 Activity in a .NET Framework 4.5 Workflow</span></span>
<span data-ttu-id="5b2a4-103"><xref:System.Activities.Statements.Interop> 활동을 사용하면 [!INCLUDE[wf](../../../../includes/wf-md.md)] 워크플로 내에서 .NET Framework 3.0 [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] 활동을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b2a4-103">The <xref:System.Activities.Statements.Interop> activity allows you to run a .NET Framework 3.0 [!INCLUDE[wf](../../../../includes/wf-md.md)] activity within a [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] workflow.</span></span> <span data-ttu-id="5b2a4-104">이 샘플에서는 <xref:System.Activities.Statements.Interop> 활동을 사용하여 문자열을 사용자 지정 [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] 활동에 인수로 전달하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5b2a4-104">This sample demonstrates how to use the <xref:System.Activities.Statements.Interop> activity to pass a string as an argument to a custom [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] activity.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="5b2a4-105">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="5b2a4-105">To use this sample</span></span>  
  
1.  <span data-ttu-id="5b2a4-106">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]을 사용하여 SimpleInterop.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5b2a4-106">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the SimpleInterop.sln solution file.</span></span>  
  
2.  <span data-ttu-id="5b2a4-107">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="5b2a4-107">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="5b2a4-108">Ctrl+F5를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5b2a4-108">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5b2a4-109">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b2a4-109">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5b2a4-110">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="5b2a4-110">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5b2a4-111">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="5b2a4-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5b2a4-112">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b2a4-112">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Migration\SimpleInterop`  
  
## <a name="see-also"></a><span data-ttu-id="5b2a4-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5b2a4-113">See Also</span></span>
