---
title: "메시지 보안의 동작 추적 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 68862534-3b2e-4270-b097-8121b12a2c97
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# 메시지 보안의 동작 추적
이 항목에서는 보안 처리에 대한 동작 추적에 대해 설명합니다. 동작 추적은 다음과 같은 세 가지 단계로 발생합니다.  
  
-   협상\/SCT 교환.이 단계는 전송 계층\(이진 데이터 교환 사용\) 또는 메시지 계층\(SOAP 메시지 교환 사용\)에서 발생할 수 있습니다.  
  
-   서명 확인 및 인증을 통한 메시지 암호화\/해독.추적이 앰비언트 동작\(일반적으로 "Process Action"\)에 나타납니다.  
  
-   권한 부여 및 확인.끝점 간에 통신할 때 또는 로컬로 발생할 수 있습니다.  
  
## 협상\/SCT 교환  
 협상\/SCT 교환 단계에서는 클라이언트에서 "Set up Secure Session" 및 "Close Secure Session"의 두 가지 동작 유형이 만들어집니다. "Set up Secure Session"은 RST\/RSTR\/SCT 메시지 교환에 대한 추적을 포함하고, "Close Secure Session"은 취소 메시지에 대한 추적을 포함합니다.  
  
 서버에서 RST\/RSTR\/SCT에 대한 각 요청\/회신이 자체 동작에 표시됩니다.서버와 클라이언트에서 모두 `propagateActivity`\=`true`이면 서버의 동작이 동일한 ID를 사용하고 Service Trace Viewer에서 볼 때 "Set up Secure Session"에 함께 표시됩니다.  
  
 이 동작 추적 모델은 사용자 이름\/암호 인증, 인증서 인증 및 NTML 인증에 사용할 수 있습니다.  
  
 다음 표에서는 협상 및 SCT 교환에 대한 동작과 추적을 보여 줍니다.  
  
||협상\/SCT 교환 발생 시기|동작|추적|  
|-|----------------------|--------|--------|  
|보안 전송<br /><br /> \(HTTPS, SSL\)|첫 번째 메시지를 수신했을 때|앰비언트 동작에서 추적을 내보냅니다.|-   교환 추적<br />-   보안 채널 설정<br />-   가져온 비밀을 공유합니다.|  
|보안 메시지 계층<br /><br /> \(WSHTTP\)|첫 번째 메시지를 수신했을 때|클라이언트 측:<br /><br /> -   RST\/RSTR\/SCT의 각 요청\/회신에 대한 첫 번째 메시지의 "Process Action" 중 "Setup Secure Session"<br />-   "Close Proxy activity"에서 CANCEL 교환에 대한 "Close Secure Session". 이 동작은 보안 세션이 닫힌 시간에 따라 일부 다른 앰비언트 동작에서 발생할 수 있습니다.<br /><br /> 서버 측:<br /><br /> -   서버에서 RST\/SCT\/Cancel의 각 요청\/회신에 대한 하나의 "Process Action" 동작.`propagateActivity`\=`true`이면 서버에서 RST\/RSTR\/SCT 동작이 "Set up Security Session"과 병합되고, Cancel은 "Close" 동작과 병합됩니다.<br /><br /> "Set up Secure Session"에는 다음과 같은 두 가지 단계가 있습니다.<br /><br /> 1.  인증 협상.클라이언트에 이미 적절한 자격 증명이 있는 경우 선택 사항입니다.이 단계는 보안 전송 또는 메시지 교환을 통해 수행할 수 있습니다.메시지 교환을 통해 수행할 경우 하나 또는 두 개의 RST\/RSTR 교환이 발생할 수 있습니다.이러한 교환에 대해 앞에서 설명한 대로 새 요청\/회신 동작에서 추적을 내보냅니다.<br />2.  보안 세션 설정\(SCT\). 여기서는 하나의 RST\/RSTR 교환이 발생합니다.이 단계에는 앞에서 설명한 것과 동일한 앰비언트 동작이 있습니다.|-   교환 추적<br />-   보안 채널 설정<br />-   가져온 비밀을 공유합니다.|  
  
> [!NOTE]
>  혼합 보안 모드의 경우 이진 교환에서는 협상 인증이 발생하지만 메시지 교환에서는 SCT가 발생합니다.순수 전송 모드의 경우에는 추가 동작이 없는 전송에서만 협상이 발생합니다.  
  
## 메시지 암호화 및 해독  
 다음 표에서는 메시지 암호화\/해독 및 서명 인증에 대한 활동과 추적을 보여 줍니다.  
  
||보안 전송<br /><br /> \(HTTPS, SSL\) 및 보안 메시지 계층<br /><br /> \(WSHTTP\)|  
|-|---------------------------------------------------------|  
|메시지 암호화\/해독 및 서명 인증 발생 시기|메시지를 수신했을 때|  
|활동|클라이언트 및 서버의 ProcessAction 동작에서 추적을 내보냅니다.|  
|추적|-   sendSecurityHeader\(발신자\):<br />-   메시지 서명<br />-   요청 데이터 암호화<br />-   receiveSecurityHeader\(수신자\):<br />-   서명 확인<br />-   응답 데이터 해독<br />-   인증|  
  
> [!NOTE]
>  순수 전송 모드에서는 추가 동작이 없는 전송에서만 메시지 암호화\/해독이 발생합니다.  
  
## 권한 부여 및 확인.  
 다음 표에서는 권한 부여에 대한 동작과 추적을 보여 줍니다.  
  
||권한 부여 발생 시기|활동|추적|  
|-|-----------------|--------|--------|  
|로컬\(기본값\)|서버에서 메시지가 해독된 후|서버의 ProcessAction 동작에서 추적을 내보냅니다.|사용자에게 권한이 부여되었습니다.|  
|원격|서버에서 메시지가 해독된 후|ProcessAction 동작에 의해 호출된 새로운 동작에서 추적을 내보냅니다.|사용자에게 권한이 부여되었습니다.|