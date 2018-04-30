---
title: 워크플로 관리 끝점 샘플
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3ac6e08f-c43d-4bb7-83c3-e3890a4dac03
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 558591cb645de9591fd0ac770061a5fb8825d21d
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2018
---
# <a name="workflow-management-endpoint-sample"></a>워크플로 관리 끝점 샘플
이 샘플에서는 워크플로 제어 끝점을 사용하여 로컬 및 원격으로 워크플로를 만들고 실행하는 방법과 제어 끝점을 호스트하고 제어 끝점을 호출하여 워크플로 인스턴스를 만들고 실행하는 클라이언트를 작성하는 방법을 보여 줍니다. 워크플로는 서비스가 아닙니다.  
  
 샘플의 서비스 쪽에서 워크플로가 WorkflowServiceHost로 호스트되고 WorkflowControlEndpoint가 추가되므로 클라이언트는 일시 중단, 시작 등의 제어 작업을 수행할 수 있습니다. 사용자 정의 CreationEndpoint도 추가되어 워크플로를 만들 수 있습니다. 그런 다음 서비스는 이러한 끝점을 사용하여 일시 중단 상태의 워크플로를 시작한 후 워크플로를 다시 시작합니다. 클라이언트는 동일한 작업을 클라이언트 코드에서 수행합니다. 이 대 한 자세한 내용은 참조 하십시오 인터페이스에 대 한 [워크플로 제어 끝점](../../../../docs/framework/wcf/feature-details/workflow-control-endpoint.md) 및 [하는 방법: IIS에서 서비스가 아닌 워크플로 호스팅](../../../../docs/framework/wcf/feature-details/how-to-host-a-non-service-workflow-in-iis.md)  
  
#### <a name="to-run-the-sample"></a>이 샘플을 실행하려면  
  
1.  관리자 권한으로 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 실행합니다.  
  
2.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 ManagementEndpoint.sln 솔루션을 엽니다.  
  
3.  솔루션을 빌드하려면 CTRL + SHIFT + B 키를 누르거나 선택 **솔루션 빌드** 에서 **빌드** 메뉴.  
  
4.  ManagementEndpoint.exe 응용 프로그램을 시작합니다.  
  
5.  Client.exe 응용 프로그램을 시작합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\ManagementEndpoint`