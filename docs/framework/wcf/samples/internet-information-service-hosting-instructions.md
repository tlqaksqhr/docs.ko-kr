---
title: "인터넷 정보 서비스 호스팅 지침"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 959a21c8-9d9d-4757-b255-4e57793ae9d6
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7dd9d70a3b93faf721b5ac3bbd5f1114bf5c1461
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="internet-information-service-hosting-instructions"></a>인터넷 정보 서비스 호스팅 지침
IIS(인터넷 정보 서비스)에서 호스팅하는 샘플을 실행하려면 IIS가 올바르게 설치되어 있고 실행 중인지 확인해야 합니다.  
  
### <a name="to-install-iis-version-75-on-windows-server-2008-r2"></a>Windows Server 2008 R2에서 IIS 버전 7.5를 설치하려면  
  
1.  **서버 관리자**선택, **역할입니다.** 아래 **역할 요약**, 클릭 **역할 추가**합니다.  
  
2.  클릭 **다음** 표시 하는 **서버 역할 선택** 대화 상자.  
  
3.  선택 **응용 프로그램 서버** 에서 **역할** 목록으로 이동한 다음 클릭 **다음** 두 번 표시 하는 **역할 서비스 선택** 대화 상자는 응용 프로그램 서버 역할입니다.  
  
4.  선택 된 **웹 서버 (IIS)** 확인란 합니다. 추가 역할 서비스 및 기능을 설치 하는 메시지가 클릭 **필요한 기능 추가**합니다. 클릭 **다음** 두 번 표시 하는 **역할 서비스 선택** 웹 서버 (IIS) 역할에 대 한 대화 상자.  
  
5.  확장 **관리 도구**을 펼친 다음 **IIS 6 관리 호환성**합니다. 선택 **IIS 6 스크립팅 도구**합니다. 추가 역할 서비스 및 기능을 설치 하는 메시지가 클릭 **필요한 역할 서비스 추가**합니다. **다음**을 클릭합니다.  
  
6.  선택 사항 요약 올바르면 클릭 **설치**합니다.  
  
7.  설치가 완료 되 면 클릭 **닫기**합니다.  
  
### <a name="to-install-iis-version-75-on-windows-7"></a>Windows 7에서 IIS 버전 7.5를 설치하려면  
  
1.  클릭 **시작**, 클릭 하 고 **제어판**합니다.  
  
2.  열기는 **프로그램** 그룹입니다.  
  
3.  아래 **프로그램 및 기능**, 클릭 **Windows 기능 사용 / 사용 해제**합니다.  
  
4.  **사용자 계정 컨트롤** 대화 상자가 표시 됩니다. **계속**을 클릭합니다.  
  
5.  **Windows 기능** 대화 상자가 표시 됩니다. 항목을 확장 **인터넷 정보 서비스**합니다.  
  
6.  항목을 확장 **World Wide Web 서비스**합니다.  
  
7.  항목을 확장 **응용 프로그램 개발 기능**합니다.  
  
8.  다음 항목이 선택되었는지 확인합니다.  
  
    1.  **.NET 확장성**  
  
    2.  **ASP.NET**  
  
    3.  **ISAPI 확장**  
  
    4.  **ISAPI 필터**  
  
9. 항목 아래 **World Wide Web 서비스**를 확장 하 고 **일반 Http 기능**합니다.  
  
10. 확인 **정적 콘텐츠** 을 선택 합니다.  
  
11. 항목 아래 **World Wide Web 서비스**를 확장 하 고 **보안**합니다.  
  
12. 다음 사항을 확인 **Windows 인증** 을 선택 합니다.  
  
13. 아래는 **인터넷 정보 서비스** 디렉터리 항목을 확장 **웹 관리 도구**를 선택한 후 **IIS 관리 콘솔**합니다.  
  
14. 항목을 확장 **IIS 6 관리 호환성**를 선택한 후 **IIS 6 스크립팅 도구**합니다.  
  
15. 아래는 **인터넷 정보 서비스** 디렉터리 항목을 확장 **Microsoft.NET Framework 3.5.1**를 선택한 후 **Windows Communication Foundation Http 활성화**.  
  
16. **확인**을 클릭합니다.  
  
### <a name="to-install-iis-version-70-on-windows-server-2008"></a>Windows Server 2008에서 IIS 버전 7.0을 설치하려면  
  
1.  **서버 관리자**선택, **역할**합니다. 아래 **역할 요약**, 클릭 **역할 추가**합니다.  
  
2.  클릭 **다음** 표시 하는 **서버 역할 선택** 대화 상자.  
  
3.  선택 **응용 프로그램 서버** 에서 **역할** 목록으로 이동한 다음 클릭 **다음** 두 번 표시 하는 **역할 서비스 선택** 대화 상자는 응용 프로그램 서버 역할입니다.  
  
4.  선택 **웹 서버 (IIS)** 확인란 합니다. 추가 역할 서비스 및 기능을 설치 하는 메시지가 클릭 **필요한 기능 추가**합니다. 클릭 **다음** 두 번 표시 하는 **역할 서비스 선택** 웹 서버 (IIS) 역할에 대 한 대화 상자.  
  
