---
title: "WebRequest에서 파생 | Microsoft Docs"
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
  - "WebRequest 클래스, 플러그형 프로토콜"
  - "프로토콜별 요청 처리기"
  - "데이터 보내기, 플러그형 프로토콜"
  - "플러그형 프로토콜, 클래스 조건"
  - "인터넷, 플러그형 프로토콜"
  - "데이터 받기, 플러그형 프로토콜"
  - "프로토콜, 플러그형"
ms.assetid: 9810c177-973e-43d7-823c-14960bd625ea
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 7
---
# WebRequest에서 파생
<xref:System.Net.WebRequest> 클래스는.NET Framework 플러그형 프로토콜 모델에 맞는 프로토콜 관련 요청 처리기를 만들기 위한 기본 메서드 및 속성을 제공 하는 추상 기본 클래스입니다.  사용 하는 응용 프로그램은  **WebRequest** 클래스는 지원 되는 프로토콜 없이 사용 되는 프로토콜을 지정 하 여 데이터를 요청할 수 있습니다.  
  
 플러그형 프로토콜로 사용 하는 프로토콜 관련 클래스를 두 조건을 충족 해야: 클래스를 구현 해야는 <xref:System.Net.IWebRequestCreate> 인터페이스 및 해당 해야 등록에 <xref:System.Net.WebRequest.RegisterPrefix%2A?displayProperty=fullName> 메서드.  클래스의 모든 추상 메서드 및 속성을 재정의 해야  **WebRequest** 플러그형 인터페이스를 제공 합니다.  
  
 **WebRequest** 인스턴스 1 회 사용 합니다; 의도 된 다른 요청을 만들려면 새로 만들기  **WebRequest**.  **WebRequest** 지원의 <xref:System.Runtime.Serialization.ISerializable> 개발자가 템플릿을 serialize 하도록 인터페이스  **WebRequest** 및 추가 요청에 대 한 서식 파일을 다시 만들.  
  
## IWebRequest 메서드 만들기  
 <xref:System.Net.IWebRequestCreate.Create%2A> 메서드는 프로토콜 관련 클래스의 새 인스턴스를 초기화 합니다.  새 때  **WebRequest** 작성 되는 <xref:System.Net.WebRequest.Create%2A?displayProperty=fullName> 일치 하는 메서드가 요청 된 URI는 URI 접두사를 등록은  **RegisterPrefix** 메서드.  **만들기** 메서드가 올바른 프로토콜 관련 하위 항목을 반환 해야 인스턴스 하위 항목의 초기화는 프로토콜 관련 필드를 수정 하지 않고도 프로토콜에 대 한 표준 요청\/응답 트랜잭션을 수행할 수 있습니다.  
  
## 요소로  
 <xref:System.Net.WebRequest.ConnectionGroupName%2A> 속성 단일 연결을 통해 여러 요청 수 있도록 리소스 연결 그룹에 이름을 지정 하는 데 사용 됩니다.  연결 공유를 구현 하려면 풀링 및 연결 할당 프로토콜 관련 메서드를 사용 해야 합니다.  예를 들어,를 제공 <xref:System.Net.ServicePointManager> 클래스 구현에 대 한 공유 연결을 <xref:System.Net.HttpWebRequest> 클래스.  **ServicePointManager** 클래스를 만듭니다는 <xref:System.Net.ServicePoint> 각 연결 그룹에는 특정 서버에 연결을 제공 합니다.  
  
## ContentLength 속성  
 <xref:System.Net.WebRequest.ContentLength%2A> 속성에 데이터를 업로드할 때 서버에 보낼 데이터의 바이트 수를 지정 합니다.  
  
 일반적으로 <xref:System.Net.WebRequest.Method%2A> 업로드 되었는지 나타내는 속성 설정 해야 경우 배치는  **ContentLength** 속성 설정 값을 0 보다 큰.  
  
## ContentType 속성  
 <xref:System.Net.WebRequest.ContentType%2A> 속성 프로토콜 보내는 콘텐츠 유형을 식별 하는 서버에 보내려면 해야 특별 한 정보를 제공 합니다.  일반적으로이 업로드 되는 데이터의 MIME 콘텐츠 형식을입니다.  
  
