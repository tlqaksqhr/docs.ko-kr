---
title: "연결 그룹화 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "인터넷, 연결"
  - "연결[.NET Framework], 그룹화"
  - "WebRequest 클래스, 연결 그룹화"
  - "네트워크 리소스, 연결"
  - "연결 풀링"
ms.assetid: 2ec502e8-4ba0-4c22-9410-f28eaf4eee63
caps.latest.revision: 7
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 7
---
# 연결 그룹화
연결 그룹화는 단일 응용 프로그램에 정의 된 연결 풀 내의 특정 요청을 연결합니다.  사용자를 대신 하 여 백 엔드 서버에 연결 하 고 위임, Kerberos 등 아래 예제와 같이 자신의 자격 증명을 제공 하는 중간 계층 응용 프로그램에서 지 원하는 인증 프로토콜을 사용 하 여 중간 계층 응용 프로그램에서 필요할 수 있습니다.  예를 들어 사용자 Joe가 급여 정보를 표시 하는 내부 웹 사이트를 방문 하는 것으로 가정 합니다.  Joe를 인증 한 후 중간 계층 응용 프로그램 서버가 급여 정보를 검색할 수 백 엔드 서버에 연결할 Joe의 자격 증명을 사용 합니다.  그런 다음 강선 사이트를 방문 하 고 자신의 급여 정보를 요청.  중간 계층 응용 프로그램 이미 Joe의 자격 증명을 사용 하 여 연결을 변경한 때문에 백 엔드 서버는 Joe의 정보로 응답 합니다.  그러나 응용 프로그램 연결 그룹에서 사용자 이름을 잘못 백 엔드 서버로 전달 하는 각 요청을 할당 하는 경우 다음 각 사용자가 별도 연결 풀에 속하고 실수로 인증 정보를 다른 사용자와 공유할 수 없습니다.  
  
 요청을 특정 연결 그룹에 할당 하는 이름에 할당 된 <xref:System.Net.WebRequest.ConnectionGroupName%2A> 속성의 사용자 <xref:System.Net.WebRequest> 요청 하기 전에.  
  
## 참고 항목  
 [연결 관리](../../../docs/framework/network-programming/managing-connections.md)   
 [방법: 그룹 연결에 사용자 정보 할당](../../../docs/framework/network-programming/how-to-assign-user-information-to-group-connections.md)