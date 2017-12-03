---
title: "XAMLX의 지속적 지연"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: efc38df4-2d34-453c-8e59-2c21d1307354
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7396c5ca2119dcf096036695233d5c89a3f014f7
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="durable-delay-in-xamlx"></a>XAMLX의 지속적 지연
이 샘플에서는 지속적 지연을 사용하는 방법을 보여 줍니다. 지속적 지연은 지연되는 동안 워크플로를 영구적인 장치에 유지하는 지연입니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelayXamlx`  
  
## <a name="discussion"></a>토론  
 샘플 워크플로에는 로컬 파일에 대해 지연으로 구분되는 두 메시지가 포함되어 있습니다. 지연이 트리거되면 워크플로가 언로드된 다음 메모리에 다시 로드되기 전에 워크플로 인스턴스 저장소에서 5초 동안 기다립니다.  
  
 .xamlx 파일은 [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]에서 호스트되는 워크플로 서비스입니다. [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]에서는 워크플로 서비스 호스트를 사용하여 워크플로를 호스트하는 Cassini를 사용합니다.  
  
 워크플로 서비스는 워크플로를 호스트하는 외에도 워크플로 인스턴스를 로드하거나 언로드하는 등의 방법으로 관리합니다. 워크플로 서비스 호스트에서 [!INCLUDE[wf](../../../../includes/wf-md.md)] 정의의 인스턴스를 시작하려면 워크플로의 <xref:System.ServiceModel.Activities.Receive> 활동에 메시지를 보내는 클라이언트를 설정합니다. 이 <xref:System.ServiceModel.Activities.Receive>의 <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> 속성은 `true`로 설정되어 있으므로, 메시지를 받으면 워크플로의 새 인스턴스를 만들 수 있습니다.  
  
 초기화하는 동안 인스턴스 언로드 동작이 구성 파일에 추가됩니다. 이 구성 파일은 인스턴스를 지속성 저장소(데이터베이스)에 언로드해야 하는 워크플로 서비스 호스트에 지정되어 있습니다. 이 샘플의 경우 지연이 트리거되어 워크플로가 유휴 상태가 되는 직후 인스턴스를 언로드합니다.  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 명령 프롬프트를 엽니다.  
  
2.  DurableDelayXamlx\CS 폴더로 이동합니다.  
  
3.  Setup.cmd.를 실행합니다.  
  
4.  관리자 권한으로 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 실행합니다.  
  
5.  DurableDelayXamlx.sln 솔루션 파일을 엽니다.  
  
6.  **솔루션 탐색기**솔루션을 마우스 오른쪽 단추로 클릭 하 고 선택 **속성**합니다.  
  
7.  선택 **여러 개의 시작 프로젝트** 두 프로젝트 설정 하 고 **시작**합니다.  
  
8.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
9. Ctrl+F5를 눌러 솔루션을 실행합니다.  
  
#### <a name="to-uninstall-this-sample"></a>이 샘플을 제거하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 명령 프롬프트를 엽니다.  
  
2.  DurableDelayXamlx\CS 폴더로 이동합니다.  
  
3.  Cleanup.cmd를 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelayXamlX`
