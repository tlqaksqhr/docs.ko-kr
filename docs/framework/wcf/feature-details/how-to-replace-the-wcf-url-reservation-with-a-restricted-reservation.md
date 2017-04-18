---
title: "방법: WCF URL 예약을 제한된 예약으로 바꾸기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2754d223-79fc-4e2b-a6ce-989889f2abfa
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 방법: WCF URL 예약을 제한된 예약으로 바꾸기
URL 예약을 사용하여 URL 또는 URL 집합에서 메시지를 수신할 수 있는 사용자를 제한할 수 있습니다.예약은 URL 템플릿, ACL\(액세스 제어 목록\) 및 플래그 집합으로 이루어집니다.URL 템플릿은 예약이 영향을 미치는 URL을 정의합니다.URL 템플릿 처리 방식에 대한 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]는 [들어오는 요청 라우팅](http://go.microsoft.com/fwlink/?LinkId=136764)\(영문 페이지일 수 있음\)을 참조하십시오.ACL은 지정된 URL에서 메시지를 수신하도록 허용할 사용자 또는 사용자 그룹을 제어합니다.플래그는 예약이 사용자 또는 그룹에게 URL에서 직접 수신 대기할 수 있는 권한을 제공하는지 또는 일부 다른 프로세스에 수신 대기 권한을 위임할 수 있는 권한을 제공하는지를 나타냅니다.  
  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]는 포트 80에 모든 사용자가 이중 통신에 이중 HTTP 바인딩을 사용하는 응용 프로그램을 실행하도록 허용하는 전역 액세스가 가능한 예약을 만듭니다.이 예약의 ACL은 모든 사용자를 위한 것이므로 관리자는 URL 또는 URL 집합에서 수신 대기할 수 있는 권한을 명시적으로 허용하거나 허용하지 않을 수 없습니다.이 항목에서는 이 예약을 삭제하고 제한된 ACL로 예약을 다시 만드는 방법에 대해 설명합니다.  
  
 [!INCLUDE[wv](../../../../includes/wv-md.md)] 또는 [!INCLUDE[lserver](../../../../includes/lserver-md.md)]에서는 고급 명령 프롬프트에서 `netsh http show urlacl`을 입력하여 모든 HTTP URL 예약을 볼 수 있습니다.다음 예에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] URL 예약의 사용 예를 보여 줍니다.  
  
```  
Reserved URL : http://+:80/Temporary_Listen_Addresses/  
        User: \Everyone  
            Listen: Yes  
            Delegate: No  
            SDDL: D:(A;;GX;;;WD)  
```  
  
 예약은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램이 이중 통신에 HTTP 이중 바인딩을 사용하는 경우 사용되는 URL 템플릿으로 이루어집니다.이러한 형식의 URL은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에서 HTTP 이중 바인딩을 통해 통신할 때 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트로 다시 메시지를 전송하는 데 사용됩니다.모든 사용자가 URL에서 수신 대기할 수 있지만 다른 프로세스에 수신 권한을 위임할 수는 없습니다.마지막으로 ACL은 SSDL\(Security Descriptor Definition Language\) 형식으로 지정됩니다.SSDL[!INCLUDE[crabout](../../../../includes/crabout-md.md)][SSDL](http://go.microsoft.com/fwlink/?LinkId=136789)을 참조하십시오.  
  
### WCF URL 예약을 삭제하려면  
  
1.  **시작**을 클릭하고 **모든 프로그램**을 가리킨 후 **보조프로그램**을 클릭하고 **명령 프롬프트**를 마우스 오른쪽 단추로 클릭한 다음 표시되는 상황에 맞는 메뉴에서 **관리자 권한으로 실행**을 클릭합니다.계속할 수 있는 권한을 요청하는 UAC\(사용자 계정 컨트롤\) 창에서 **계속**을 클릭합니다.  
  
2.  명령 프롬프트 창에 **netsh http delete urlacl url\=http:\/\/\+:80\/Temporary\_Listen\_Addresses\/**를 입력합니다.  
  
3.  예약이 삭제되면 다음 메시지가 표시됩니다.**URL reservation successfully deleted**  
  
## 새 보안 그룹 및 새 제한된 URL 예약 만들기  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] URL 예약을 제한된 예약으로 바꾸려면 먼저 새 보안 그룹을 만들어야 합니다.이 작업은 명령 프롬프트 또는 컴퓨터 관리 콘솔에서 수행할 수 있습니다.한 가지만 수행하면 됩니다.  
  
#### 명령 프롬프트에서 새 보안 그룹을 만들려면  
  
1.  **시작**을 클릭하고 **모든 프로그램**을 가리킨 후 **보조프로그램**을 클릭하고 **명령 프롬프트**를 마우스 오른쪽 단추로 클릭한 다음 표시되는 상황에 맞는 메뉴에서 **관리자 권한으로 실행**을 클릭합니다.계속할 수 있는 권한을 요청하는 UAC\(사용자 계정 컨트롤\) 창에서 **계속**을 클릭합니다.  
  
2.  명령 프롬프트에 **net localgroup "\<security group name\>" \/comment:"\<security group description\>" \/add**를 입력합니다.여기서 **\<security group name\>**은 원하는 보안 그룹 이름으로 바꾸고 **\<security group description\>**은 보안 그룹에 대한 적절한 설명으로 바꿉니다.  
  
3.  보안 그룹이 만들어지면 다음 메시지가 표시됩니다.**The command completed successfully.**  
  
#### 컴퓨터 관리 콘솔에서 새 보안 그룹을 만들려면  
  
1.  **시작**, **제어판**, **관리 도구**, **컴퓨터 관리**를 차례로 클릭하여 컴퓨터 관리 콘솔을 엽니다.계속할 수 있는 권한을 요청하는 UAC\(사용자 계정 컨트롤\) 창에서 **계속**을 클릭합니다.  
  
2.  **시스템 도구**, **로컬 사용자 및 그룹**을 차례로 클릭하고 **그룹** 폴더를 마우스 오른쪽 단추로 클릭하고 표시되는 상황에 맞는 메뉴에서 **새 그룹**을 클릭합니다.이 새 보안 그룹에 대해 원하는 **그룹 이름**, **설명** 및 기타 세부 사항을 입력하고 **만들기** 단추를 클릭하여 보안 그룹을 만듭니다.  
  
#### 제한된 URL 예약을 만들려면  
  
1.  **시작**을 클릭하고 **모든 프로그램**을 가리킨 후 **보조프로그램**을 클릭하고 **명령 프롬프트**를 마우스 오른쪽 단추로 클릭한 다음 표시되는 상황에 맞는 메뉴에서 **관리자 권한으로 실행**을 클릭합니다.계속할 수 있는 권한을 요청하는 UAC\(사용자 계정 컨트롤\) 창에서 **계속**을 클릭합니다.  
  
2.  명령 프롬프트에 **netsh http add urlacl url\=http:\/\/\+:80\/Temporary\_Listen\_Addresses\/ user\="\<machine name\>\\\<security group name\>**을 입력합니다.여기서 **\<machine name\>**은 그룹에서 만들 컴퓨터 이름으로 바꾸고 **\<security group name\>**은 이전에 만든 보안 그룹 이름으로 바꿉니다.  
  
3.  예약이 만들어지면 다음 메시지가 표시됩니다.**URL reservation successfully added**.