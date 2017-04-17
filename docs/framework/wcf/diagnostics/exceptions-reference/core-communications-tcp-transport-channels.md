---
title: "핵심 통신: TCP 전송 채널 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d5cd057f-faec-4e21-ae0e-18bbc22bcfb1
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# 핵심 통신: TCP 전송 채널
이 항목에서는 TCP 전송 채널에 의해 생성된 모든 예외를 보여 줍니다.  
  
## 예외 목록  
  
|리소스 코드|리소스 문자열|  
|------------|-------------|  
|SocketCloseReadTimeout|지정한 소켓의 원격 끝점이 할당된 시간 제한 내에 닫기 요청에 응답하지 않았습니다.  Receive 작업에서 EOF 신호\(null\)를 받은 후에 원격 끝점이 Close를 호출하지 않을 수 있습니다.  이 작업에 할당된 시간은 더 긴 시간 제한의 일부였을 수 있습니다.|