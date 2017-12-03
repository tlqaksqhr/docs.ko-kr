---
title: "Using AsyncOperationContext in an Activity 샘플"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0888a0bd-d227-4c00-ad6a-b654a01740e8
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d5fce0160f98b5af5476b5e647763d79e94fb4e3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="using-asyncoperationcontext-in-an-activity-sample"></a>Using AsyncOperationContext in an Activity 샘플
이 샘플에서는 <xref:System.Activities.CodeActivity>를 사용하여 워크플로 외부에서 비동기적으로 작업을 수행하는 사용자 지정 <xref:System.Activities.AsyncCodeActivityContext>를 개발하는 방법을 보여 줍니다.  
  
## <a name="sample-details"></a>샘플 세부 정보  
 샘플 활동에서는 <xref:System.IO.FileStream.BeginWrite%2A> 클래스의 <xref:System.IO.FileStream.EndWrite%2A> 및 <xref:System.IO.FileStream> 메서드를 사용하여 비동기적으로 파일에 데이터를 씁니다. 여기에서 사용되는 패턴은 다른 비동기 메서드에도 사용할 수 있습니다. 비동기 작업이 실행 중일 때 워크플로의 다른 활동을 실행할 수는 있지만 워크플로를 유지할 수는 없습니다.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 Async.sln 샘플 솔루션을 엽니다.  
  
2.  솔루션을 빌드하고 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\Async`