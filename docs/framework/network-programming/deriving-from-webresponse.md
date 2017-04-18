---
title: "WebResponse에서 파생 | Microsoft Docs"
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
  - "WebResponse에서 파생"
ms.assetid: f11d4866-a199-4087-9306-a5a4c18b13db
caps.latest.revision: 7
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 7
---
# WebResponse에서 파생
<xref:System.Net.WebResponse> 클래스는.NET Framework 플러그형 프로토콜 모델에 맞는 프로토콜 관련 응답 만들기 위한 기본 메서드 및 속성을 제공 하는 추상 기본 클래스입니다.  사용 하는 응용 프로그램은 <xref:System.Net.WebRequest> 리소스에서 클래스 데이터 요청에 응답을 받을  **WebResponse**.  프로토콜별  **WebResponse** 하위 추상 멤버를 구현 해야 하는  **WebResponse** 클래스입니다.  
  
 연결 된  **WebRequest** 클래스를 만들어야  **WebResponse** 하위 항목.  예를 들어, <xref:System.Net.HttpWebResponse> 인스턴스 호출 결과로 만들어지는 <xref:System.Net.HttpWebRequest.GetResponse%2A?displayProperty=fullName> 또는 <xref:System.Net.HttpWebRequest.EndGetResponse%2A?displayProperty=fullName>.  각  **WebResponse** 리소스 요청 결과 포함 하 고 다시 사용할 수는 없습니다.  
  
## ContentLength 속성  
 <xref:System.Net.WebResponse.ContentLength%2A> 반환한 스트림에서 사용할 수 있는 데이터의 바이트 수를 나타내는 속성은 <xref:System.Net.WebResponse.GetResponseStream%2A> 메서드.  **ContentLength** 속성 헤더 또는 메타 데이터 정보를 반환 합니다; 서버에서 바이트 수를 표시 하지 않습니다 요청 된 리소스에 있는 데이터의 바이트 수만을 나타냅니다.  
  
## ContentType 속성  
 <xref:System.Net.WebResponse.ContentType%2A> 속성 프로토콜을 서버에서 보내는 콘텐츠의 형식을 식별 하는 클라이언트에 보내려면 필요한 특수 정보를 제공 합니다.  일반적으로이 반환 된 데이터의 MIME 콘텐츠 형식을입니다.  
  
## 헤더 속성  
 <xref:System.Net.WebResponse.Headers%2A> 속성에는 응답과 관련 된 메타 데이터의 이름\/값 쌍의 임의의 컬렉션 포함 합니다.  이름\/값 쌍으로 포함 될 수 있는 대로 표현할 수 있는 프로토콜에 필요한 모든 메타 데이터는  **헤더** 속성.  
  
 사용 하지 않아도  **헤더** 헤더 메타 데이터를 사용 하는 속성입니다.  프로토콜 관련 메타 데이터는 속성으로 노출 될 수 있습니다. 예를 들어 있는 <xref:System.Net.HttpWebResponse.LastModified%2A?displayProperty=fullName> 속성 노출의  **최종 수정일** HTTP 헤더.  헤더 메타 데이터를 속성으로 노출할 경우 동일한 속성을 사용 하 여 설정할 수를 허용 해야는  **헤더** 속성.  
  
## ResponseUri 속성  
 <xref:System.Net.WebResponse.ResponseUri%2A> 속성 실제로 응답을 제공 하는 리소스의 URI를 포함 합니다.  리디렉션을 지원 하지 않는 프로토콜에 대 한  **ResponseUri** 와 같습니다는 <xref:System.Net.WebRequest.RequestUri%2A> 속성의는  **WebRequest** 응답을 생성 합니다.  요청을 리디렉션하는 프로토콜을 지 원하는 경우  **ResponseUri** URI의 응답을 포함 합니다.  
  
## 메서드를 닫습니다.  
 <xref:System.Net.WebResponse.Close%2A> 메서드 요청 및 응답에 대 한 연결을 닫고 응답에 사용 된 리소스를 정리 합니다.  **닫기** 메서드는 응답에서 사용 되는 스트림 인스턴스 닫습니다 있지만 응답 스트림에 이전 호출에 의해 닫힌 경우 예외를 throw 하지는 <xref:System.IO.Stream.Close%2A?displayProperty=fullName> 메서드.  
  
## GetResponseStream 메서드  
 <xref:System.Net.WebResponse.GetResponseStream%2A> 메서드는 응답에서 요청 된 리소스가 포함 된 스트림을 반환 합니다.  응답 스트림에 리소스에서 반환 된 데이터를만 포함 되어 있습니다. 모든 헤더 또는 응답에 포함 된 메타 데이터에서 응답을 제거 고 프로토콜 관련 속성을 통해 응용 프로그램에 노출 되어야 또는  **헤더** 속성.  
  
 스트림 인스턴스를 반환 하는  **GetResponseStream** 메서드는 응용 프로그램에서 소유 하 고 닫는 하지 않고 닫을 수 있습니다는  **WebResponse**.  규칙에 따라, 호출 하는  **WebResponse.Close** 메서드는 또한 반환 스트림 닫습니다  **GetResponse**.  
  
## 참고 항목  
 <xref:System.Net.WebResponse>   
 <xref:System.Net.HttpWebResponse>   
 <xref:System.Net.FileWebResponse>   
 [플러그형 프로토콜 프로그래밍](../../../docs/framework/network-programming/programming-pluggable-protocols.md)   
 [WebRequest에서 파생](../../../docs/framework/network-programming/deriving-from-webrequest.md)