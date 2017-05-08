---
title: "wsatConfig.exe에서 반환된 오류 코드 해석 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ab65f22b-0d69-4c21-9aaf-74acef0ca102
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# wsatConfig.exe에서 반환된 오류 코드 해석
이 항목에서는 WS\-AtomicTransaction 구성 유틸리티\(wsatConfig.exe\)에서 생성한 모든 오류 코드 및 수행할 동작을 나열합니다.  
  
## 오류 코드 목록  
  
|오류 코드|설명|수행할 동작|  
|-----------|--------|------------|  
|0|작업이 완료되었습니다.|없음|  
|1|예기치 않은 오류|Microsoft에 문의하십시오.|  
|2|보안 설정을 검색하기 위해 MSDTC에 연결하는 동안 예기치 않은 오류가 발생했습니다.|MSDTC 서비스가 비활성화되지 않았는지 확인하고 반환된 예외에 표시된 모든 문제를 해결합니다.|  
|3|WsatConfig.exe가 실행된 계정에는 네트워크 보안 설정을 읽을 수 있는 충분한 권한이 없습니다.|Administrator 사용자 계정으로 WsatConfig.exe를 실행합니다.|  
|4|WS\-AT를 지원하기 전에 MSDTC에 "네트워크 DTC 액세스"를 사용합니다.|MSDTC에 "네트워크 DTC 액세스"를 사용하고 유틸리티를 다시 실행합니다.|  
|5|입력한 포트가 범위를 벗어났습니다.값은 1에서 65535 사이의 범위 내에 있어야 합니다.|오류 메시지에 표시된 대로 `-port:<portNum>`<br /><br /> 명령줄 옵션을 수정합니다.|  
|6|명령줄에 잘못된 끝점 인증서가 지정되었습니다.인증서를 찾을 수 없거나 인증서가 확인 과정을 통과하지 못했습니다.|`-endpointCert` 명령줄 옵션을 수정합니다.인증서에 개인 키가 있는지, 인증서를 ClientAuthentication 및 ServerAuthentication 모두에 사용할 수 있는지, 인증서가 LocalMachine\\MY 인증서 저장소에 설치되어 있는지 그리고 인증서를 완전히 신뢰할 수 있는지 확인합니다.|  
|7|명령줄에 잘못된 계정 인증서가 지정되었습니다.|`-accountsCerts` 명령줄 옵션을 수정합니다.지정한 인증서가 잘못 지정되었거나 해당 인증서를 찾을 수 없습니다.|  
|8|기본 시간 제한이 1초에서 3600초 사이의 범위를 벗어나 지정되었습니다.|표시된 대로 올바른 기본 시간 제한 값을 입력합니다.|  
|10|레지스트리에 액세스하는 동안 예기치 않은 오류가 발생했습니다.|실행 가능한 항목에 대한 오류 메시지 및 오류 코드를 확인합니다.|  
|11|레지스트리에 쓸 수 없습니다.|오류 메시지에 나열된 키가 WsatConfig.exe가 실행된 계정의 레지스트리 액세스를 지원할 수 있는지 확인합니다.|  
|12|인증서 저장소에 액세스하는 동안 예기치 않은 오류가 발생했습니다.|반환된 오류 코드를 사용하여 적절한 시스템 오류에 매핑합니다.|  
|13|http.sys를 구성하지 못했습니다.MSDTC에 대한 새 HTTPS 포트 예약을 만들 수 없습니다.|반환된 오류 코드를 사용하여 적절한 시스템 오류에 매핑합니다.|  
|14|http.sys를 구성하지 못했습니다.MSDTC에 대한 이전 HTTPS 포트 예약을 제거할 수 없습니다.|반환된 오류 코드를 사용하여 적절한 시스템 오류에 매핑합니다.|  
|15|http.sys를 구성하지 못했습니다.지정된 포트에 대한 이전 HTTPS 포트 예약이 이미 있습니다.|다른 응용 프로그램에 특정 포트에 대한 소유권이 이미 있습니다.다른 포트로 변경하거나 현재 응용 프로그램을 제거 또는 다시 구성합니다.|  
|16|http.sys를 구성하지 못했습니다.지정된 인증서를 포트에 바인딩할 수 없습니다.|오류 메시지에 반환된 오류 코드를 사용하여 적절한 시스템 오류에 매핑합니다.|  
|17|http.sys를 구성하지 못했습니다.이전 포트에서 SSL 인증서를 바인딩 해제할 수 없습니다.|오류 메시지에 반환된 오류 코드를 사용하여 적절한 시스템 오류에 매핑합니다.필요한 경우 httpcfg.exe 또는 netsh.exe를 사용하여 잘못된 포트 예약을 제거합니다.|  
|18|http.sys를 구성하지 못했습니다.이전 SSL 바인딩이 이미 있으므로 지정된 인증서를 포트에 바인딩할 수 없습니다.|다른 응용 프로그램에 특정 포트에 대한 소유권이 이미 있습니다.다른 포트로 변경하거나 현재 응용 프로그램을 제거 또는 다시 구성합니다.|  
|19|MSDTC를 다시 시작하지 못했습니다.|필요한 경우 MSDTC를 수동으로 다시 시작합니다.문제가 계속되면 Microsoft에 문의하십시오.|  
|20|[!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)]가 원격 컴퓨터에 설치되지 않았거나 올바로 설치되지 않았습니다.|컴퓨터에 [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)]를 설치합니다.|  
|21|작업 시간 제한 초과로 인해 원격 구성에 실패했습니다.|원격 컴퓨터에 WS\-AT를 구성하기 위해 호출은 90초보다 길어야 합니다.|  
|22|[!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)]가 원격 컴퓨터에 설치되지 않았거나 올바로 설치되지 않았습니다.|컴퓨터에 [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)]를 설치합니다.|  
|23|원격 컴퓨터의 예외로 인해 원격 구성에 실패했습니다.|실행 가능한 항목에 대한 오류 메시지를 확인합니다.|  
|26|잘못된 인수가 WsatConfig.exe에 전달되었습니다.|오류가 있는지 명령줄을 확인합니다.|  
|27|`-accounts` 명령줄 옵션이 잘못되었습니다.|\-`accounts` 명령줄 옵션을 수정하여 사용자 계정을 올바로 지정합니다.|  
|28|`-network` 명령줄 옵션이 잘못되었습니다.|`-network` 명령줄 옵션을 수정하여 "사용" 또는 "사용 안 함"을 올바로 지정합니다.|  
|29|`-maxTimeout` 명령줄 옵션이 잘못되었습니다.|표시된 대로 `-maxTimeout` 명령줄 옵션을 수정합니다.|  
|30|`-timeout` 명령줄 옵션이 잘못되었습니다.|표시된 대로 `-timeout` 명령줄 옵션을 수정합니다.|  
|31|`-traceLevel` 명령줄 옵션이 잘못되었습니다.|`-traceLevel` 명령줄 옵션을 수정하여 다음에서 유효한 값을 지정합니다.<br /><br /> -   Off<br />-   Error<br />-   Critical<br />-   경고<br />-   정보<br />-   Verbose<br />-   모두|  
|32|`-traceActivity` 명령줄 옵션이 잘못되었습니다.|"사용" 또는 "사용 안 함"을 지정하여 `-traceActivity` 명령줄 옵션을 수정합니다.|  
|33|`-traceProp` 명령줄 옵션이 잘못되었습니다.|"사용" 또는 "사용 안 함"을 지정하여 `-traceProp` 명령줄 옵션을 수정합니다.|  
|34|`-tracePII` 명령줄 옵션이 잘못되었습니다.|"사용" 또는 "사용 안 함"을 지정하여 `-tracePII` 명령줄 옵션을 수정합니다.|  
|37|WsatConfig.exe에서 정확한 시스템 인증서를 확인할 수 없습니다.둘 이상의 인증서가 있거나 인증서가 없는 경우 이 문제가 발생할 수 있습니다.|인증서 지문 또는 Issuer\\SubjectName 쌍을 지정하여 구성할 정확한 인증서를 올바로 확인합니다.|  
|38|프로세스 또는 사용자에게 방화벽 구성을 변경할 충분한 권한이 없습니다.|Administrator 사용자 계정으로 WsatConfig.exe를 실행합니다.|  
|39|방화벽 구성을 업데이트하는 동안 WsatConfig.exe에서 오류가 발생했습니다.|실행 가능한 항목에 대한 오류 메시지를 확인합니다.|  
|40|WsatConfig.exe에서 인증서의 개인 키 파일에 MSDTC 읽기 액세스 권한을 부여할 수 없습니다.|Administrator 사용자 계정으로 WsatConfig.exe를 실행합니다.|  
|41|[!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)]가 설치되지 않았거나 설치된 버전이 도구에서 구성할 수 있는 버전과 일치하지 않습니다.|[!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)]가 올바르게 설치되어 있고 해당 버전의 [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)]와 함께 제공되는 WsatConfig.exe 도구만을 사용하여 WS\-AT를 구성하는지 확인합니다.|  
|42|명령줄에 인수가 여러 번 지정되었습니다.|WsatConfig.exe를 실행할 때 각 인수를 한 번만 지정합니다.|  
|43|WS\-AT를 사용할 수 없는 경우 WsatConfig.exe에서는 WS\-AT 설정을 업데이트할 수 없습니다.|`-network:enable`을 추가 명령줄 인수로 지정합니다.|  
|44|필수 핫픽스가 없습니다. 먼저 핫픽스를 설치해야 WS\-AT를 구성할 수 있습니다.|필수 핫픽스 설치에 대한 지침은 [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] 릴리스 정보를 참조하십시오.|  
|45|`-virtualServer` 명령줄 옵션이 잘못되었습니다.|구성할 클러스터 리소스의 네트워크 이름을 지정하여 `-virtualServer` 명령줄 옵션을 수정합니다.|  
|46|ETW 추적 세션을 시작하려는 동안 예기치 않은 오류가 발생했습니다.|반환된 오류 코드를 사용하여 적절한 시스템 오류에 매핑합니다.|  
|47|프로세스 또는 사용자에게 ETW 추적 세션을 사용할 충분한 권한이 없습니다.|Administrator 사용자 계정으로 WsatConfig.exe를 실행합니다.|  
|48|ETW 추적 세션을 시작하려는 동안 예기치 않은 오류가 발생했습니다.|Microsoft에 문의하십시오.|  
|49|%systemdrive%에 공간이 부족하기 때문에 새 로그 파일을 만들 수 없습니다.|%systemdrive%에 로그 파일 공간이 충분한지 확인합니다.|  
|51|ETW 추적 세션을 시작하려는 동안 예기치 않은 오류가 발생했습니다.|Microsoft에 문의하십시오.|  
|52|ETW 추적 세션을 시작하려는 동안 예기치 않은 오류가 발생했습니다.|Microsoft에 문의하십시오.|  
|53|이전 ETW 세션 로그 파일을 백업하지 못했습니다.|%systemdrive%에 로그 파일 공간 및 이전 로그 파일의 백업\(있을 경우\) 공간이 충분하지 확인합니다.필요한 경우 이전 로그 파일을 수동으로 제거합니다.|  
|55|ETW 추적 세션을 시작하려는 동안 예기치 않은 오류가 발생했습니다.|Microsoft에 문의하십시오.|  
|56|ETW 추적 세션을 시작하려는 동안 예기치 않은 오류가 발생했습니다.|Microsoft에 문의하십시오.|  
  
## 참고 항목  
 [WS\-AtomicTransaction 구성 유틸리티\(wsatConfig.exe\)](../../../docs/framework/wcf/ws-atomictransaction-configuration-utility-wsatconfig-exe.md)