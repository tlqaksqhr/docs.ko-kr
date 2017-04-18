---
title: "HttpTransportBindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 088a7bce-6bb2-4839-ad74-f68d4b1aa0f9
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# HttpTransportBindingElement
HttpTransportBindingElement  
  
## 구문  
  
```  
class HttpTransportBindingElement : TransportBindingElement  
{  
  boolean AllowCookies;  
  string AuthenticationScheme;  
  boolean BypassProxyOnLocal;  
  string HostNameComparisonMode;  
  boolean KeepAliveEnabled;  
  sint32 MaxBufferSize;  
  string ProxyAddress;  
  string ProxyAuthenticationScheme;  
  string Realm;  
  string TransferMode;  
  boolean UnsafeConnectionNtlmAuthentication;  
  boolean UseDefaultWebProxy;  
};  
```  
  
## 메서드  
 HttpTransportBindingElement 클래스는 메서드를 정의하지 않습니다.  
  
## 속성  
 HttpTransportBindingElement 클래스에는 다음과 같은 속성이 있습니다.  
  
### AllowCookies  
 데이터 형식: boolean  
  
 액세스 형식: 읽기 전용  
  
 클라이언트가 쿠키를 수락하고 이를 앞으로의 요청에서 전파할지 여부를 나타내는 값입니다.  
  
### AuthenticationScheme  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 HTTP 수신기가 처리하는 클라이언트 요청을 인증하는 데 사용되는 인증 스키마입니다.  
  
### BypassProxyOnLocal  
 데이터 형식: boolean  
  
 액세스 형식: 읽기 전용  
  
 로컬 주소의 프록시를 무시할지 여부를 나타내는 값입니다.  
  
### HostNameComparisonMode  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 URI를 일치시킬 때 서비스에 연결하기 위해 호스트 이름이 사용되는지 여부를 나타내는 값입니다.  
  
### KeepAliveEnabled  
 데이터 형식: boolean  
  
 액세스 형식: 읽기 전용  
  
 선택하면 동작 수준에 상관없이 HTTP 연결이 유지됩니다.  
  
### MaxBufferSize  
 데이터 형식: sint32  
  
 액세스 형식: 읽기 전용  
  
 버퍼 풀의 최대 크기입니다.  
  
### ProxyAddress  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 HTTP 요청에 사용할 프록시의 주소를 포함하는 URI입니다.  
  
### ProxyAuthenticationScheme  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 HTTP 프록시가 처리하는 클라이언트 체계를 인증하는 데 사용되는 인증 스키마입니다.  
  
### Realm  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 인증 영역입니다.  
  
### TransferMode  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 메시지가 버퍼링되거나 스트리밍되는지 또는 요청이나 응답인지 지정하는 값입니다.  
  
### UnsafeConnectionNtlmAuthentication  
 데이터 형식: boolean  
  
 액세스 형식: 읽기 전용  
  
 서버에서 안전하지 않은 연결 공유를 사용할 수 있는지 여부를 나타내는 값입니다.  
  
### UseDefaultWebProxy  
 데이터 형식: boolean  
  
 액세스 형식: 읽기 전용  
  
 사용자별 설정이 아닌 시스템 수준의 프록시 설정을 사용할지 여부를 나타내는 값입니다.  
  
## 요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|----------------------------------|  
|네임스페이스|root\\ServiceModel에 정의되어 있습니다.|  
  
## 참고 항목  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>