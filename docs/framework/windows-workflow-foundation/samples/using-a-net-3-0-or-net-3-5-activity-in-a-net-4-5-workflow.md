---
title: .NET Framework 3.0 또는.NET Framework 3.5 활동을 사용 하 여.NET Framework 4.5 워크플로에서
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6c53fd4c-5dd0-4fb4-ab6b-111302629548
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 64c0e4b6e84f442b6e34f0cbd442ae04e2a9d0b5
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="using-a-net-framework-30-or-net-framework-35-activity-in-a-net-framework-45-workflow"></a><span data-ttu-id="06ba1-102">.NET Framework 3.0 또는.NET Framework 3.5 활동을 사용 하 여.NET Framework 4.5 워크플로에서</span><span class="sxs-lookup"><span data-stu-id="06ba1-102">Using a .NET Framework 3.0 or .NET Framework 3.5 Activity in a .NET Framework 4.5 Workflow</span></span>
<span data-ttu-id="06ba1-103"><xref:System.Activities.Statements.Interop> 활동 내에서.NET Framework 3.0 Windows WF (Workflow Foundation) 작업을 실행할 수 있습니다는 [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] 워크플로 합니다.</span><span class="sxs-lookup"><span data-stu-id="06ba1-103">The <xref:System.Activities.Statements.Interop> activity allows you to run a .NET Framework 3.0 Windows Workflow Foundation (WF) activity within a [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] workflow.</span></span> <span data-ttu-id="06ba1-104">이 샘플에서는 <xref:System.Activities.Statements.Interop> 활동을 사용하여 문자열을 사용자 지정 [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] 활동에 인수로 전달하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="06ba1-104">This sample demonstrates how to use the <xref:System.Activities.Statements.Interop> activity to pass a string as an argument to a custom [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] activity.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="06ba1-105">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="06ba1-105">To use this sample</span></span>  
  
1.  <span data-ttu-id="06ba1-106">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]을 사용하여 SimpleInterop.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="06ba1-106">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the SimpleInterop.sln solution file.</span></span>  
  
2.  <span data-ttu-id="06ba1-107">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="06ba1-107">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="06ba1-108">Ctrl+F5를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="06ba1-108">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="06ba1-109">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06ba1-109">The samples may already be installed on your machine.</span></span> <span data-ttu-id="06ba1-110">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="06ba1-110">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="06ba1-111">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="06ba1-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="06ba1-112">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06ba1-112">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Migration\SimpleInterop`  
  
## <a name="see-also"></a><span data-ttu-id="06ba1-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="06ba1-113">See Also</span></span>
