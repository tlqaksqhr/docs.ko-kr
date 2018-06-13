---
title: HTTP 및 HTTPS 구성
ms.date: 03/30/2017
helpviewer_keywords:
- configuring HTTP [WCF]
ms.assetid: b0c29a86-bc0c-41b3-bc1e-4eb5bb5714d4
ms.openlocfilehash: ed9c7a444018e7c5e9ac00de82133cce633fac93
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2018
ms.locfileid: "33956488"
---
# <a name="configuring-http-and-https"></a>HTTP 및 HTTPS 구성
WCF 서비스 및 클라이언트는 HTTP 및 HTTPS를 통해 통신할 수 있습니다. HTTP/HTTPS 설정은 IIS(인터넷 정보 서비스)나 명령줄 도구를 사용하여 구성합니다. WCF 서비스가 IIS 아래에서 호스팅되거나 IIS에서 inetmgr.exe 도구를 사용하여 HTTP 또는 HTTPS 설정을 구성할 수 있는 경우입니다. WCF 서비스가 자체 호스팅되는 경우 HTTP 또는 HTTPS 설정은 명령줄 도구를 사용하여 구성됩니다.  
  
 최소한 URL 등록을 구성하고 서비스에서 사용할 URL의 방화벽 예외를 추가할 것입니다.  
  
 HTTP 설정 구성에 사용하는 도구는 컴퓨터에서 실행되고 있는 운영 체제에 따라 다릅니다.  
  
 실행 하는 경우 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 또는 [!INCLUDE[wxp](../../../../includes/wxp-md.md)]를 HttpCfg.exe 도구를 사용 합니다. [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]이 도구를 자동으로 설치합니다. 실행 하는 경우 [!INCLUDE[wxp](../../../../includes/wxp-md.md)]에서 도구를 다운로드할 수 있습니다 [Windows XP 서비스 팩 2 지원 도구](http://go.microsoft.com/fwlink/?LinkId=88606)합니다. 자세한 내용은 참조 [Httpcfg 개요](http://go.microsoft.com/fwlink/?LinkId=88605)합니다.  
  
 실행 하는 경우 [!INCLUDE[wv](../../../../includes/wv-md.md)] 또는 Windows 7의 경우 이러한 설정을 구성 하면 Netsh.exe 도구와 함께 합니다.  
  
## <a name="configuring-namespace-reservations"></a>네임스페이스 예약 구성  
 네임스페이스 예약은 HTTP URL 네임스페이스 일부에 대한 권한을 특정 사용자 그룹에 할당합니다. 예약을 통해 이러한 사용자에게 네임스페이스의 해당 부분에서 수신 대기하는 서비스를 만들 수 있는 권한을 제공합니다. 예약은 URL 접두사이며 예약이 예약 경로의 모든 하위 경로를 포함함을 의미합니다. 네임스페이스 예약은 와일드카드를 사용하는 두 가지 방법을 허용합니다. HTTP Server API 설명서에서 설명 하는 [와일드 카드가 포함 하는 네임 스페이스 클레임 확인 순서](http://go.microsoft.com/fwlink/?LinkId=94841)합니다.  
  
 실행 중인 응용 프로그램에서 비슷한 요청을 만들어 네임스페이스 등록을 추가할 수 있습니다. 등록과 예약은 네임스페이스의 특정 부분에 대해 충돌합니다. 예약에 제공 된 확인 순서에 따라 등록 보다 우선 순위가 있을 수 있습니다는 [와일드 카드가 포함 하는 네임 스페이스 클레임 확인 순서](http://go.microsoft.com/fwlink/?LinkId=94841)합니다. 이 경우 예약은 실행 중인 응용 프로그램이 요청을 수신하지 못하도록 차단합니다.  
  
### <a name="running-windows-xp-or-server-2003"></a>Windows XP 또는 Server 2003 실행  
 사용 된 `httpcfg.exe set urlacl` 네임 스페이스 예약을 변경 하는 명령입니다. [Windows 지원 도구 설명서](http://go.microsoft.com/fwlink/?LinkId=94840) Httpcfg.exe 도구에 대 한 구문에 설명 합니다. 네임스페이스 특정 부분에 대한 예약 권한을 수정하려면 네임스페이스 해당 부분에 대한 관리자 권한 또는 소유권이 필요합니다. 처음에 전체 HTTP 네임스페이스는 로컬 관리자에 속합니다.  
  
 다음은 `set urlacl` 옵션이 있는 Httpcfg 명령 구문을 보여 줍니다.  
  
```  
httpcfg set urlacl /u {http://URL:Port/ | https://URL:Port/} /aACL  
```  
  
 `/u` 매개 변수는 `set urlacl`을 사용하는 경우 필요합니다. 이 매개 변수는 만들고 있는 예약에 대한 레코드 키 역할을 수행하는 정규화된 URL이 포함된 문자열을 사용합니다.  
  
 `/a` 매개 변수도 `set urlacl`을 사용하는 경우 필요합니다. 이 매개 변수는 SDDL(Security Descriptor Definition Language) 문자열 형식의 ACL(액세스 제어 목록)이 포함된 문자열을 사용합니다.  
  
 다음에서는 이 명령을 사용하는 예를 보여 줍니다.  
  
```  
httpcfg.exe set urlacl /u http://myhost:8000/ /a "O:AOG:DAD:(A;;RPWPCCDCLCSWRCWDWOGA;;;S-1-0-0)"  
```  
  
### <a name="running-windows-vista-windows-server-2008-r2-or-windows-7"></a>Windows Vista, Windows Server 2008 R2 또는 Windows 7 실행  
 [!INCLUDE[wv](../../../../includes/wv-md.md)], Windows Server 2008 R2 또는 Windows 7에서 실행 중인 경우에는 Netsh.exe 도구를 사용합니다. 다음에서는 이 명령을 사용하는 예를 보여 줍니다.  
  
```  
netsh http add urlacl url=http://+:80/MyUri user=DOMAIN\user  
```  
  
 이 명령은 도메인\사용자 계정의 지정된 URL 네임스페이스에 대한 URL 예약을 추가합니다.  자세한 내용은 netsh 명령 형식을 사용 하 여 누릅니다 명령 프롬프트에서 "netsh http add urlacl"을 입력 합니다.  
  
## <a name="configuring-a-firewall-exception"></a>방화벽 예외 구성  
 HTTP에서 통신하는 WCF 서비스를 자체 호스팅하는 경우 특정 URL을 사용하여 인바운드 연결을 허용하려면 예외를 방화벽 구성에 추가해야 합니다. 자세한 내용은 참조 [(Windows 7) Windows 방화벽에서 포트 열기](http://go.microsoft.com/fwlink/?LinkId=239961)  
  
## <a name="configuring-ssl-certificates"></a>SSL 인증서 구성  
 SSL(Secure Sockets Layer) 프로토콜은 클라이언트 및 서버에서 인증서를 사용하여 암호화 키를 저장합니다. 서버는 클라이언트가 서버 ID를 확인할 수 있도록 연결된 경우 SSL 인증서를 제공합니다. 또한 서버는 양쪽 연결에 상호 인증을 제공하기 위해 클라이언트로부터 인증서를 요청할 수 있습니다.  
  
 인증서는 연결 IP 주소 및 연결 포트 번호에 따라 중앙 저장소에 저장됩니다. 특수 IP 주소 0.0.0.0은 로컬 시스템의 IP 주소와 일치합니다. 인증서 저장소는 경로에 따라 URL을 구분하지 않습니다. IP 주소와 포트 조합이 같은 서비스는 서비스의 URL 경로가 다른 경우에도 인증서를 공유해야 합니다.  
  
 단계별 지침은 참조 하십시오. [하는 방법: SSL 인증서로 포트 구성](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)합니다.  
  
## <a name="configuring-the-ip-listen-list"></a>IP 수신 대기 목록 구성  
 사용자가 URL을 등록하면 HTTP Server API는 IP 주소 및 포트에만 바인딩됩니다. 기본적으로 HTTP Server API는 모든 시스템 IP 주소에 대한 URL의 포트에 바인딩됩니다. HTTP Server API를 사용하지 않는 응용 프로그램이 이전에 해당 IP 주소 및 포트 조합에 바인딩된 경우 충돌이 발생합니다. IP 수신 대기 목록을 WCF 서비스를 컴퓨터의 IP 주소 중 일부에 대 한 포트를 사용 하는 응용 프로그램과 함께 사용할 수 있습니다. IP 수신 대기 목록에 항목이 포함된 경우 HTTP Server API는 목록에서 지정한 IP 주소에만 바인딩됩니다. IP 수신 대기 목록을 수정하려면 관리자 권한이 필요합니다.  
  
### <a name="running-windows-xp-or-server-2003"></a>Windows XP 또는 Server 2003 실행  
 다음 예제와 같이 httpcfg 도구를 사용하여 IP 수신 대기 목록을 수정합니다. [Windows 지원 도구 설명서](http://go.microsoft.com/fwlink/?LinkId=94840) httpcfg.exe 도구에 대 한 구문에 설명 합니다.  
  
```  
httpcfg.exe set iplisten -i 0.0.0.0:8000  
```  
  
### <a name="running-windows-vista-or-windows-7"></a>Windows Vista 또는 Windows 7 실행  
 다음 예제와 같이 netsh 도구를 사용하여 IP 수신 대기 목록을 수정합니다.  
  
```  
netsh http add iplisten ipaddress=0.0.0.0:8000  
```  
  
## <a name="other-configuration-settings"></a>기타 구성 설정  
 <xref:System.ServiceModel.WSDualHttpBinding>을 사용하는 경우 클라이언트 연결은 네임스페이스 예약 및 Windows 방화벽과 호환되는 기본값을 사용합니다. 이중 연결에 대한 클라이언트 기본 주소를 사용자 지정하는 경우에도 새 주소와 일치하도록 클라이언트에 이러한 HTTP 설정을 구성해야 합니다.  
  
 HTTP Server API에는 HttpCfg를 통해 사용할 수 없는 일부 고급 구성 설정이 포함되어 있습니다. 이러한 설정은 레지스트리에 유지되며 HTTP Server API를 사용하는 시스템에서 실행되는 모든 응용 프로그램에 적용됩니다. 이러한 설정에 대 한 정보를 참조 하십시오. [IIS에 대 한 Http.sys 레지스트리 설정](http://go.microsoft.com/fwlink/?LinkId=94843)합니다. 대부분의 사용자는 이러한 설정을 변경할 필요 없습니다.  
  
## <a name="issues-specific-to-windows-xp"></a>Windows XP 관련 문제  
 IIS는 [!INCLUDE[wxp](../../../../includes/wxp-md.md)]에서 포트 공유를 지원하지 않습니다. IIS가 실행 되는 WCF 서비스를 동일한 포트와 네임 스페이스를 사용 하려고 하는 경우 WCF 서비스가 시작 되지 않습니다. IIS 및 WCF 모두 기본적으로 포트 80을 사용 합니다. 서비스 중 하나에 대 한 포트 할당을 변경 하거나 IP 수신 대기 목록을 사용 하 여 WCF 서비스를 IIS에서 사용 되지 네트워크 어댑터에 할당 합니다. HTTP Server API를 사용할 수 있도록 IIS 6.0 이상이 다시 디자인되었습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.WSDualHttpBinding>  
 [방법: SSL 인증서로 포트 구성](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)
