---
title: "방법: WCF URL 예약을 제한된 예약으로 바꾸기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2754d223-79fc-4e2b-a6ce-989889f2abfa
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8c25403f298444732f6787979add595bd877bb2c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation"></a>방법: WCF URL 예약을 제한된 예약으로 바꾸기
URL 예약을 사용하여 URL 또는 URL 집합에서 메시지를 수신할 수 있는 사용자를 제한할 수 있습니다. 예약은 URL 템플릿, ACL(액세스 제어 목록) 및 플래그 집합으로 이루어집니다. URL 템플릿은 예약이 영향을 미치는 URL을 정의합니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]URL 템플릿 처리 되며, 참조 [들어오는 요청 라우팅](http://go.microsoft.com/fwlink/?LinkId=136764)합니다. ACL은 지정된 URL에서 메시지를 수신하도록 허용할 사용자 또는 사용자 그룹을 제어합니다. 플래그는 예약이 사용자 또는 그룹에게 URL에서 직접 수신 대기할 수 있는 권한을 제공하는지 또는 일부 다른 프로세스에 수신 대기 권한을 위임할 수 있는 권한을 제공하는지를 나타냅니다.  
  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]는 포트 80에 모든 사용자가 이중 통신에 이중 HTTP 바인딩을 사용하는 응용 프로그램을 실행하도록 허용하는 전역 액세스가 가능한 예약을 만듭니다. 이 예약의 ACL은 모든 사용자를 위한 것이므로 관리자는 URL 또는 URL 집합에서 수신 대기할 수 있는 권한을 명시적으로 허용하거나 허용하지 않을 수 없습니다. 이 항목에서는 이 예약을 삭제하고 제한된 ACL로 예약을 다시 만드는 방법에 대해 설명합니다.  
  
 [!INCLUDE[wv](../../../../includes/wv-md.md)] 또는 [!INCLUDE[lserver](../../../../includes/lserver-md.md)]에서는 고급 명령 프롬프트에서 `netsh http show urlacl`을 입력하여 모든 HTTP URL 예약을 볼 수 있습니다.  다음 예에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] URL 예약의 사용 예를 보여 줍니다.  
  
```  
Reserved URL : http://+:80/Temporary_Listen_Addresses/  
        User: \Everyone  
            Listen: Yes  
            Delegate: No  
            SDDL: D:(A;;GX;;;WD)  
```  
  
 예약은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램이 이중 통신에 HTTP 이중 바인딩을 사용하는 경우 사용되는 URL 템플릿으로 이루어집니다. 이러한 형식의 URL은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에서 HTTP 이중 바인딩을 통해 통신할 때 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트로 다시 메시지를 전송하는 데 사용됩니다. 모든 사용자가 URL에서 수신 대기할 수 있지만 다른 프로세스에 수신 권한을 위임할 수는 없습니다. 마지막으로 ACL은 SSDL(Security Descriptor Definition Language) 형식으로 지정됩니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]SSDL, 참조 [SSDL](http://go.microsoft.com/fwlink/?LinkId=136789)  
  
### <a name="to-delete-the-wcf-url-reservation"></a>WCF URL 예약을 삭제하려면  
  
1.  클릭 **시작**, 가리킨 **모든 프로그램**, 클릭 **액세서리**를 마우스 오른쪽 단추로 클릭 **명령 프롬프트** 클릭 **계정으로 실행 관리자** 에서 비롯 되는 상황에 맞는 메뉴에 있습니다. 클릭 **계속** 궁금할 것 계속 하려면 관리 권한이 있는 사용자 계정 컨트롤 (UAC) 창에 있습니다.  
  
2.  에 입력 **urlacl url을 삭제 하는 netsh http = http: / / +:80/Temporary_Listen_Addresses/** 명령 프롬프트 창에서.  
  
3.  예약이 삭제되면 다음 메시지가 표시됩니다. **성공적으로 삭제 하는 URL 예약**  
  
## <a name="creating-a-new-security-group-and-new-restricted-url-reservation"></a>새 보안 그룹 및 새 제한된 URL 예약 만들기  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] URL 예약을 제한된 예약으로 바꾸려면 먼저 새 보안 그룹을 만들어야 합니다. 이 작업은 명령 프롬프트 또는 컴퓨터 관리 콘솔에서 수행할 수 있습니다. 한 가지만 수행하면 됩니다.  
  
#### <a name="to-create-a-new-security-group-from-a-command-prompt"></a>명령 프롬프트에서 새 보안 그룹을 만들려면  
  
1.  클릭 **시작**, 가리킨 **모든 프로그램**, 클릭 **액세서리**를 마우스 오른쪽 단추로 클릭 **명령 프롬프트** 클릭 **계정으로 실행 관리자** 에서 비롯 되는 상황에 맞는 메뉴에 있습니다. 클릭 **계속** 궁금할 것 계속 하려면 관리 권한이 있는 사용자 계정 컨트롤 (UAC) 창에 있습니다.  
  
2.  에 입력 **net localgroup "\<보안 그룹 이름 >" / 주석: "\<보안 그룹 설명 >"] / [추가** 명령 프롬프트입니다. 교체  **\<보안 그룹 이름 >** 만들 보안 그룹의 이름으로 및  **\<보안 그룹 설명 >** 에 대 한 적절 한 설명으로는 보안 그룹입니다.  
  
3.  보안 그룹이 만들어지면 다음 메시지가 표시됩니다. **명령이 성공적으로 완료 합니다.**  
  
#### <a name="to-create-a-new-security-group-from-the-computer-management-console"></a>컴퓨터 관리 콘솔에서 새 보안 그룹을 만들려면  
  
1.  클릭 **시작**, 클릭 **제어판**, 클릭 **관리 도구**를 클릭 하 고 **컴퓨터 관리** 컴퓨터를 열려면 관리 콘솔입니다. 클릭 **계속** 궁금할 것 계속 하려면 관리 권한이 있는 사용자 계정 컨트롤 (UAC) 창에 있습니다.  
  
2.  클릭 **시스템 도구**, 클릭 **로컬 사용자 및 그룹**를 마우스 오른쪽 단추로 클릭 **그룹** 폴더 **새 그룹** 상황에 맞는 메뉴에 있는 제공 합니다. 형식에서 원하는 **그룹 이름**, **설명** 및 기타 세부 사항을이 새 보안 그룹을 클릭은 **만들기** 단추 보안 그룹을 만듭니다.  
  
#### <a name="to-create-the-restricted-url-reservation"></a>제한된 URL 예약을 만들려면  
  
1.  클릭 **시작**, 가리킨 **모든 프로그램**, 클릭 **액세서리**를 마우스 오른쪽 단추로 클릭 **명령 프롬프트** 클릭 **계정으로 실행 관리자** 에서 비롯 되는 상황에 맞는 메뉴에 있습니다. 클릭 **계속** 궁금할 것 계속 하려면 관리 권한이 있는 사용자 계정 컨트롤 (UAC) 창에 있습니다.  
  
2.  에 입력 **netsh http urlacl url 추가 = http: / / +: 80/Temporary_Listen_Addresses/사용자 = "\<컴퓨터 이름 >\\< 보안 그룹 이름이\>**  명령 프롬프트입니다. 교체  **\<컴퓨터 이름 >** 기반이 여 그룹을 만들 컴퓨터 이름으로 및  **\<보안 그룹 이름 >** 만든 보안 그룹의 이름으로 이전에 있습니다.  
  
3.  예약이 만들어지면 다음 메시지가 표시됩니다. **성공적으로 추가 하는 URL 예약은**합니다.
