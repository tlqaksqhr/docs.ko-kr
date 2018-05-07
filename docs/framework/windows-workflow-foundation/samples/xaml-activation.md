---
title: XAML Activation
ms.date: 03/30/2017
ms.assetid: 486760e2-bb10-4ed5-8c02-fe7472498d2d
ms.openlocfilehash: 8621b0ea7b390c81e76ac7eeedb0b547b44320d7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="xaml-activation"></a>XAML Activation
이 샘플에서는 IIS에서 선언적 워크플로를 호스트하는 방법을 보여 줍니다. 샘플은 하나의 작업이 있는 `EchoService`라는 기본 워크플로입니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 다운로드 페이지로 이동 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플입니다. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\XAMLActivation`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 XAMLActivation.sln 솔루션을 엽니다.  
  
2.  키를 눌러 솔루션을 빌드합니다 **F5**합니다.  
  
3.  WcfTestClient.exe를 실행합니다. 명령 프롬프트에서 다음과 같이 입력합니다.  
  
    1.  cd %SystemDrive%\Program Files\Microsoft Visual Studio 10.0\Common7\IDE  
  
    2.  WcfTestClient.exe를 실행합니다.  
  
4.  CTRL + SHIFT + A를 하는 서비스 주소 설정 하 여 WcfTestClient.exe에 서비스의 주소를 설정 http://localhost:56133/Service.xamlx합니다.  
  
5.  Echo 작업을 수행하여 서비스를 테스트합니다.  
  
6.  관리자 권한으로 명령 프롬프트에서 DeployToIIS.Bat를 사용하여 IIS에 서비스를 배포합니다.  
  
7.  클라이언트에 서비스 주소 http://localhost/XAMLActivation/Service.xamlx 하 고 WcfTestClient.exe를 사용 하 여 다시 서비스를 테스트 합니다.
