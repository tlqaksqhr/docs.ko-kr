---
title: "상호 관련된 계산기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c365166e-6552-49a4-bf17-9f4e597d4d41
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f6296ecb5c708d344624cac6e24247d2163fd66b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="correlated-calculator"></a>상호 관련된 계산기
이 샘플에서는 디자이너에서 메시지의 매개 변수를 기준으로 내용 기반 상관 관계에 <xref:System.ServiceModel.Activities.Receive> 및 <xref:System.ServiceModel.Activities.SendReply> 메시징 활동을 사용하는 방법을 보여 줍니다. 이 시나리오에서는 계산이 작업이 병렬 호송됩니다. 인스턴스 및 `CalculatorId` 기반의 상관 관계는 둘 다 워크플로에 첫 메시지를 보낼 때 만들어지며, `CalculatorId`가 동일한 후속 메시지는 Reset 작업을 호출할 때까지 해당 인스턴스에 디스패치됩니다. 클라이언트는 서비스와 통신하기 위해 코드 기반 클라이언트 프록시를 사용하는 WPF 응용 프로그램으로 구현됩니다.  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  높은 권한으로 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 시작하고 For.sln 솔루션 파일을 엽니다.  
  
    1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]이 들어 있는 폴더로 이동합니다.  
  
    2.  Devenv.exe를 마우스 오른쪽 단추로 클릭 하 고 선택 **관리자 권한으로 실행**합니다.  
  
2.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 CorrelatedCalculator.sln 솔루션 파일을 엽니다.  
  
3.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
4.  서비스 프로젝트를 실행하려면 Ctrl+F5를 누릅니다.  
  
5.  서버가 메시지를 수신할 준비가 되어 있으면 솔루션 탐색기에서 클라이언트 프로젝트를 마우스 오른쪽 단추로 클릭하고 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\CorellatedCalculator`