---
title: "피어 투 피어 공동 작업"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b6216d88-bccb-4a59-9f1c-9f751708e811
caps.latest.revision: "7"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 607fadad19d4fe69800798583a14d7fd9082ff23
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="peer-to-peer-collaboration"></a>피어 투 피어 공동 작업
피어 투 피어 네트워킹은 인터넷의 에지에서 클라이언트 기반 컴퓨팅 작업 이상을 수행하는 비교적 강력한 컴퓨터(개인용 컴퓨터)를 활용합니다. 최신 개인용 컴퓨터(PC)에는 매우 빠른 프로세서, 광대한 메모리 및 대형 하드 디스크가 있으며, 이러한 리소스는 전자 메일과 웹 검색 등의 일반적인 컴퓨팅 작업을 수행할 때 완전히 이용되지 않습니다. 최신 PC는 여러 형식의 응용 프로그램을 위한 서버(피어) 및 클라이언트로 사용될 수 있습니다.  
  
-   피어 투 피어 공동 작업 인프라는 Windows Vista 이상 플랫폼에서 주변 사람 찾기 서비스를 활용하는 Microsoft Windows 피어 투 피어 인프라의 간단한 구현입니다. 인터넷 끝점과 연락처의 서비스도 제공할 수 있지만, 주변 사람 찾기 서비스가 작동하는 서브넷에서 피어 지원 응용 프로그램용으로 가장 적합합니다. 연락처 끝점, 가용성 및 현재 상태를 확인하기 위해 Live Messenger 및 기타 Live 인식 응용 프로그램에서 사용하는 일반적인 연락처 관리자를 통합합니다.  
  
-  
  
## <a name="collaboration-applications"></a>공동 작업 응용 프로그램  
 일반적인 피어 투 피어 공동 작업 응용 프로그램은 다음 단계로 구성됩니다.  
  
-   피어는 공동 작업 세션을 호스트하려는 피어의 ID를 판별합니다.  
  
-   세션을 호스트하기 위한 요청을 보내면 호스트 피어가 공동 작업 활동을 관리하도록 동의합니다.  
  
-   호스트에서 서브넷의 연락처(요청자 포함)를 세션에 초대합니다.  
  
-   공동 작업하려는 모든 피어가 해당 연락처 관리자에 호스트를 추가할 수 있습니다.  
  
-   대부분의 피어는 승인 또는 거부 여부에 상관없이 시기적절하게 호스트 피어에게 초대에 대한 응답을 보냅니다.  
  
-   공동 작업하려는 모든 피어는 호스트 피어에 가입합니다.  
  
-   피어가 초기 공동 작업을 수행하는 동안 호스트 피어가 연락처 관리자에 원격 피어를 추가할 수 있습니다. 또한 승인, 거부 및 응답하지 않은 사람을 판별하기 위해 모든 초대 응답도 처리합니다.  응답하지 않은 사람에 대한 초대는 취소하거나 다른 활동을 수행할 수 있습니다.  
  
-   이때 호스트 피어는 초대된 모든 피어와 공동 작업 세션을 시작하거나 응용 프로그램을 공동 작업 인프라에 등록할 수 있습니다.  P2P 응용 프로그램에서는 피어 투 피어 공동 작업 인프라와 <xref:System.Net.PeerToPeer.Collaboration> 네임스페이스를 사용하여 게임, 게시판, 회의 및 기타 서버가 없는 현재 상태 응용 프로그램의 통신을 조정합니다.  
  
-  
  
## <a name="peer-to-peer-networking-security"></a>피어 투 피어 네트워킹 보안  
 Active Directory 도메인에서 도메인 컨트롤러는 Kerberos를 사용하여 인증 서비스를 제공합니다. 서버 없는 피어 환경에서 피어는 자체 인증을 제공해야 합니다. 피어 투 피어 네트워킹의 경우 노드는 CA 역할을 수행할 수 있으므로, 각 피어의 신뢰할 수 있는 루트 저장소에서 루트 인증서의 요구 사항을 제거합니다. 인증은 X.509 인증서 형식의 자체 서명된 인증서를 사용하여 제공됩니다. 이러한 인증서는 공개 키/개인 키 쌍을 생성하고 개인 키를 사용하여 서명된 인증서를 생성하는 각 피어가 만듭니다. 자체 서명된 인증서는 피어 엔터티에 대한 정보를 제공하고 인증을 위해 사용됩니다. X.509 인증과 마찬가지로 피어 네트워킹 인증은 신뢰할 수 있는 공개 키로 다시 추적되는 일련의 인증서를 사용합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Net.PeerToPeer.Collaboration>  
 [System.Net.PeerToPeer.Collaboration 네임스페이스 정보](../../../docs/framework/network-programming/about-the-system-net-peertopeer-collaboration-namespace.md)
