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
# <a name="using-a-net-framework-30-or-net-framework-35-activity-in-a-net-framework-45-workflow"></a>.NET Framework 3.0 또는.NET Framework 3.5 활동을 사용 하 여.NET Framework 4.5 워크플로에서
<xref:System.Activities.Statements.Interop> 활동 내에서.NET Framework 3.0 Windows WF (Workflow Foundation) 작업을 실행할 수 있습니다는 [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] 워크플로 합니다. 이 샘플에서는 <xref:System.Activities.Statements.Interop> 활동을 사용하여 문자열을 사용자 지정 [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] 활동에 인수로 전달하는 방법을 보여 줍니다.  
  
## <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]을 사용하여 SimpleInterop.sln 솔루션 파일을 엽니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
3.  Ctrl+F5를 눌러 솔루션을 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Migration\SimpleInterop`  
  
## <a name="see-also"></a>참고 항목
