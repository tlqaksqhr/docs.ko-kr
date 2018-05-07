---
title: WS-Atomic Transaction 지원 구성
ms.date: 03/30/2017
helpviewer_keywords:
- WS-AT protocol [WCF], configuring WS-Atomic Transaction
ms.assetid: cb9f1c9c-1439-4172-b9bc-b01c3e09ac48
ms.openlocfilehash: a89caad51f098e17bca1a5ba3df600a6dbf1dd9f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="configuring-ws-atomic-transaction-support"></a>WS-Atomic Transaction 지원 구성
이 항목에서는 WS-AT 구성 유틸리티를 사용하여 WS-AT(WS-AtomicTransaction) 지원을 구성하는 방법에 대해 설명합니다.  
  
## <a name="using-the-ws-at-configuration-utility"></a>WS-AT 구성 유틸리티 사용  
 WS-AT 구성 유틸리티(wsatConfig.exe)는 WS-AT 설정을 구성하는 데 사용됩니다. WS-AT 프로토콜 서비스를 사용하려면 구성 유틸리티를 사용하여 WS-AT에 대해 HTTPS 포트를 구성하고, X.509 인증서를 HTTPS 포트에 바인딩하고, 인증서 주체 이름이나 지문을 지정하여 허가된 파트너 인증서를 구성해야 합니다. 구성 유틸리티를 사용하여 추적 모드를 선택하고 기본 보내기 및 최대 받기 트랜잭션 시간 제한을 설정할 수도 있습니다.  
  
 구성 요소 서비스 관리 콘솔의 MMC(Microsoft Management Console) 속성 페이지 스냅인을 사용하거나 명령줄 창에서 이 도구의 기능에 액세스할 수 있습니다. 명령줄 창을 통해 로컬 컴퓨터에서 WS-AT 지원을 구성합니다. MMC 스냅인을 사용하는 경우 로컬 및 원격 컴퓨터에서 모두 설정을 구성합니다.  
  
 명령줄 창은 Windows SDK 설치 위치 "%WINDIR%\Microsoft.NET\Framework\v3.0\Windows Communication Foundation"에서 액세스할 수 있습니다.  
  
 명령줄 도구에 대 한 자세한 내용은 참조 [Ws-atomictransaction 구성 유틸리티 (wsatConfig.exe)](../../../../docs/framework/wcf/ws-atomictransaction-configuration-utility-wsatconfig-exe.md)합니다.  
  
 실행 하는 경우 [!INCLUDE[wxp](../../../../includes/wxp-md.md)] 또는 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]로 이동 하 여 MMC 스냅인을 액세스할 수 있습니다 **제어판/관리 도구/구성 요소 서비스**단추로 클릭 한 다음, **내 컴퓨터**, 및 선택 하면 **속성**합니다. 동일한 위치에서 MSDTC(Microsoft Distributed Transaction Coordinator)를 구성할 수 있습니다. 구성에 대해 사용할 수 있는 옵션 아래에 그룹화 되는 **WS-AT** 탭 합니다. Windows Vista를 실행 하는 경우 또는 [!INCLUDE[lserver](../../../../includes/lserver-md.md)]를 클릭 하 여 MMC 스냅인을 사용 하 여 찾을 수는 **시작** 단추 및 입력 `dcomcnfg.exe` 에 **검색** 상자입니다. MMC가 열리면로 이동 된 **내 Computer\Distributed Transaction Coordinator\Local DTC** 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **속성**합니다. 구성에 대해 사용할 수 있는 옵션 아래에 그룹화 되는 **WS-AT** 탭 합니다.  
  
 스냅인에 대 한 자세한 내용은 참조는 [Ws-atomictransaction 구성 MMC 스냅인](../../../../docs/framework/wcf/ws-atomictransaction-configuration-mmc-snap-in.md)합니다.  
  
 도구의 사용자 인터페이스를 사용하려면 먼저 다음 경로에 있는 WsatUI.dll 파일을 등록해야 합니다.  
  
 %PROGRAMFILES%\Microsoft SDKs\Windows\v6.0\Bin  
  
 제품을 등록하려면 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
 `regasm.exe /codebase WsatUI.dll`  
  
## <a name="enabling-ws-at"></a>WS-AT 사용  
 포트 443과 로컬 컴퓨터 저장소에 설치된 개인 키가 있는 X.509 인증서를 사용하여 MSDTC 내부에서 WS-AT 프로토콜 서비스를 활성화하려면 다음 명령으로 wsatConfig.exe 도구를 사용합니다.  
  
 `WsatConfig.exe –network:enable –port:8443 –endpointCert:<machine|"Issuer\SubjectName"> -accountsCerts:<thumbprint|"Issuer\SubjectName"> -restart`  
  
 각 매개 변수를 환경에 적합한 값으로 대체합니다.  
  
 MSDTC 내부에서 WS-AT 프로토콜 서비스를 비활성화하려면 다음 명령으로 wsatConfig.exe 도구를 사용합니다.  
  
 `WsatConfig.exe –network:disable -restart`  
  
