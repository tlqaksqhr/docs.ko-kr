---
title: "방법: WCF Activation 구성 요소 설치 및 구성 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "HTTP 활성화 [WCF]"
ms.assetid: 33a7054a-73ec-464d-83e5-b203aeded658
caps.latest.revision: 16
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# 방법: WCF Activation 구성 요소 설치 및 구성
이 항목에서는 [!INCLUDE[wv](../../../../includes/wv-md.md)]에서 HTTP 네트워크 프로토콜을 통해 통신하지 않는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스를 호스팅하도록 WAS라고도 하는 Windows Process Activation Service를 설정하는 데 필요한 단계에 대해 설명합니다.다음 단원에서는 이 구성 단계에 대해 간략히 설명합니다.  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 활성화 구성 요소를 설치하거나 설치를 확인합니다.  
  
-   HTTP가 아닌 프로토콜을 지원하도록 WAS를 구성합니다.다음 절차에서는 TCP 활성화를 위해 [!INCLUDE[wv](../../../../includes/wv-md.md)]를 구성합니다.  
  
 WAS를 설치 및 구성한 후, WAS를 사용하는 HTTP가 아닌 끝점이 노출되는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 해당 절차가 만들 수 있도록 [방법: WAS에서 WCF 서비스 호스팅](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md)를 참조하십시오.  
  
### WCF Non\-HTTP Activation 구성 요소를 설치하려면  
  
1.  **시작** 단추를 클릭한 다음 **제어판**을 클릭합니다.  
  
2.  **프로그램**을 클릭하고 **프로그램 및 기능**을 클릭합니다.  
  
3.  **작업** 메뉴에서 **Windows 기능 사용\/사용 안 함**을 클릭합니다.  
  
4.  [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] 노드를 찾아서 선택한 다음 확장합니다.  
  
5.  **WCF Non\-HTTP Activation 구성 요소** 상자를 선택하고 설정을 저장합니다.  
  
### TCP 활성화를 지원하도록 WAS를 구성하려면  
  
1.  net.tcp 활성화를 지원하려면 먼저 기본 웹 사이트를 net.tcp 포트에 바인딩해야 합니다.이 작업은 [!INCLUDE[iisver](../../../../includes/iisver-md.md)] 관리 도구 집합과 함께 설치되는 Appcmd.exe를 사용하여 수행할 수 있습니다.관리자 수준 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']  
    ```  
  
    > [!NOTE]
    >  이 명령은 줄 바꿈 없이 한 줄로 입력해야 합니다.이 명령은 임의의 호스트 이름을 사용하여 TCP 포트 808에서 수신 대기하는 기본 웹 사이트에 net.tcp 사이트 바인딩을 추가합니다.  
  
2.  사이트 내의 모든 응용 프로그램이 공통된 net.tcp 바인딩을 공유하지만 각 응용 프로그램에서 개별적으로 net.tcp 지원을 사용하도록 설정할 수 있습니다.응용 프로그램에 대해 net.tcp를 사용하도록 설정하려면 관리자 수준 명령 프롬프트에서 다음 명령을 실행합니다.  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set app   
    "Default Web Site/<WCF Application>" /enabledProtocols:http,net.tcp  
    ```  
  
    > [!NOTE]
    >  이 명령은 줄 바꿈 없이 한 줄로 입력해야 합니다.이 명령을 사용하면 http:\/\/localhost*\/\<WCF Application\>* 및 net.tcp:\/\/localhost\/*\<WCF Application\>* 둘 다를 사용하여 \/\<*WCF Application*\> 응용 프로그램에 액세스할 수 있습니다.  
  
     이 샘플에 대해 추가한 net.tcp 사이트 바인딩을 제거합니다.  
  
     편의를 위해 다음 두 단계는 샘플 디렉터리에 있는 RemoveNetTcpSiteBinding.cmd라는 배치 파일에서 구현됩니다.  
  
    1.  관리자 수준 명령 프롬프트 창에서 다음 명령을 실행하여 사용하도록 설정된 프로토콜 목록에서 net.tcp를 제거합니다.  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set app   
        "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http  
        ```  
  
        > [!NOTE]
        >  이 명령은 줄 바꿈 없이 한 줄로 입력해야 합니다.  
  
    2.  고급 명령 프롬프트 창에서 다음 명령을 실행하여 net.tcp 사이트 바인딩을 제거합니다.  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
        --bindings.[protocol='net.tcp',bindingInformation='808:*']  
        ```  
  
        > [!NOTE]
        >  이 명령은 줄 바꿈 없이 한 줄로 입력해야 합니다.  
  
### 사용하도록 설정된 프로토콜 목록에서 net.tcp를 제거하려면  
  
1.  사용하도록 설정된 프로토콜 목록에서 net.tcp를 제거하려면 관리자 수준 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http  
    ```  
  
    > [!NOTE]
    >  이 명령은 줄 바꿈 없이 한 줄로 입력해야 합니다.  
  
### net.tcp 사이트 바인딩을 제거하려면  
  
1.  net.tcp 사이트 바인딩을 제거하려면 관리자 수준 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
    -bindings.[protocol='net.tcp',bindingInformation='808:*']  
    ```  
  
    > [!NOTE]
    >  이 명령은 줄 바꿈 없이 한 줄로 입력해야 합니다.  
  
## 참고 항목  
 [TCP 활성화](../../../../docs/framework/wcf/samples/tcp-activation.md)   
 [MSMQ 활성화](../../../../docs/framework/wcf/samples/msmq-activation.md)   
 [NamedPipe 활성화](../../../../docs/framework/wcf/samples/namedpipe-activation.md)   
 [Windows Server AppFabric 호스팅 기능](http://go.microsoft.com/fwlink/?LinkId=201276)