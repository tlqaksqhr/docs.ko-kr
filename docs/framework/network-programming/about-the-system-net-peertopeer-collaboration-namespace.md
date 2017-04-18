---
title: "System.Net.PeerToPeer.Collaboration 네임스페이스 정보 | Microsoft Docs"
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
ms.assetid: b5d8c1c1-6844-4947-9759-c7f1b564bded
caps.latest.revision: 4
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 4
---
# System.Net.PeerToPeer.Collaboration 네임스페이스 정보
<xref:System.Net.PeerToPeer.Collaboration> 네임 스페이스 클래스 및 피어\-투\-피어 공동 작업 인프라를 사용 하 여 피어 공동 작업을 구현 하는 데 사용 되는 Api를 제공 합니다.  
  
## 클래스  
 피어\-투\-피어 공동 작업의 구현에 사용 되는 주 클래스는 다음과 같습니다.  
  
-   <xref:System.Net.PeerToPeer.Collaboration.ContactManager>는 사용 피어 연락처를 저장할 수 있습니다.  
  
-   <xref:System.Net.PeerToPeer.Collaboration.PeerApplication> 게임, 채팅 클라이언트 또는 회의 솔루션 등 공동 작업을 합니다.  
  
-   활동에서 공동으로 작업할 피어.  이러한 피어도 나타낼 수 <xref:System.Net.PeerToPeer.Collaboration.PeerContact>, <xref:System.Net.PeerToPeer.Collaboration.PeerNearMe>, 또는 <xref:System.Net.PeerToPeer.Collaboration.PeerEndPoint> 개체입니다.  
  
-   정적 <xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration> 클래스 자체에 사용할 수 있는 응용 프로그램을 지정 하 고 있는 피어 있는 참여에.  
  
 <xref:System.Net.PeerToPeer.Collaboration.PeerContact.Invite%2A> 메서드는 공동 작업 세션에 피어를 초대 하는 데 사용 합니다.  호출 피어 다른 피어에 신호 업데이트 응용 프로그램, 개체 또는 현재 상태 정보를 공동 작업 세션에 관련 있는 이벤트를 구독할 수 있습니다.  상태 클래스를 지정 여부는 <xref:System.Net.PeerToPeer.Collaboration.Peer> 공동 작업에 사용할 수 및 <xref:System.Net.PeerToPeer.Collaboration.PeerScope> 클래스 얼마나 참여 수는 피어를 지정 하는 데 사용 됩니다: <xref:System.Net.PeerToPeer.Collaboration.PeerScope> \(글로벌\) <xref:System.Net.PeerToPeer.Collaboration.PeerScope>, \(서브넷\) 또는 <xref:System.Net.PeerToPeer.Collaboration.PeerScope>.  
  
 공동 작업 세션의 네 단계로 구성 됩니다.  
  
-   검색 합니다.  검색 하거나 응용 프로그램, 피어 및 현재 상태 정보를 게시 합니다.  예를 들어, 설치 된 동일한 게임에 있는 다른 사용자가 로컬 서브넷에 찾습니다.  
  
-   초대 합니다.  보내고 시작 하거나 참가할 수 있는 원격 피어에 대 한 보안 초대장을 수락 <xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration> 세션.  
  
-   연락처 관리입니다.  발견 된 피어를 연락처로 추가 된 <xref:System.Net.PeerToPeer.Collaboration.ContactManager>.  
  
-   통신 합니다.  통신이 설정 되 면 사용 하는 <xref:System.Net> Api는 <xref:System.Net.PeerToPeer> 다자간 통신에 대 한 Windows 통신 Foundation 피어 채널 클래스나 API를.  
  
 예를 들어 호스트 피어 공동 작업 세션을 시작 하 고 활용 하는 <xref:System.Net.PeerToPeer.Collaboration.ContactManager.CreateContact%2A> 메서드가 원격 피어와 로컬 피어를 호스트 피어의 연락처 관리자에 추가 합니다.  세 명의 사용자가 다음 자신의 개인 공동 작업 세션에 참가 합니다.  
  
 일반적인 P2P 응용 프로그램입니다: 공동 기록 또는 화이트 보드, 채팅을 사용 하지 않는 응용 프로그램, 대화형 광고 및 온라인 게임 세션에 대 한 전화 회의.  
  
## 참고 항목  
 <xref:System.Net.PeerToPeer.Collaboration>