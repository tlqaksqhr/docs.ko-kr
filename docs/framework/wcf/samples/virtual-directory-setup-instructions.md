---
title: 가상 디렉터리 설치 지침
ms.date: 03/30/2017
ms.assetid: 3c62cab5-81a4-48b6-ac8c-9ce33a85a157
ms.openlocfilehash: 3ff578b69590071ef2135e777b3105e7c226563e
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="virtual-directory-setup-instructions"></a>가상 디렉터리 설치 지침
Windows Communication Foundation (WCF) 샘플은 %SystemDrive%\inetpub\wwwroot\servicemodelsamples 폴더에 매핑되어 있는 servicemodelsamples 라는 공용 가상 디렉터리를 공유 하는 데 사용 됩니다.  
  
> [!NOTE]
>  %SystemDrive%는 일반적으로 C: 또는 D:이며 IIS(인터넷 정보 서비스)가 설치된 드라이브 위치에 따라 달라집니다.  
  
 Setupvroot.bat 및 Cleanupvroot.bat 파일을 실행할 수는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) 가상 디렉터리를 만듭니다. 가상 디렉터리를 수동으로 만들려면 다음 절차를 사용합니다.  
  
## <a name="procedures"></a>절차  
  
#### <a name="to-create-a-virtual-directory-in-iis-70-or-75"></a>IIS 7.0 또는 7.5에서 가상 디렉터리를 만들려면  
  
1.  **시작** 메뉴를 클릭 **실행**, 다음 입력 **inetmgr** 를 인터넷 정보 서비스 (IIS) MMC 스냅인을 엽니다.  
  
2.  왼쪽된 창에서 컴퓨터의 이름이 있는 노드를 확장 한 다음 확장은 **사이트** 노드.  
  
3.  마우스 오른쪽 단추로 클릭 **기본 웹 사이트**를 선택한 후 **응용 프로그램 추가** 열려는 **추가 응용 프로그램 창**합니다.  
  
4.  창에서 입력 `servicemodelsamples` 만들고 있는 가상 디렉터리에 대 한 별칭으로 합니다.  
  
5.  %SystemDrive%\inetpub\wwwroot\servicemodelsamples 디렉터리를 만듭니다.  
  
6.  실제 경로를 %SystemDrive%\inetpub\wwwroot\servicemodelsamples로 설정합니다.  대부분의 WCF 샘플은 빌드 시 서비스 실행 파일을 이 위치에 복사합니다.  
  
7.  **확인**을 클릭합니다. WCF 샘플에 웹 응용 프로그램이 만들어집니다.  
  
    > [!NOTE]
    >  모든 WCF 샘플에서는 동일한 servicemodelsamples 웹 응용 프로그램을 사용 하기 때문에이 작업을 한 번만 수행 되어야 합니다.  
  
    > [!NOTE]
    >  이 문서에서는 `virtual directory`라는 용어는 `Web application`과 동의어입니다.  
  
     가상 디렉터리를 만드는 것 이외에 WCF 서비스를 실행할 수 있도록 해당 속성을 설정 해야 합니다. 자세한 내용은 다음을 참조하십시오.  
  
#### <a name="to-create-a-virtual-directory-in-iis-51-or-60"></a>IIS 5.1 또는 6.0에서 가상 디렉터리를 만들려면  
  
1.  명령 프롬프트 창을 열고 형식 `start inetmgr` 를 인터넷 정보 서비스 (IIS) MMC 스냅인을 엽니다.  
  
2.  왼쪽된 창에서 컴퓨터의 이름이 있는 노드를 확장 한 다음 확장은 **웹사이트** 노드.  
  
3.  마우스 오른쪽 단추로 클릭 **기본 웹 사이트** 선택 **새로 만들기, 가상 디렉터리** 가상 디렉터리 만들기 마법사를 엽니다.  
  
4.  마법사에서 입력 `servicemodelsamples` 만들고 있는 가상 디렉터리에 대 한 별칭으로 합니다.  
  
5.  경로를 %SystemDrive%\inetpub\wwwroot\servicemodelsamples로 설정합니다. 대부분의 WCF 샘플은 빌드 시 서비스 실행 파일을 이 위치에 복사합니다.  
  
