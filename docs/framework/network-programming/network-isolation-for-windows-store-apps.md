---
title: "Windows 스토어 앱에 대한 네트워크 격리 | Microsoft Docs"
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
ms.assetid: b064497c-d956-46b8-838d-7a0223c7e200
caps.latest.revision: 7
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 7
---
# Windows 스토어 앱에 대한 네트워크 격리
클래스에 <xref:System.Net>, <xref:System.Net.Http>, 및 <xref:System.Net.Http.Headers> 네임 스페이스를 사용 Windows 저장소 응용 프로그램 또는 데스크톱 응용 프로그램을 개발 하는 데.  Windows 저장소 응용 프로그램에서 사용 되 면이 네임 스페이스에서 클래스 네트워크 격리를 사용 하 여 응용 프로그램 보안 모델의 일부 영향을 받습니다에 [!INCLUDE[win8](../../../includes/win8-md.md)].  응용 프로그램 매니페스트에 Windows 저장소 응용 프로그램에 대 한 네트워크 액세스를 허용 하도록 시스템에 대 한 적절 한 네트워크 기능을 활성화 합니다.  
  
## 네트워크 격리를 위한 검사 목록  
 이 검사 목록을 사용 하 여 네트워크 격리 저장소 Windows 응용 프로그램에 대해 구성 되어 있는지 확인 합니다.  
  
1.  응용 프로그램에서 필요한 네트워크 액세스 요청의 방향을 결정 합니다.  이러한 네트워크 요청 유형 중 두 가지를 조합한 수 있습니다이 원하지 않는 인바운드 요청 또는 아웃 바운드 요청 클라이언트에서 시작 될 수 있습니다.  
  
2.  해당 응용 프로그램이 통신할 수 있는 네트워크 리소스를 결정 합니다.  홈 또는 회사 네트워크에서 신뢰할 수 있는 리소스와 통신 하는 응용 프로그램을 해야 합니다.  응용 프로그램에서 인터넷 리소스와 통신 해야 합니다.  응용 프로그램은 두 종류의 네트워크 리소스에 액세스를 해야 합니다.  
  
3.  네트워킹 격리 기능이 필요한 최소 응용 프로그램 매니페스트를 구성 합니다.  
  
4.  배포 및 응용 프로그램 문제 해결을 제공 하는 네트워크 격리 도구를 사용 하 여 테스트를 실행 합니다.  
  
 네트워크 기능 및 네트워크 격리를 해결 하는 데 사용 되는 격리 도구를 구성 하는 방법에 대 한 자세한 내용은 참조 하십시오. [네트워크 격리 기능을 구성 하는 방법](http://go.microsoft.com/fwlink/?LinkID=228265) 에 있는 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 개발자 설명서.  
  
## 참고 항목  
 [웹 서비스에 연결](http://go.microsoft.com/fwlink/?LinkID=245696)   
 [지침 및 네트워크 격리 검사 목록](http://go.microsoft.com/fwlink/?LinkID=228265)   
 [퀵 스타트: Httpclient를 사용 하 여 연결](http://go.microsoft.com/fwlink/?LinkId=245697)   
 [HttpClient 처리기를 사용 하](http://go.microsoft.com/fwlink/?LinkId=245699)   
 [HttpClient 연결 보안을 설정 하는 방법](http://go.microsoft.com/fwlink/?LinkId=245698)   
 [HttpClient 샘플](http://go.microsoft.com/fwlink/?LinkId=242550)