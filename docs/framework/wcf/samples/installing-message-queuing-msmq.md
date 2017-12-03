---
title: "메시지 큐(MSMQ) 설치"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7ddcd497-3e04-427e-bc04-3610ad98b01e
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6a7ee646c2f6b20410c493ee139f08d11fc55d54
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="installing-message-queuing-msmq"></a>메시지 큐(MSMQ) 설치
다음 절차에서는 메시지 큐 4.0 및 메시지 큐 3.0을 설치하는 방법을 보여 줍니다.  
  
> [!NOTE]
>  [!INCLUDE[wxp](../../../../includes/wxp-md.md)] 및 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]에서는 메시지 큐 4.0을 사용할 수 없습니다.  
  
#### <a name="to-install-message-queuing-40-on-windows-server-2008-or-windows-server-2008-r2"></a>Windows Server 2008 또는 Windows Server 2008 R2에 메시지 큐 4.0을 설치하려면  
  
1.  서버 관리자에서 클릭 **기능**합니다.  
  
2.  아래에 있는 오른쪽 창에서 **기능 요약**, 클릭 **기능 추가**합니다.  
  
3.  결과 창에서 확장 **메시지 큐**합니다.  
  
4.  확장 **메시지 대기열 서비스**합니다.  
  
5.  클릭 **디렉터리 서비스 통합** (컴퓨터에 대 한 도메인에 가입)를 클릭 **HTTP 지원**합니다.  
  
6.  클릭 **다음**, 클릭 **설치**합니다.  
  
#### <a name="to-install-message-queuing-40-on-windows-7-or-windows-vista"></a>Windows 7 또는 Windows Vista에 메시지 큐 4.0을 설치하려면  
  
1.  **제어판**을 엽니다.  
  
2.  클릭 **프로그램** 차례로 선택한 다음 **프로그램 및 기능**, 클릭 **Windows 기능 사용을 설정 및 해제**합니다.  
  
3.  MSMQ(Microsoft Message Queue) Server, MSMQ(Microsoft Message Queue) Server Core를 차례로 확장한 후 설치할 다음과 같은 메시지 큐 기능 확인란을 선택합니다.  
  
    -   MSMQ Active Directory 도메인 서비스 통합(도메인에 연결된 컴퓨터의 경우)  
  
    -   MSMQ HTTP 지원  
  
4.  **확인**을 클릭합니다.  
  
5.  컴퓨터를 다시 시작 하는 메시지가 클릭 **확인** 설치를 완료 합니다.  
  
#### <a name="to-install-message-queuing-30-on-windows-xp-and-windows-server-2003"></a>Windows XP 및 Windows Server 2003에 메시지 큐 3.0을 설치하려면  
  
1.  **제어판**을 엽니다.  
  
2.  클릭 **프로그램 추가 / 제거** 클릭 하 고 **Windows 구성 요소 추가**합니다.  
  
3.  메시지 큐를 선택 하 고 클릭 **세부 정보**합니다.  
  
    > [!NOTE]
    >  [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]을 실행 중인 경우 메시지 큐에 액세스하기 위해 응용 프로그램 서버를 선택합니다.  
  
4.  MSMQ HTTP 지원 옵션이 자세히 페이지에 선택되어 있는지 확인합니다.  
  
5.  클릭 **확인** 세부 정보 페이지를 종료 한 다음 클릭 **다음**합니다. 설치를 완료합니다.  
  
6.  컴퓨터를 다시 시작 하는 메시지가 클릭 **확인** 설치를 완료 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [설치 지침](../../../../docs/framework/wcf/samples/set-up-instructions.md)