6.  **다음**을 클릭합니다.  
  
7.  기본적으로 다음 확인란이 선택되어 있습니다.  
  
    -   **읽기**  
  
    -   **스크립트 실행 (예: ASP)**  
  
8.  클릭 **다음**, 클릭 하 고 **마침** 마법사를 완료 합니다.  
  
    > [!NOTE]
    >  모든 WCF 샘플에서는 동일한 servicemodelsamples 가상 디렉터리를 사용 하기 때문에이 작업을 한 번만 수행 되어야 합니다.  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-70-or-75"></a>7.5 또는 IIS 7.0에서 추가 가상 디렉터리 속성을 설정 하려면  
  
1.  servicemodelsamples 노드를 클릭합니다. 창 아래쪽에 두 개의 뷰가 표시됩니다. 선택 **기능 보기** 아직 선택 되지 않은 경우.  
  
2.  에 대 한 항목을 두 번 클릭 **디렉터리 검색**합니다.  
  
3.  작업 창에서 선택 된 **사용** 옵션입니다. 이렇게 하면 Internet Explorer를 사용하는 디렉터리의 디렉터리에 액세스할 수 있어 서비스를 디버깅할 때 도움이 됩니다.  
  
 마지막으로 다른 사용자가 액세스할 수 있도록 servicemodelsamples 폴더의 보안 속성을 설정해야 합니다. 자세한 내용은 다음을 참조하십시오.  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-51-or-60"></a>IIS 5.1 또는 6.0에서 추가 가상 디렉터리 속성을 설정하려면  
  
1.  Servicemodelsamples 노드를 마우스 오른쪽 단추로 누른 **속성**합니다.  
  
2.  기본적으로 다음 확인란이 선택되어 있습니다.  
  
    -   **읽기**  
  
    -   **방문 기록**  
  
    -   **이 리소스 색인화**  
  
3.  선택 된 **디렉터리 검색** 확인란 합니다. 이렇게 하면 Internet Explorer를 사용하는 디렉터리의 디렉터리에 액세스할 수 있어 서비스를 디버깅할 때 도움이 됩니다.  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-70-or-75"></a>IIS 7.0 또는 7.5에서 폴더의 보안 속성을 설정 하려면  
  
1.  %SystemDrive%\inetpub\wwwroot\servicemodelsamples로 이동합니다.  
  
2.  Servicemodelsamples 폴더를 마우스 오른쪽 단추로 클릭 하 고 클릭 **공유** 또는 **공유**합니다.  
  
3.  왼쪽의 아래쪽 화살표를 클릭는 **추가** 단추입니다.  
  
4.  선택 된 **찾을** 항목입니다. **사용자 또는 그룹 선택** 창이 열립니다.  
  
5.  **고급**을 클릭합니다.  
  
6.  클릭 **위치**합니다. **위치** 창이 열려 되었습니다.  
  
7.  사용 중인 컴퓨터에 대한 항목을 선택합니다. 표시되어 있는 도메인이나 네트워크에 대한 항목이 아닌 로컬 컴퓨터를 선택해야 합니다. 사용자가 컴퓨터를 선택한 후 클릭 **확인**합니다.  
  
8.  클릭 **지금 찾기**합니다. 그러면 검색 결과가 로컬 컴퓨터와 연결된 개체로 채워집니다.  
  
9. 찾을 **IIS_IUSRS** 항목에는 **이름 (상대 고유 이름)** 열입니다. 항목을 선택 하 고 클릭 **확인** 결과 창을 닫으려면 검색 합니다.  
  
10. 클릭 **확인** 를 닫으려면는 **사용자 또는 그룹 선택** 창.  
  
11. 클릭 **공유** 의 변경 사항을 유지 합니다.  
  
12. 공유할 수 있도록 변경이 완료 후 클릭 **수행** 를 닫으려면는 **파일 공유** 창.  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-51-or-60"></a>IIS 5.1 또는 6.0에서 폴더의 보안 속성을 설정하려면  
  
1.  %SystemDrive%\inetpub\wwwroot\servicemodelsamples로 이동합니다.  
  
2.  마우스 오른쪽 단추로 클릭는 **servicemodelsamples** 폴더와 클릭 **공유 및 보안 합니다.**  
  
