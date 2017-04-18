---
title: "연결 관리 | Microsoft Docs"
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
  - "HTTP, 연결을 위한 클래스"
  - "인터넷에서 데이터 요청, 연결"
  - "데이터 보내기, 연결"
  - "데이터 받기, 연결"
  - "ServicePoint 클래스, ServicePoint 클래스"
  - "인터넷 요청에 대한 응답, 연결"
  - "연결[.NET Framework], 클래스"
  - "네트워크 리소스, 연결"
  - "인터넷 리소스 다운로드, 연결"
  - "ServicePointManager 클래스, ServicePointManager 클래스 정보"
ms.assetid: 9b3d3de7-189f-4f7d-81ae-9c29c441aaaa
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# 연결 관리
HTTP를 사용 하 여 데이터 리소스에 연결 하는 응용 프로그램의.NET Framework 사용할 수 있는 <xref:System.Net.ServicePoint> 및 <xref:System.Net.ServicePointManager> 최적 배율 및 성능을 얻을 수 있도록 하 고 인터넷 연결을 관리 하는 클래스입니다.  
  
 **ServicePoint** 응용 프로그램 끝점을 응용 프로그램에 연결할 수 있습니다 인터넷 리소스에 액세스할 수 있는 클래스를 제공 합니다.  각  **ServicePoint** 통해 성능을 향상 시키는 연결 간에 최적화 정보를 공유 하 여 인터넷 서버와 연결을 최적화 하는 정보가 들어 있습니다.  
  
 각  **ServicePoint** 동일한 리소스 식별자 \(URI\)로 식별 되 고 체계 식별자 및 호스트 조각의 URI에 따라 분류 됩니다.  예를 들어, 동일한  **ServicePoint** 인스턴스 요청 Uri http:\/\/www.contoso.com\/index.htm 및 http:\/\/www.contoso.com\/news.htm?date\=today 제공 같은 체계 식별자 \(http\) 및 호스트 \(www.contoso.com\) 조각 들 때문입니다.  이미 응용 프로그램이 서버 www.contoso.com에 영구 연결 되어 있으면 해당 연결을 사용 하 여 두 개의 연결을 만들 필요 없이 요청을 검색할 수 있습니다.  
  
 **ServicePointManager** 의 생성 및 소멸을 관리 하는 정적 클래스는  **ServicePoint** 인스턴스.  **ServicePointManager** 생성 한  **ServicePoint** 응용 프로그램의 기존 컬렉션에는 인터넷 리소스를 요청할 때  **ServicePoint** 인스턴스.  **ServicePoint** 인스턴스는 소멸은 최대 유휴 시간 초과 또는 때 기존  **ServicePoint** 인스턴스의 최대 수가 초과  **ServicePoint** 인스턴스 응용 프로그램.  모두 기본 최대 유휴 시간 및 최대 개수를 제어할 수 있습니다  **ServicePoint**  를 설정 하 여 인스턴스는 <xref:System.Net.ServicePointManager.MaxServicePointIdleTime%2A> 및 <xref:System.Net.ServicePointManager.MaxServicePoints%2A> 속성에는  **ServicePointManager**.  
  
 클라이언트와 서버 간의 연결 수를 응용 프로그램의 처리량에 크게 영향을 가질 수 있습니다.  기본적으로 사용 하 여 응용 프로그램의 <xref:System.Net.HttpWebRequest> 클래스는 지정 된 서버에 영구 연결을 두 최대 사용 하지만 각 응용 프로그램 별로 최대 연결 수를 설정할 수 있습니다.  
  
> [!NOTE]
>  HTTP\/1.1 사양 서버당 2 개의 연결 응용 프로그램에서 연결 수를 제한합니다.  
  
 최적의 연결 수는 응용 프로그램이 실행 되는 실제 조건에 따라 달라 집니다.  응용 프로그램에 사용할 수 있는 연결 개수를 늘리면 응용 프로그램 성능에 영향을 수 있습니다.  더 많은 연결의 영향을 확인 하려면 연결 수를 변경 하는 동안 성능 테스트를 실행 합니다.  정적을 변경 하 여 응용 프로그램을 사용 하 여 연결 수를 변경할 수 있습니다 <xref:System.Net.ServicePointManager.DefaultConnectionLimit%2A> 속성에는  **ServicePointManager** 는 다음 코드 예제 에서처럼 응용 프로그램 초기화 시 클래스.  
  
```csharp  
// Set the maximum number of connections per server to 4.  
ServicePointManager.DefaultConnectionLimit = 4;  
```  
  
```vb  
' Set the maximum number of connections per server to 4.  
ServicePointManager.DefaultConnectionLimit = 4  
```  
  
 변경 된  **ServicePointManager.DefaultConnectionLimit** 속성 초기화 이전에 미치지 않습니다  **ServicePoint** 인스턴스.  다음 코드에서 기존 연결 제한을 변경 하는 방법을 보여 줍니다  **ServicePoint** 는 서버 http:\/\/www.contoso.com에 저장 된 값에 대 한 `newLimit`.  
  
```csharp  
Uri uri = new Uri("http://www.contoso.com/");  
ServicePoint sp = ServicePointManager.FindServicePoint(uri);  
sp.ConnectionLimit = newLimit;  
```  
  
```vb  
Dim uri As New Uri("http://www.contoso.com/")  
Dim sp As ServicePoint = ServicePointManager.FindServicePoint(uri)  
sp.ConnectionLimit = newLimit  
```  
  
## 참고 항목  
 [연결 그룹화](../../../docs/framework/network-programming/connection-grouping.md)   
 [응용 프로그램 프로토콜 사용](../../../docs/framework/network-programming/using-application-protocols.md)