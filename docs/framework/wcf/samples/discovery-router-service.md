---
title: "검색 라우터 서비스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d30af47-b24f-40e5-833a-24d77125c9e6
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 66ff9d760ee59ef7a08f38826437b29077bc68d5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="discovery-router-service"></a>검색 라우터 서비스
이 샘플에서는 검색 메시지를 다른 끝점에 전달하는 방법을 보여 줍니다.  
  
## <a name="demonstrates"></a>세부 항목  
 검색 라우팅  
  
## <a name="discussion"></a>토론  
 클라이언트에서 프록시를 사용하여 서비스를 찾으려고 하며 프록시에서는 이러한 서비스를 인식하지 못하지만 다른 프록시는 인식하는 경우에 검색 라우팅이 유용합니다. 이 프록시에서는 이 클라이언트의 검색 패킷을 두 번째 프록시에 전달할 수 있습니다. 두 번째 프록시에서는 서비스를 찾고 원래 클라이언트에 응답을 반환할 수 있습니다.  
  
 이 샘플의 클라이언트에서는 검색 라우팅 구성 요소에 메시지를 보냅니다. 이 메시지는 검색 라우터의 특정 끝점에 보내집니다. 그런 다음 라우터에서 해당 메시지를 UDP 멀티캐스트 끝점에 전달합니다. 프로브 메시지는 멀티캐스트 끝점으로 이동하며 UDP 멀티캐스트 주소에서 수신 대기하는 서비스는 해당 검색 라우터에 응답합니다. 검색 라우터에서는 응답을 수집하여 클라이언트로 다시 보냅니다.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  샘플을 빌드합니다.  
  
2.  DiscoveryRouter 실행 파일을 실행합니다.  
  
3.  빌드 디렉터리에서 서비스 실행 파일을 실행합니다.  
  
4.  클라이언트 실행 파일을 실행합니다. 그러면 클라이언트에서는 서비스를 찾습니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryRouter`