3.  **보안** 탭을 클릭합니다.  
  
4.  IIS 6.0을 사용 하는 경우는 **그룹 또는 사용자 이름** 상자에서 확인 여부 **인터넷 게스트 계정** 나열 됩니다.  
  
     인터넷 게스트 계정이 표시되어 있지 않은 경우  
  
    1.  클릭 **시작** 클릭 하 고 **제어판**합니다.  
  
    2.  표시 되지 않으면는 **사용자 계정** 아이콘을 클릭 하 여 **종류별 보기로 전환**합니다.  
  
    3.  클릭는 **사용자 계정** 아이콘입니다.  
  
    4.  아래에서 "또는 제어판 아이콘 선택" 클릭 **사용자 계정**합니다.  
  
    5.  에 **사용자 계정** 대화 상자를 클릭는 **고급** 탭 합니다.  
  
    6.  **고급**을 클릭합니다.  
  
    7.  에 **로컬 사용자 및 그룹** 대화 상자를 클릭 하 여 확장 하 고는 **사용자** 폴더입니다.  
  
    8.  오른쪽 창에서 두 번 클릭 **인터넷 게스트 계정**합니다.  
  
    9. 에 **속성** 이름이 인터넷 게스트 계정으로 사용 대화 상자, 복사 합니다. 기본적으로 이름은 "USR_" 다음에 컴퓨터의 이름이 옵니다.  
  
    10. **속성** 대화 상자를 닫습니다.  
  
    11. 닫기는 **로컬 사용자 및 그룹** 대화 상자.  
  
    12. 닫기는 **사용자 계정** 대화 상자.  
  
    13. 다른 닫습니다 **사용자 계정** 대화 상자.  
  
    14. 에 **servicemodelsamples 속성** 대화 상자의 **보안** 탭을 클릭 **추가**합니다.  
  
    15. 뒤에 백슬래시가 오는 컴퓨터의 이름을 입력 하 고 예를 들어 myMachineName 인터넷 사용자 계정의 이름을 붙여\\% InternetGuestAccountName %  
  
    16. 클릭 **이름 확인** 에 추가 된 내용을 확인 합니다. 이름이 올바른 경우 모두 밑줄이 있는 대문자입니다.  
  
5.  IIS 6.0에 대해서도 확인 네트워크 서비스에 나열 되어 있는지는 **그룹 또는 사용자 이름** 상자입니다.  
  
     NETWORK SERVICE가 표시되어 있지 않은 경우  
  
    1.  **추가**를 클릭합니다.  
  
    2.  에 **사용자 또는 그룹 선택** 컴퓨터의 이름 뒤에 백슬래시가 오는 대화 상자를 입력 합니다.  
  
    3.  형식 **서비스** 뒤의 백슬래시 (공백 없음).  
  
    4.  클릭 **이름 확인**합니다.  
  
    5.  이름이 여러 개 있는 경우 선택 **네트워크 서비스** 클릭 **확인**합니다.  
  
    6.  클릭 **확인** 를 닫으려면는 **사용자 또는 그룹 선택** 대화 상자.  
  
6.  IIS 5.1과 Windows XP s p 2를 사용 하는 경우 인터넷 게스트 계정 및 ASPNET 모두에 나열 되어 있는지 확인은 **그룹 또는 사용자 이름** 상자입니다.  
  
     ASPNET 사용자는 멤버의 기본 제공 될 수 있습니다 **사용자** 보안 그룹입니다. 이 경우 다음 경우는 **사용자** 그룹 대화 상자에 표시 됩니다, 허용 된 사용자 목록에 별도 항목으로 추가할 필요가 없습니다.  
  
     ASPNET의 일부 인지 확인 하기는 **사용자** 보안 그룹:  
  
    1.  에 **시작** 메뉴를 클릭 하 여 **제어판**합니다.  
  
    2.  클릭는 **사용자 계정** 아이콘입니다.  
  
    3.  에 **그룹** 열에 있는지 여부를 확인에 대 한 값 **ASPNET** 가 "Users"  
  
## <a name="see-also"></a>참고 항목  
 [인터넷 정보 서비스 호스팅 지침](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md)
