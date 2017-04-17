---
title: "플러그형 프로토콜 프로그래밍 | Microsoft Docs"
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
  - "인터넷 리소스 다운로드, 플러그형 프로토콜"
  - "WebRequest 클래스, 플러그형 프로토콜"
  - "인터넷 요청에 응답, 플러그형 프로토콜"
  - "WebResponse 클래스, 플러그형 프로토콜"
  - "데이터 보내기, 플러그형 프로토콜"
  - "네트워크 리소스, 플러그형 프로토콜"
  - "인터넷, 플러그형 프로토콜"
  - "플러그형 프로토콜 프로그래밍"
  - "플러그형 프로토콜, 프로그래밍"
  - "인터넷에서 데이터 요청, 플러그형 프로토콜"
  - "데이터 받기, 플러그형 프로토콜"
  - "프로토콜, 플러그형"
ms.assetid: 66ef8456-7576-4e97-8956-959b216373db
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# 플러그형 프로토콜 프로그래밍
추상 <xref:System.Net.WebRequest> 및 <xref:System.Net.WebResponse> 클래스는 플러그형 프로토콜에 대 한 자료를 제공 합니다.  프로토콜 관련 클래스를 파생 하 여 <xref:System.Net.WebRequest> 및 <xref:System.Net.WebResponse>, 응용 프로그램 인터넷 리소스에서 데이터를 요청 하 고 사용 되는 프로토콜을 지정 하지 않고 응답을 읽을 수 있습니다.  
  
 특정 프로토콜을 만들려면 <xref:System.Net.WebRequest>, 만들기 메서드를 등록 해야 합니다.  정적 사용 <xref:System.Net.WebRequest.RegisterPrefix%28System.String%2CSystem.Net.IWebRequestCreate%29> 메서드를 <xref:System.Net.WebRequest> 등록 하는 <xref:System.Net.WebRequest> 하위 집합 특정 인터넷 구성표, 구성표 및 서버, 또는 구성표, 서버 및 경로 요청을 처리 합니다.  
  
 대부분의 메서드 및 속성을 사용 하 여 데이터를 주고받을 수 있을 것을 <xref:System.Net.WebRequest> 클래스입니다.  하지만 형식 프로토콜 관련 속성에 액세스 하는 경우를 변환할 수 있는 <xref:System.Net.WebRequest> 특정 파생 클래스 인스턴스.  
  
 플러그형 프로토콜을 이용 하 여 <xref:System.Net.WebRequest> 하위 프로토콜 관련 속성을 설정할 필요가 없는 기본 요청\-응답 트랜잭션을 제공 해야 합니다.  예를 들어,는 <xref:System.Net.HttpWebRequest> 는 구현 클래스는 <xref:System.Net.WebRequest> 클래스에 대 한 HTTP, 제공는 `GET` 요청을 반환 하 고 기본은 <xref:System.Net.HttpWebResponse> 웹 서버에서 반환 된 스트림에 포함 된.  
  
## 참고 항목  
 [WebRequest에서 파생](../../../docs/framework/network-programming/deriving-from-webrequest.md)   
 [WebResponse에서 파생](../../../docs/framework/network-programming/deriving-from-webresponse.md)   
 [.NET Framework의 네트워크 프로그래밍](../../../docs/framework/network-programming/index.md)   
 [방법: 프로토콜 관련 속성에 액세스하기 위해 WebRequest 형식 캐스팅](../../../docs/framework/network-programming/how-to-typecast-a-webrequest-to-access-protocol-specific-properties.md)