## 자격 증명 속성  
 <xref:System.Net.WebRequest.Credentials%2A> 속성 서버와 요청을 인증 하는 데 필요한 정보를 포함 합니다.  프로토콜에 대 한 인증 프로세스의 세부 사항을 구현 해야 합니다.  <xref:System.Net.AuthenticationManager> 클래스는 요청을 인증 하 고 인증 토큰을 제공 합니다.  프로토콜에 의해 사용 되는 자격 증명을 제공 하는 클래스를 구현 해야는 <xref:System.Net.ICredentials> 인터페이스.  
  
## 헤더 속성  
 <xref:System.Net.WebRequest.Headers%2A> 속성에는 임의의 컬렉션 요청과 관련 된 메타 데이터의 이름\/값 쌍을 포함 합니다.  이름\/값 쌍으로 포함 될 수 있는 대로 표현할 수 있는 프로토콜에 필요한 모든 메타 데이터는  **헤더** 속성.  일반적으로이 정보 호출 하기 전에 설정 해야는 <xref:System.Net.WebRequest.GetRequestStream%2A> 또는 <xref:System.Net.WebRequest.GetResponse%2A> 메서드; 요청을 보낸 후에 메타 데이터를 읽기 전용으로 간주 됩니다.  
  
 사용 하지 않아도  **헤더** 헤더 메타 데이터를 사용 하는 속성입니다.  프로토콜 관련 메타 데이터는 속성으로 노출 될 수 있습니다. 예를 들어 있는 <xref:System.Net.HttpWebRequest.UserAgent%2A?displayProperty=fullName> 속성 노출의  **사용자 에이전트**  HTTP 헤더.  헤더 메타 데이터를 속성으로 노출할 경우 동일한 속성을 사용 하 여 설정할 수를 허용 해야는  **헤더** 속성.  
  
## 속성 메서드  
 <xref:System.Net.WebRequest.Method%2A> 동사 또는 서버가 수행 하는 요청을 요청 하는 작업 속성을 포함 합니다.  기본값은  **메서드** 속성 해야 사용 표준 요청\/응답 작업 프로토콜 관련 속성을 설정할 수 없어도.  예를 들어,는  [HttpWebResponse](frlrfSystemNetHttpWebResponseClassMethodTopic) 메서드는 웹 서버에서 리소스를 요청 하 고 응답을 반환 하는 GET에 기본값입니다.  
  
 일반적으로  **ContentLength** 속성 설정 되어야 하는 값 0 때 보다 큰의  **메서드** 속성 동사 또는 업로드 수행 사실을 나타내는 동작을 설정 합니다.  
  
## 속성을 미리 인증 하는지  
 응용 프로그램 설정의 <xref:System.Net.WebRequest.PreAuthenticate%2A> 초기 요청과 함께 인증 정보를 나타내는 속성 보내야 인증 챌린지를 기다리지 않고.  **PreAuthenticate** 속성을 초기 요청과 함께 전송 되는 인증 자격 증명의 프로토콜을 지 원하는 경우에 의미입니다만.  
  
## 프록시 속성  
 <xref:System.Net.WebRequest.Proxy%2A> 속성에 포함 된 <xref:System.Net.IWebProxy> 요청 된 리소스에 액세스 하는 데 사용 되는 인터페이스.  **프록시** 속성 프로토콜 프록시 요청 지원할 경우에 의미가 있습니다.  한 프로토콜을 통해 요청 하는 경우 기본 프록시를 설정 해야 합니다.  
  
 일부 환경에서와 같이 기업 방화벽 프로토콜 프록시를 사용 하도록 필요할 수 있습니다.  구현 해야 경우에  **IWebProxy** 인터페이스를 작동 하는 프로토콜에 대 한 프록시 클래스를 만들려면.  
  
## RequestUri 속성  
 <xref:System.Net.WebRequest.RequestUri%2A> 속성에 전달 된 URI에 포함 된  **WebRequest.Create** 메서드.  읽기만 가능 하 고 한 번에 변경할 수 없습니다를  **WebRequest** 만들었습니다.  리디렉션 기능을 지 원하는 프로토콜 응답 다른 URI로 식별 되는 리소스를 가져올 수 있습니다.  응답 한 URI에 대 한 액세스를 제공 하는 경우 해당 URI를 포함 하는 추가 속성을 제공 해야 합니다.  
  
## Timeout 속성  
 <xref:System.Net.WebRequest.Timeout%2A> 속성에서 요청 시간 초과 예외를 throw 하기 전에 대기할 시간 \(밀리초\), 시간을 포함 합니다.  **시간 제한** 만 동기 요청에 적용 되는 <xref:System.Net.WebRequest.GetResponse%2A> 메서드도 있습니다. 비동기 요청을 사용 해야 하는 <xref:System.Net.WebRequest.Abort%2A> 메서드는 보류 중인 요청을 취소 합니다.  
  
 설정의  **시간 초과** 속성만 프로토콜 관련 클래스에서 시간 제한 프로세스를 구현 하는 경우에 의미입니다.  
  