5.  확장 **관리 도구**을 펼친 다음 **IIS 6 관리 호환성**합니다. 선택 **IIS 6 스크립팅 도구**합니다. 추가 역할 서비스 및 기능을 설치 하는 메시지가 클릭 **필요한 역할 서비스 추가**합니다. **다음**을 클릭합니다.  
  
6.  선택 사항 요약 올바르면 클릭 **설치**합니다.  
  
7.  설치가 완료 되 면 클릭 **닫기**합니다.  
  
### <a name="to-install-iis-version-70-on-windows-vista"></a>Windows Vista에서 IIS 버전 7.0을 설치하려면  
  
1.  시작을 클릭한 다음 제어판을 클릭합니다.  
  
2.  선택 된 **프로그램** 그룹입니다.  
  
3.  아래 **프로그램 및 기능**, 클릭 **Windows 기능 사용 / 사용 해제**합니다.  
  
4.  **사용자 계정 컨트롤** 대화 상자가 표시 됩니다. **계속**을 클릭합니다.  
  
5.  **Windows 기능** 대화 상자가 표시 됩니다. 항목을 확장 **인터넷 정보 서비스**합니다.  
  
6.  항목을 확장 **World Wide Web 서비스**합니다.  
  
7.  항목을 확장 **응용 프로그램 개발 기능**합니다.  
  
8.  다음 항목이 선택되었는지 확인합니다.  
  
    1.  **.NET 확장성**  
  
    2.  **ASP.NET**  
  
    3.  **ISAPI 확장**  
  
    4.  **ISAPI 필터**  
  
9. 항목을 확장 **웹 관리 도구**를 선택한 후 **IIS 관리 콘솔**합니다.  
  
10. 항목 아래 **World Wide Web 서비스**를 확장 하 고 **일반 Http 기능**합니다.  
  
11. 확인 **정적 콘텐츠** 을 선택 합니다.  
  
12. 항목 아래 **World Wide Web 서비스**를 확장 하 고 **보안**합니다.  
  
13. 확인 **Windows 인증** 을 선택 합니다.  
  
14. 항목을 확장 **IIS 6 관리 호환성**를 선택한 후 **IIS 6 스크립팅 도구**합니다.  
  
15. 항목을 확장 **Microsoft.NET Framework 3.0**를 선택한 후 **Windows Communication Foundation Http Activation**합니다.  
  
16. 클릭**확인**합니다.  
  
### <a name="to-install-iis-version-60-on-windows-server-2003"></a>Windows Server 2003에서 IIS 버전 6.0을 설치하려면  
  
1.  **사용자 서버 관리**, 클릭 **추가 또는 제거 하는 역할**, 클릭 하 고 **다음**합니다.  
  
2.  선택 **응용 프로그램 서버 (IIS, ASP.NET)** 에서 **서버 역할** 목록으로 이동한 다음 클릭 **다음**합니다.  
  
3.  선택 **ASP.NET 사용** 확인란을 선택한 다음 클릭 **다음**합니다.  
  
4.  선택 항목에 대한 요약이 모두 올바르면 다음을 클릭합니다.  
  
### <a name="to-install-iis-version-51-on-windows-xp-with-service-pack-2-and-service-pack-3-installed"></a>Windows XP 서비스 팩 2 및 서비스 팩 3에서 IIS 버전 5.1을 설치하려면  
  
1.  제어판에서 클릭 **프로그램 추가 / 제거**합니다.  
  
2.  에 **프로그램 추가 / 제거** 대화 상자를 클릭 **Windows 구성 요소 추가/제거**합니다.  
  
3.  에 **Windows 구성 요소 마법사**, 선택는 **인터넷 정보 서비스 (IIS)** 확인란을 선택한 다음 클릭 **다음**합니다.  
  
4.  경우는 **필요한 파일** 대화 상자가 표시 됩니다, 운영 체제 설치 디스크를 삽입, i386 폴더로 및 클릭 **확인**합니다.  
  
5.  설치가 완료 되 면 클릭 **마침**합니다.  
  
6.  닫습니다는 **프로그램 추가 / 제거** 대화 상자를 닫은 다음 **제어판**합니다.  
  
### <a name="to-verify-the-installation-of-iis-and-aspnet"></a>IIS 및 ASP.NET의 설치를 확인하려면  
  
1.  이 항목의 끝에 있는 HTML 파일을 루트 \InetPub\wwwroot 디렉터리에 저장하고 이름을 Default.aspx로 지정합니다.  
  
2.  브라우저 창을 엽니다.  
  
3.  형식 `http://localhost/Default.aspx` 주소 상자에 다음 ENTER 누릅니다.  
  
4.  "Hello World"라는 텍스트가 포함된 웹 페이지가 나타납니다.  
  
> [!NOTE]
>  새 버전의 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]를 설치할 때마다 aspnet_isapi를 IIS의 웹 서비스 확장으로 다시 등록해야 합니다. 이렇게 하려면 `aspnet_regiis –I –enable` 명령을 실행합니다.  
  
## <a name="sample-code"></a>샘플 코드  
  
```xml  
<html>  
   <body>  
       <form >  
           <h3> Hello World  
           </h3>  
       </form>  
   </body>  
</html>  
```
