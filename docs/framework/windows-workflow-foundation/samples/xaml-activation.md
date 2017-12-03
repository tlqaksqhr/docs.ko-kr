---
title: XAML Activation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 486760e2-bb10-4ed5-8c02-fe7472498d2d
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9ac691e3d24e3526b43a6818fbe6bbb33a3375a7
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="xaml-activation"></a>XAML Activation
이 샘플에서는 IIS에서 선언적 워크플로를 호스트하는 방법을 보여 줍니다. 샘플은 하나의 작업이 있는 `EchoService`라는 기본 워크플로입니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 다운로드 페이지로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\XAMLActivation`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 XAMLActivation.sln 솔루션을 엽니다.  
  
2.  키를 눌러 솔루션을 빌드합니다 **F5**합니다.  
  
3.  WcfTestClient.exe를 실행합니다. 명령 프롬프트에서 다음과 같이 입력합니다.  
  
    1.  cd %SystemDrive%\Program Files\Microsoft Visual Studio 10.0\Common7\IDE  
  
    2.  WcfTestClient.exe를 실행합니다.  
  
4.  Ctrl+Shift+A를 누르고 서비스 주소를 http://localhost:56133/Service.xamlx로 설정하여 WcfTestClient.exe에 대한 서비스 주소를 설정합니다.  
  
5.  Echo 작업을 수행하여 서비스를 테스트합니다.  
  
6.  관리자 권한으로 명령 프롬프트에서 DeployToIIS.Bat를 사용하여 IIS에 서비스를 배포합니다.  
  
7.  클라이언트에서 서비스 주소를 http://localhost/XAMLActivation/Service.xamlx로 업데이트하고 WcfTestClient.exe를 사용하여 서비스를 다시 테스트합니다.
