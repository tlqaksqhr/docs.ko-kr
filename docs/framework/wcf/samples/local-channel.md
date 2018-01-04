---
title: "로컬 채널"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fa1917a4-f701-4e82-a439-14a16282c7cc
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1298b4b96006837f0634040c5c615adfa3a1a11b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="local-channel"></a>로컬 채널
로컬 채널은 동일한 응용 프로그램 도메인 내에서 통신하는 데 사용되는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 전송 채널입니다. 로컬 채널은 클라이언트와 서비스가 동일한 응용 프로그램 도메인에서 실행 중이고 일반적인 WCF 채널 스택(메시지의 serialization 및 deserialization)의 오버헤드를 방지해야 하는 경우에 유용합니다.  
  
## <a name="demonstrates"></a>세부 항목  
 로컬 채널  
  
## <a name="discussion"></a>토론  
 이 샘플은 다음의 두 프로젝트 파일로 구성되어 있습니다.  
  
-   **LocalChannel**: 현재 응용 프로그램 도메인 내의 로컬 채널의 프로그래밍 방식으로 표현 합니다. 이 프로젝트에서 보내기 구성 요소는 메시지를 메모리 내 큐에 넣고 받기 구성 요소는 메시지를 큐에서 꺼내 해당 메시지를 받습니다.  
  
-   **ClientAndService**:이 프로젝트는 콘솔 응용 프로그램에 서비스를 호스트 한 다음 같은 응용 프로그램 도메인 내에서 서비스를 호출 하는 클라이언트를 실행 합니다.  
  
 로컬 채널 디자인은 채널 스택과 serialization 프로세스를 모두 건너뛰므로 속도가 빨라집니다. 로컬 전송 채널은 클라이언트의 서비스 호출을 서비스로 전송하고 값을 클라이언트에 다시 반환하는 큐를 사용하여 구현됩니다. 매개 변수 및 반환 값을 serialize하는 대신 이 샘플에서는 해당 개체를 복사합니다.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  LocalChannel 솔루션을 빌드하고 실행합니다.  
  
2.  서비스 호스트가 시작되고 클라이언트가 로컬 채널을 사용하여 서비스를 호출합니다. 콘솔 창에 서비스 호출 결과가 표시됩니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\LocalChannel`
