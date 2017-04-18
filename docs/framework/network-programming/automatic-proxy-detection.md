---
title: "자동 프록시 검색 | Microsoft Docs"
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
  - "자동 프록시 검색"
  - "웹 프록시 자동 검색"
  - "웹 프록시"
  - "자동으로 프록시 검색"
  - "웹 프록시 클래스, 자동 프록시 검색"
  - "프록시, 자동으로 검색"
  - "네트워크"
  - "WPAD(웹 프록시 자동 검색)"
ms.assetid: fcd9c3bd-93de-4c92-8ff3-837327ad18de
caps.latest.revision: 18
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 18
---
# 자동 프록시 검색
자동 프록시 검색 웹 프록시 서버는 시스템에서 식별 하 여 클라이언트를 대신 하 여 요청을 보내는 데 사용 되는 프로세스입니다.  이 기능을 WPAD\(Web Proxy Auto\-Discovery\)라고도 합니다.  자동 프록시 검색을 사용 하면 시스템 요청에 대해 사용할 수 있는 프록시 집합을 반환 해야 하는 프록시 구성 스크립트를 찾을 시도 합니다.  프록시 구성 스크립트를 찾을 경우 스크립트 다운로드, 컴파일, 및 사용에 대 한 요청 프록시 정보, 요청 스트림 또는 응답을 가져올 때는 로컬 컴퓨터에서 실행 된 <xref:System.Net.WebProxy> 인스턴스.  
  
 자동 프록시 검색을 수행 하는 <xref:System.Net.WebProxy> 클래스와 구성 파일의 설정을 요청 수준 설정 및 Internet Explorer 사용 하 여 지정 된 설정을 사용할 수 있습니다  **로컬 영역 네트워크 \(LAN\)** 대화 상자.  
  
> [!NOTE]
>  Internet Explorer 표시할 수 있습니다  **로컬 영역 네트워크 \(LAN\) 설정** 대화 상자를 선택 하 여  **도구** Internet Explorer 주 메뉴 및 다음 선택에서  **인터넷 옵션**.  그런 다음 선택은  **연결** 탭을 클릭 하 고  **LAN 설정**.  
  
 자동 프록시 검색을 사용 하는 경우는 <xref:System.Net.WebProxy> 클래스를 시도 하는 다음과 같이 프록시 구성 스크립트를 찾습니다.  
  
1.  Wininet은 `InternetQueryOption` 함수 Internet Explorer 가장 최근에 검색된 프록시 구성 스크립트를 찾는 데.  
  
2.  스크립트가 있을 경우는 <xref:System.Net.WebProxy> 클래스는 동적 호스트 구성 프로토콜 \(DHCP\)를 사용 하 여 스크립트를 찾습니다.  DHCP 서버 위치 \(호스트 이름\)으로 스크립트 또는 스크립트의 전체 URL로 응답할 수 있습니다.  
  
3.  DHCP의 WPAD 호스트 식별 하지 못할 경우에 WPAD 호스트 이름 또는 별칭으로 DNS는 쿼리 합니다.  
  
4.  호스트 식별 되지 않는 Internet Explorer LAN 설정 또는 구성 파일에서 프록시 구성 스크립트의 위치를 지정 하는 경우이 위치를 사용 합니다.  
  
> [!NOTE]
>  NT 서비스 또는 ASP.NET의 일부로 실행 되는 응용 프로그램 Internet Explorer 프록시 서버 설정 \(사용 가능한 경우\)를 호출 하는 사용자의 사용 합니다.  이러한 설정은 모든 서비스 응용 프로그램에서 사용할 수 있습니다.  
  
 프록시는 각 전화 접속 아이콘이 별로 구성 됩니다.  전화 접속 아이콘이 네트워크 연결 대화 상자에서 항목 이므로 실제 네트워크 장치 \(모뎀 또는 이더넷 카드\) 또는 가상 인터페이스 \(예: 네트워크 장치를 통해 실행 되는 VPN 연결\) 될 수 있습니다.  전화 접속 아이콘이 변경 하면 \(액세스 지점이 나 VPN 사용 예는 무선 연결 변경\) 프록시 검색 알고리즘이 다시 실행 됩니다.  
  
 기본적으로 Internet Explorer 프록시 설정은 프록시 검색에 사용 됩니다.  응용 프로그램이 비 대화형 계정 \(없이 IE 프록시 설정을 구성 하는 편리한 방법\), 또는 IE 설정 보다 다른 프록시 설정을 사용 하려면 구성 파일을 만들어 프록시를 구성할 수 있습니다 경우는 [\<defaultProxy\> 요소\(네트워크 설정\)](../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md) 및 [\<proxy\> 요소\(네트워크 설정\)](../../../docs/framework/configure-apps/file-schema/network/proxy-element-network-settings.md) 에 정의 된 요소.  
  
 만들 요청에 대해 null을 사용 하 여 요청 수준에서 자동 프록시 검색 비활성화할 수 있습니다 <xref:System.Net.WebRequest.Proxy%2A> 다음 코드 예에서 같이 요청을 사용 합니다.  
  
```csharp  
public static void DisableForMyRequest (Uri resource)  
{  
    WebRequest request = WebRequest.Create (resource);  
    request.Proxy = null;  
    WebResponse response = request.GetResponse ();  
}  
```  
  
```vb  
Public Shared Sub DisableForMyRequest(ByVal resource As Uri)  
    Dim request As WebRequest = WebRequest.Create(resource)  
    request.Proxy = Nothing  
    Dim response As WebResponse = request.GetResponse()  
    End Sub   
```  
  
 프록시 없는 요청에서 사용할 수 있는 응용 프로그램 도메인의 기본 프록시를 사용 하 여 <xref:System.Net.WebRequest.DefaultWebProxy%2A> 속성.  
  
## 참고 항목  
 <xref:System.Net.WebProxy>   
 <xref:System.Net.WebRequest>   
 [\<system.Net\> 요소\(네트워크 설정\)](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)