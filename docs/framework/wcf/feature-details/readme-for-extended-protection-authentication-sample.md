---
title: "인증에 대한 확장된 보호 ReadMe 샘플 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 80bf2e97-398d-4db5-9040-d96478a2ccab
caps.latest.revision: 3
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 3
---
# 인증에 대한 확장된 보호 ReadMe 샘플
확장된 보호는 공격자가 클라이언트의 자격 증명을 가로채서 클라이언트가 액세스하려는 서버의 보호된 리소스에 액세스하는 데 사용하는 MITM\(Man\-In\-The\-Middle, 메시지 가로채기\) 공격을 방지하기 위한 보안 이니셔티브입니다.  
  
 자세한 내용은 [인증에 대한 확장된 보호 개요](../../../../docs/framework/wcf/feature-details/extended-protection-for-authentication-overview.md)을 참조하십시오.  
  
> [!NOTE]
>  이 샘플은 IIS에서 호스팅하는 경우에만 작동하며,HTTPS를 지원하지 않는 Visual Studio 개발 서버에서는 작동하지 않습니다.  
  
## 샘플 설치, 빌드 및 실행  
  
1.  컴퓨터의 프로그램 추가\/제거 \-\> Windows 기능에서 IIS를 설치합니다.  
  
2.  Windows 기능: 인터넷 정보 서비스 \-\> World Wide Web 서비스 \-\> 보안 \-\> Windows 인증에서 Windows 인증을 설정합니다.  
  
3.  Windows 기능: Microsoft .NET Framework 3.5.1 \-\> Windows Communication Foundation HTTP 활성화에서 HTTP 활성화를 설정합니다.  
  
4.  이 샘플을 사용하려면 클라이언트에서 서버와의 보안 채널을 설정해야 하므로, IIS\(인터넷 정보 서비스\) 관리자에서 설치할 수 있는 서버 인증서가 있어야 합니다.  
  
    1.  기능 보기 탭에서 IIS 관리자\-\> 서버 인증서를 엽니다.  
  
    2.  이 샘플을 테스트하기 위해 자체 서명된 인증서를 만들 수 있습니다.Internet Explorer에서 인증서가 안전하지 않다는 메시지가 표시되지 않도록 하려면 인증서를 신뢰할 수 있는 인증서 루트 인증 기관 저장소에 설치하면 됩니다.  
  
5.  기본 웹 사이트의 작업 창으로 이동하여사이트 편집 \-\> 바인딩을 클릭합니다.그런 다음 HTTPS 유형이 없으면 포트 번호 443으로 추가하고 위 단계에서 만든 SSL 인증서를 할당합니다.  
  
6.  서비스를 빌드합니다.그러면 프로젝트 속성에 지정된 빌드 후 작업을 통해 IIS에 가상 디렉터리가 자동으로 만들어지며, 필요에 따라 웹에서 호스팅할 서비스에 대해 dll, .svc 및 config 파일이 복사됩니다.  
  
7.  IIS 관리자를 열고앞 단계에서 만든 가상 디렉터리\(ExtendedProtection\)를 마우스 오른쪽 단추로 클릭한 다음 응용 프로그램으로 변환을 선택합니다.  
  
8.  IIS 관리자에서 이 가상 디렉터리에 대한 인증 모듈을 열고 Windows 인증을 사용하도록 설정합니다.  
  
9. 샘플에서는 해당 ExtendedProtection 설정이 항상으로 설정되므로, 이 가상 디렉터리에 대해 Windows 인증의 고급 설정을 열고 필수로 설정합니다.  
  
10. 브라우저 창에서 URL에 액세스해 서비스를 테스트할 수 있습니다.다중 컴퓨터 구성에서 이 URL에 액세스하려면 들어오는 모든 HTTP 및 HTTPS 연결에 대해 방화벽이 열려 있는지 확인하십시오.  
  
11. 클라이언트 구성 파일을 열고 \<client\> \- \<endpoint\> \- address 특성에 대해 전체 컴퓨터 이름을 제공합니다. \<\<\>\>full\_machine\_name을 전체 컴퓨터 이름으로 바꾸면 됩니다.  
  
12. 클라이언트를 실행합니다.클라이언트가 보안 채널을 설정하고 자동으로 확장된 보호를 사용하여 서비스와 통신합니다.