## Abort 메서드  
 <xref:System.Net.WebRequest.Abort%2A> 메서드는 서버에 보류 중인 비동기 요청을 취소 합니다.  요청이 취소 된 후에 호출  **GetResponse**,  **BeginGetResponse**,  **EndGetResponse**,  **GetRequestStream**,  **BeginGetRequestStream**, 또는  **EndGetRequestStream** throw 됩니다는 <xref:System.Net.WebException> 에 <xref:System.Net.WebException.Status%2A> 속성을 설정  [RequestCanceled](frlrfSystemNetWebExceptionStatusClassTopic).  
  
## EndGetRequestStream 메서드와 BeginGetRequestStream  
 <xref:System.Net.WebRequest.BeginGetRequestStream%2A> 메서드는 데이터를 서버에 업로드 하는 데 사용 되는 스트림에 대 한 비동기 요청을 시작 합니다.  <xref:System.Net.WebRequest.EndGetRequestStream%2A> 메서드 비동기 요청을 완료 하 고 요청 된 스트림을 반환 합니다.  이러한 메서드를 구현 된  **GetRequestStream**  .NET Framework 표준 비동기 패턴을 사용 하는 방법.  
  
## BeginGetResponse 및 EndGetResponse 메서드  
 <xref:System.Net.WebRequest.BeginGetResponse%2A> 메서드는 서버로 비동기 요청을 시작 합니다.  <xref:System.Net.WebRequest.EndGetResponse%2A> 메서드 비동기 요청을 완료 하 고 요청 된 응답을 반환 합니다.  이러한 메서드를 구현 된  **GetResponse**  .NET Framework 표준 비동기 패턴을 사용 하는 방법.  
  
## GetRequestStream 메서드  
 <xref:System.Net.WebRequest.GetRequestStream%2A> 메서드는 요청한 서버에 데이터를 쓰는 데 사용 되는 스트림을 반환 합니다.  반환 되는 스트림에 검색 하지 않습니다 쓰기 전용 스트림 있어야 합니다. 로 서버에 기록 되는 데이터의 단방향 스트림을 위한 것입니다.  스트림에 대해 false를 반환의 <xref:System.IO.Stream.CanRead%2A> 및 <xref:System.IO.Stream.CanSeek%2A> 속성과 true는 <xref:System.IO.Stream.CanWrite%2A> 속성.  
  
 **GetRequestStream** 메서드는 일반적으로 서버 연결할 엽니다 및 스트림을 반환 하기 전에 해당 데이터를 나타내는 전송 헤더 정보는 서버로 전송 되는.  때문에  **GetRequestStream** 시작 설정 요청을  **헤더** 속성 또는  **ContentLength** 속성은 일반적으로 허용 되지 않습니다 호출한 후  **GetRequestStream**.  
  
## GetResponse 메서드  
 <xref:System.Net.WebRequest.GetResponse%2A> 메서드는 프로토콜 관련 하위 항목을 반환의 <xref:System.Net.WebResponse> 서버 로부터 응답을 나타내는 클래스입니다.  요청 하면 이미 시작 된 경우를 제외는  **GetRequestStream** 메서드는  **GetResponse** 메서드에 의해 식별 되는 리소스는 연결을 만듭니다  **RequestUri**헤더 정보가 변경 되는 요청 된 형식을 나타내는 보내고 다음 리소스에서 응답을 받습니다.  
  
 한 번은  **GetResponse** 메서드를 호출 하 고 모든 속성 읽기 전용으로 간주 해야 합니다.  **WebRequest** 인스턴스 1 회 사용 합니다; 의도 된 다른 요청을 하려면 새로 만들어야  **WebRequest**.  
  
 **GetResponse** 메서드는 적절 한 만드는 것  **WebResponse** 하위 들어오는 응답을 포함 합니다.  
  
## 참고 항목  
 <xref:System.Net.WebRequest>   
 <xref:System.Net.HttpWebRequest>   
 <xref:System.Net.FileWebRequest>   
 [플러그형 프로토콜 프로그래밍](../../../docs/framework/network-programming/programming-pluggable-protocols.md)   
 [WebResponse에서 파생](../../../docs/framework/network-programming/deriving-from-webresponse.md)