## <a name="configuring-trust-between-two-machines"></a>두 컴퓨터 간에 트러스트 구성  
 WS-AT 프로토콜 서비스를 사용하려면 관리자가 분산 트랜잭션에 참여할 개별 계정에 명시적으로 권한을 부여해야 합니다. 두 컴퓨터의 관리자인 경우 컴퓨터 간에 올바른 인증서 집합을 교환하고 적합한 인증서 저장소에 설치한 다음 wsatConfig.exe 도구를 사용하여 각 컴퓨터의 인증서를 다른 컴퓨터의 허가된 참가자 인증서 목록에 추가함으로써 상호 트러스트 관계를 설정하도록 두 컴퓨터를 구성할 수 있습니다. 이 단계는 WS-AT를 사용하여 두 컴퓨터 간에 분산 트랜잭션을 수행하는 데 필요합니다.  
  
 다음 예제에서는 두 컴퓨터 A와 B 간에 트러스트를 설정하는 단계를 간략하게 설명합니다.  
  
### <a name="creating-and-exporting-certificates"></a>인증서 만들기 및 내보내기  
 이 절차에는 MMC 인증서 스냅인이 필요합니다. 이 스냅인은 시작/실행 메뉴를 열고 입력 상자에 "mmc"를 입력한 다음 확인을 눌러 액세스할 수 있습니다. 그런 다음는 **Console1** 창으로 이동 **파일/추가 / 제거** 스냅인을 추가 클릭 하 고 선택 **인증서** 에서 **사용 가능한 독립 실행형 스냅인** 목록입니다. 마지막으로 선택 **컴퓨터 계정** 관리 하 고 클릭 **확인**합니다. **인증서** 노드가 스냅인 콘솔에 나타납니다.  
  
 트러스트를 설정하려면 필요한 인증서가 이미 있어야 합니다. 참조를 만들고 다음 단계 전에 새 인증서를 설치 하는 방법을 알아보려면 [하는 방법: 만들기 및 개발 중 WCF에서에서 임시 클라이언트 인증서 설치](http://go.microsoft.com/fwlink/?LinkId=158925)합니다.  
  
1.  컴퓨터 A에서 MMC 인증서 스냅인을 사용하여 기존 인증서(certA)를 LocalMachine\MY(개인 노드) 및 LocalMachine\ROOT 저장소(신뢰할 수 있는 루트 인증 기관 노드)로 가져옵니다. 인증서를 특정 노드로 가져오려면 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **All Tasks/Import**합니다.  
  
2.  컴퓨터 B에서 MMC 인증서 스냅인을 사용하여 개인 키가 있는 certB 인증서를 만들거나 얻어 LocalMachine\MY(개인 노드) 및 LocalMachine\ROOT 저장소(신뢰할 수 있는 루트 인증 기관 노드)로 가져옵니다.  
  
3.  아직 수행하지 않은 경우 certA의 공개 키를 파일로 내보냅니다.  
  
4.  아직 수행하지 않은 경우 certB의 공개 키를 파일로 내보냅니다.  
  
### <a name="establishing-mutual-trust-between-machines"></a>컴퓨터 간의 상호 트러스트 설정  
  
1.  컴퓨터 A에서 certB의 파일 표현을 LocalMachine\MY 및 LocalMachine\ROOT 저장소로 가져옵니다. 이렇게 하면 컴퓨터 A가 통신할 때 certB를 트러스트합니다.  
  
2.  컴퓨터 B에서 certA의 파일을 LocalMachine\MY 및 LocalMachine\ROOT 저장소로 가져옵니다. 이렇게 하면 컴퓨터 B가 통신할 때 certA를 트러스트합니다.  
  
 이 단계를 완료하면 두 컴퓨터 간에 트러스트가 설정되고 WS-AT를 사용하여 서로 통신하도록 구성할 수 있습니다.  
  
### <a name="configuring-msdtc-to-use-certificates"></a>인증서를 사용하도록 MSDTC 구성  
 WS-AT 프로토콜 서비스는 클라이언트와 서버로 모두 작동하므로 들어오는 연결을 수신 대기하고 보내는 연결을 시작해야 합니다. 따라서 외부 당사자와 통신할 때 사용할 인증서와 들어오는 통신을 수락할 때 권한을 부여할 인증서를 알 수 있도록 MSDTC를 구성해야 합니다.  
  
 MMC WS-AT 스냅인을 사용하여 이 작업을 구성할 수 있습니다. 이 도구에 대 한 자세한 내용은 참조는 [Ws-atomictransaction 구성 MMC 스냅인](../../../../docs/framework/wcf/ws-atomictransaction-configuration-mmc-snap-in.md) 항목입니다. 다음 단계에서는 MSDTC를 실행하는 두 컴퓨터 간에 트러스트를 설정하는 방법에 대해 설명합니다.  
  
1.  컴퓨터 A의 설정을 구성합니다. "끝점 인증서" certA를 선택 합니다. "허가 된 인증서" certB를 선택 합니다.  
  
2.  컴퓨터 B의 설정을 구성합니다. "끝점 인증서" certB를 선택 합니다. "허가 된 인증서" certA를 선택 합니다.  
  
> [!NOTE]
>  한 컴퓨터에서 다른 컴퓨터로 메시지를 보낼 때 발신자는 수신자 인증서의 주체 이름과 수신자 컴퓨터의 이름이 일치하는지 확인합니다. 일치하지 않으면 인증서 확인이 실패하고 두 컴퓨터가 통신할 수 없습니다.  
>   
>  도메인에 가입된 컴퓨터의 경우 이름이 정규화된 도메인 이름입니다. 기본적으로 작업 그룹의 컴퓨터 이름은 컴퓨터의 NetBIOS 이름입니다. 그러나 두 컴퓨터 간에 사용되는 연결에 DNS(Domain Name System) 접미사가 있는 경우 해당 접미사도 이름에 포함될 수 있습니다.  
>   
>  컴퓨터 이름이 변경되는 경우, 예를 들어 작업 그룹 컴퓨터가 도메인에 가입하는 경우 인증서를 다시 발급하거나 수동으로 DNS 접미사를 구성해야 합니다.  
  
## <a name="security"></a>보안  
 MSDTC 및 WS-AT와 관련된 설정 중 일부는 레지스트리의 HKLM\Software\Microsoft\MSDTC 및 HKLM\Software\Microsoft\WSAT에 각각 저장되므로 이러한 레지스트리 키의 보안을 유지하여 관리자만 쓸 수 있도록 해야 합니다. 레지스트리 편집기 도구를 보호 하 고 선택 키를 마우스 오른쪽 단추로 클릭 **권한** 적절 한 액세스 제어를 설정 합니다. 시스템의 보안과 무결성을 유지하려면 권한이 낮은 사용자에 대해 중요한 키를 읽기 전용으로 설정해야 합니다.  
  
 MSDTC를 배포하는 경우 관리자는 MSDTC 데이터 교환의 보안을 유지해야 합니다. 작업 그룹 배포에서는 트랜잭션 인프라를 악의적인 사용자로부터 격리합니다. 클러스터 배포에서는 클러스터 레지스트리의 보안을 유지합니다.  
  
## <a name="tracing"></a>추적  
 WS-AT 프로토콜 서비스가 지 원하는 통합, 트랜잭션 사용 및을 사용 하 여 관리할 수 있는 특정 추적의 [Ws-atomictransaction 구성 MMC 스냅인](../../../../docs/framework/wcf/ws-atomictransaction-configuration-mmc-snap-in.md) 도구입니다.  추적에는 특정 트랜잭션에 대해 인리스트먼트가 수행된 시간, 트랜잭션이 터미널 상태에 도달한 시간, 각 트랜잭션 인리스트먼트가 받은 결과 등을 나타내는 데이터가 포함될 수 있습니다. 사용 하 여 모든 추적 내용을 볼 수는 [Service Trace Viewer 도구 (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) 도구입니다.  
  
 또한 WS-AT 프로토콜 서비스는 ETW 추적 세션을 통해 통합된 ServiceModel 추적을 지원합니다. 이 추적 기능은 기존의 트랜잭션 추적 외에 보다 자세한 통신 관련 추적을 제공합니다.  이러한 추가 추적을 사용하려면 다음 단계를 수행합니다.  
  
1.  열기는 **시작/실행** 메뉴 입력된 상자에 "regedit"를 입력 하 고 선택 **확인**합니다.  
  
2.  에 **레지스트리 편집기**, 왼쪽 창에서 Hkey_Local_Machine\SOFTWARE\Microsoft\WSAT\3.0\ 폴더로 이동 합니다.  
  
3.  마우스 오른쪽 단추로 클릭는 `ServiceModelDiagnosticTracing` 값 오른쪽 창에서 선택한 **수정**합니다.  
  
4.  에 **값 데이터** 입력 상자를 사용 하도록 설정 하려는 추적 수준을 지정 하려면 유효한 값 중 하나를 입력 합니다.  
  
-   0: 해제  
  
-   1: 위험  
  
-   3: 오류. 이 값이 기본값입니다.  
  
-   7: 경고  
  
-   15: 정보  
  
-   31: 자세한 정보  
  
## <a name="see-also"></a>참고 항목  
 [WS-AtomicTransaction 구성 유틸리티(wsatConfig.exe)](../../../../docs/framework/wcf/ws-atomictransaction-configuration-utility-wsatconfig-exe.md)  
 [WS-AtomicTransaction 구성 MMC 스냅인](../../../../docs/framework/wcf/ws-atomictransaction-configuration-mmc-snap-in.md)
