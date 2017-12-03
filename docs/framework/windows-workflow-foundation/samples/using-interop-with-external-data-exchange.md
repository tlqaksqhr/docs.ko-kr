---
title: "외부 데이터 교환과 함께 Interop 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 96f6fe26-5305-494f-9119-7748e0c4b3fa
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f62d5a468e3730ec4f636d57cb9d0c6c3973a8d3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="using-interop-with-external-data-exchange"></a>외부 데이터 교환과 함께 Interop 사용
<xref:System.Activities.Statements.Interop> 활동을 사용하여 [!INCLUDE[wf](../../../../includes/wf-md.md)] 및 [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)](WF3)에서 [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)]의 활동과 [!INCLUDE[wf2](../../../../includes/wf2-md.md)](WF4)에서 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]의 워크플로를 실행할 수 있습니다. 이 샘플에서는 WF4 워크플로 서비스의 <xref:System.Workflow.Activities.ExternalDataExchangeService> 활동을 사용하여 <xref:System.Activities.Statements.Interop> 및 메서드 호출과 이벤트 처리를 위한 해당 사용자 지정 활동을 사용하는 WF3 워크플로를 구성하고 실행하는 방법을 보여 줍니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Migration\ExternalDataExchange`  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 ExternalDataExchange.sln 파일을 엽니다.  
  
2.  Ctrl+Shift+B를 눌러 샘플을 빌드합니다.  
  
3.  F5 키를 눌러 샘플을 실행합니다.
