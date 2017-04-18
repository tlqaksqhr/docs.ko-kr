---
title: "Windows Communication Foundation 샘플 실행 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: db8a83da-95c1-4a21-a9d2-48caeb6398ea
caps.latest.revision: 26
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 26
---
# Windows Communication Foundation 샘플 실행
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 샘플을 단일 컴퓨터 또는 다중 컴퓨터 구성에서 실행할 수 있습니다.  샘플은 단일 컴퓨터 구성에서 실행할 준비가 된 상태로 제공됩니다.  다중 컴퓨터 구성에서는 샘플의 구성 파일 설정을 수정해야 합니다.  다음 절차에서는 단일 컴퓨터 및 다중 컴퓨터 구성에서 샘플을 실행하는 방법에 대해 설명합니다.  IIS\(인터넷 정보 서비스\) 및 자체 호스팅 샘플에서 호스트되는 서비스에 적용되는 단계가 약간씩 다릅니다.  대부분의 샘플은 IIS에서 호스트됩니다. 이러한 샘플이 호스트되는 방법에 대한 자세한 내용은 샘플 추가 정보를 참조하세요.  
  
 [!INCLUDE[wv](../../../../includes/wv-md.md)]에서는 IIS에서 호스트되지 않는 샘플의 경우 Http.sys에 수신기를 등록하기 위해 상승된 권한이 필요합니다.  Httpcfg.exe를 사용하여 서비스가 수신 대기 중인 계정에 서비스의 수신 대기 주소를 등록하거나 관리자 권한으로 실행 중인 명령 프롬프트에서 서비스를 실행합니다.  
  
> [!NOTE]
>  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 샘플을 빌드하거나 실행하기 전에 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)를 수행했는지 확인합니다.  
  
### 단일 컴퓨터 구성에서 샘플을 실행하려면  
  
1.  서비스가 IIS에 의해 호스트될 경우 브라우저에서 http:\/\/localhost\/servicemodelsamples\/service.svc 주소를 입력하여 서비스에 액세스할 수 있는지 확인합니다.  확인 페이지가 응답으로 표시됩니다.  확인 페이지가 표시되지 않을 경우 [Troubleshooting Tips](http://msdn.microsoft.com/ko-kr/8787c877-5e96-42da-8214-fa737a38f10b)을 참조하세요.  
  
2.  서비스가 자체 호스트될 경우 언어별 폴더의 \\service\\bin에서 Service.exe를 실행합니다.  서비스 콘솔 창에 서비스 동작이 표시됩니다.  
  
3.  언어별 폴더의 \\client\\bin\\에서 Client.exe를 실행합니다.  클라이언트 콘솔 창에 클라이언트 동작이 표시됩니다.  
  
4.  클라이언트와 서비스가 통신할 수 없는 경우 [Troubleshooting Tips](http://msdn.microsoft.com/ko-kr/8787c877-5e96-42da-8214-fa737a38f10b)을 참조하세요.  
  
### 다중 컴퓨터 구성에서 샘플을 실행하려면  
  
1.  서비스가 IIS에서 호스트될 경우  
  
    1.  서비스 컴퓨터에서 ServiceModelSamples라는 가상 디렉터리를 만듭니다.  [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)에 포함된 Setupvroot.bat 배치 파일을 사용하여 디스크 디렉터리와 가상 디렉터리를 만들 수 있습니다.  
  
    2.  %SystemDrive%\\Inetpub\\wwwroot\\servicemodelsamples에서 서비스 컴퓨터의 ServiceModelSamples 가상 디렉터리로 서비스 프로그램 파일을 복사합니다.  \\bin 디렉터리에 파일을 포함해야 합니다.  
  
    3.  클라이언트 컴퓨터에서 브라우저를 사용하여 서비스에 액세스할 수 있는지 테스트합니다.  
  
     서비스가 자체 호스트될 경우  
  
    1.  서비스 컴퓨터에서 서비스 파일을 포함할 디렉터리를 만듭니다.  
  
    2.  언어별 폴더의 \\service\\bin\\ 폴더에서 서비스 컴퓨터로 서비스 프로그램 파일을 복사합니다.  
  
    3.  서비스 구성 파일에서 끝점 정의의 주소 값을 서비스의 새 주소와 일치하도록 변경합니다.  주소에서 "localhost"에 대한 참조를 정규화된 도메인 이름으로 바꿉니다.  
  
    4.  명령 프롬프트에서 Service.exe를 실행합니다.  
  
2.  언어별 폴더의 \\client\\bin\\ 폴더에서 클라이언트 컴퓨터로 클라이언트 프로그램 파일을 복사합니다.  
  
3.  끝점 주소를 설정합니다.  
  
    1.  서비스가 도메인 계정으로 실행 중이 아닌 경우 클라이언트 구성 파일을 열고 끝점 정의의 주소 값을 서비스의 새 주소와 일치하도록 변경합니다.  주소에서 "localhost"에 대한 참조를 정규화된 도메인 이름으로 바꿉니다.  
  
    2.  서비스가 도메인 계정으로 실행 중인 경우 서비스에 대해 Svcutil.exe를 실행하여 클라이언트 구성을 다시 생성합니다.  Svcutil.exe를 실행하는 방법에 대한 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]는 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)를 참조하세요.  샘플의 구성 파일 대신에 생성된 파일을 사용합니다.  생성된 구성 파일에는 추가 ID 정보가 포함되어 있고 기본 설정이기는 하지만 서비스 끝점에 연결하는 데 필요한 모든 설정이 포함되어 있습니다.  ID 정보에 대한 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]는 [서비스 ID 및 인증](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md) 및 [\<identity\>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)를 참조하세요.  
  
4.  클라이언트 컴퓨터의 명령 프롬프트에서 Client.exe를 실행합니다.  
  
### 서비스를 디버깅하려면  
  
1.  **빌드** 메뉴나 Ctrl\+Shift\+B를 사용하여 솔루션\(클라이언트 및 서비스 모두\)을 빌드합니다.  
  
2.  서비스가 IIS에서 호스트될 경우  
  
    1.  브라우저에서 http:\/\/localhost\/servicemodelsamples\/service.svc 주소를 입력하여 서비스를 활성화합니다.  
  
    2.  솔루션에서 **디버그** 메뉴를 선택하고 **프로세스에 연결** 메뉴 항목을 선택합니다.  
  
    3.  **모든 사용자의 프로세스 표시** 확인란을 선택합니다.  
  
    4.  디버깅할 호스트 작업자 프로세스 W3wp.exe를 선택합니다\(Windows XP에서는 select ASPNet\_wp.exe 선택\).  
  
3.  이제 서비스 코드에서 중단점을 설정하고 예외에 중단점을 사용하도록 설정할 수 있습니다.  
  
4.  클라이언트 프로젝트 항목을 마우스 오른쪽 단추로 클릭하고 **디버그**, **새 인스턴스 시작**을 차례로 선택합니다.  
  
### 샘플 실행 후 정리를 수행하려면  
  
-   보안을 위해 서비스가 IIS에서 호스트될 경우 샘플 사용이 끝나면 설정 단계에서 부여된 가상 디렉터리 정의와 사용 권한을 제거합니다.  
  
## 참고 항목  
 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)   
 [Running the Samples in a Workgroup and Across Machines](http://msdn.microsoft.com/ko-kr/a451a525-e7ce-452d-9da9-620221260113)   
 [Troubleshooting Tips](http://msdn.microsoft.com/ko-kr/8787c877-5e96-42da-8214-fa737a38f10b)