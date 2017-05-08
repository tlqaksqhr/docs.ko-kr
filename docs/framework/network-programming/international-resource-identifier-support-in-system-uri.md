---
title: "System.Uri의 국가별 리소스 식별자 지원 | Microsoft Docs"
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
ms.assetid: b5e994c3-3535-4aff-8e1b-b69be22e9a22
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# System.Uri의 국가별 리소스 식별자 지원
<xref:System.Uri?displayProperty=fullName> 클래스가 확장 되었습니다 국제 자원 식별자 \(IRI\)와 다국어 도메인 이름 \(IDN\) 지원 합니다.  이러한 향상 된이 기능은.NET Framework 3.5, 3.0 SP1 및 2.0 s p 1에서 사용할 수 있습니다.  
  
## IRI 및 IDN 지원  
 웹 주소 식별자 \(매우 제한 된 문자 집합으로 구성 된 URI\)을 사용 하 여 일반적으로 표현 됩니다.  
  
-   영어 알파벳의 대문자 및 소문자 ASCII 문자  
  
-   0에서 9까지의 숫자  
  
-   몇 가지 다른 ASCII 기호  
  
 URI 사양은 IETF\(Internet Engineering Task Force\)에서 게시한 RFC 2396 및 RFC 3986에 문서화되어 있습니다.  
  
 인터넷의 발전과 함께 영어 이외의 언어를 사용하여 리소스를 식별해야 할 필요성도 점점 크게 부각되고 있습니다.  이러한 필요에 부응하여 ASCII 문자가 아닌 문자\(Unicode\/ISO 10646 문자 집합의 문자\)를 허용하는 식별자가 바로 IRI\(International Resource Identifier\)입니다.  IRI 사양은 IETF에서 게시한 RFC 3987에 문서화되어 있습니다.  IRI를 사용하면 URL에 유니코드 문자를 포함할 수 있습니다.  
  
 기존 <xref:System.Uri?displayProperty=fullName> 클래스가 RFC 3987에 따라 IRI를 지원 하도록 확장 되었습니다.  IRI를 사용하도록 명확하게 설정하지 않을 경우 .NET Framework 2.0 동작의 어떠한 변경도 현재 사용자에게 표시되지 않습니다.  이를 통해 .NET Framework의 이전 버전과의 응용 프로그램 호환성을 유지할 수 있습니다.  
  
 응용 프로그램 국제화 도메인 이름 \(IDN\) 도메인 이름에 적용 된 구문 분석을 사용할지 여부와 IRI 구문 분석 규칙 적용 여부를 지정할 수 있습니다.  machine.config 또는 app.config 파일에서 이 작업을 수행할 수 있습니다.  
  
 IDN을 사용하도록 설정하면 도메인 이름의 모든 유니코드 레이블은 동등한 Punycode 항목으로 변환됩니다.  Punycode 이름은 ASCII 문자만 포함하고 항상 xn\-\- 접두사로 시작합니다.  이는 대부분의 DNS 서버가 ASCII 문자만 지원하므로\(RFC 3940 참조\) 인터넷에서 기존 DNS 서버를 지원하기 위해서입니다.  
  
 IRI와 IDN을 사용하도록 설정하면 <xref:System.Uri.DnsSafeHost%2A?displayProperty=fullName> 속성 값이 영향을 받습니다.  IRI 및 IDN을 사용 하면 동작을 변경할 수 있습니다 또한는 <xref:System.Uri.Equals%2A?displayProperty=fullName>, <xref:System.Uri.OriginalString%2A?displayProperty=fullName>, <xref:System.Uri.GetComponents%2A?displayProperty=fullName>, 및 <xref:System.Uri.IsWellFormedOriginalString%2A> 방법.  
  
 IRI 및 IDN을 지원하는 사용자 지정할 수 있는 파서를 만들 수 있도록 <xref:System.GenericUriParser?displayProperty=fullName> 클래스도 확장되었습니다.  <xref:System.GenericUriParser?displayProperty=fullName> 개체의 동작은 <xref:System.GenericUriParserOptions?displayProperty=fullName> 열거형에서 사용할 수 있는 값의 비트 조합을 <xref:System.GenericUriParser?displayProperty=fullName> 생성자에 전달하여 지정합니다.  <xref:System.GenericUriParserOptions?displayProperty=fullName> 형식은 파서가 RFC 3987의 IRI\(International Resource Identifier\)에 지정된 구문 분석 규칙을 지원함을 나타냅니다.  IRI가 실제로 사용 되는지 여부에 따라 IRI를 사용 하는 경우 다릅니다.  
  
 <xref:System.GenericUriParserOptions?displayProperty=fullName> 형식은 파서가 호스트 이름에 대한 IDN\(Internationalized Domain Name\) 구문 분석을 지원함을 나타냅니다.  IDN이 실제로 사용 되는지 여부에 따라 IDN을 사용 하는 경우 다릅니다.  
  
 IRI를 사용 하면 구문 분석 표준화 수행 됩니다 및 RFC 3987의 최신 IRI에 따라 검사 문자 규칙.  기본값은 iri RFC 2396 및 RFC 3986에 따라 정규화 및 문자 검사 수행 되지 않도록 해제 하려면 구문 분석 됩니다.  
  
 IRI 및 IDN 처리에 <xref:System.Uri?displayProperty=fullName> 클래스도 제어할 수 있습니다 사용 하는 <xref:System.Configuration.IriParsingElement?displayProperty=fullName> 및 <xref:System.Configuration.IdnElement?displayProperty=fullName> 구성 설정 클래스.  <xref:System.Configuration.IriParsingElement?displayProperty=fullName> 설정은 <xref:System.Uri?displayProperty=fullName> 클래스에서의 IRI 처리를 설정하거나 해제합니다.  <xref:System.Configuration.IdnElement?displayProperty=fullName> 설정은 <xref:System.Uri> 클래스에서의 IDN 처리를 설정하거나 해제합니다.  <xref:System.Configuration.IriParsingElement?displayProperty=fullName> 설정도 IDN을 간접적으로 제어합니다.  IRI 처리를 사용해야 IDN 처리가 가능합니다.  IRI 처리를 사용하지 않는 경우, IDN 처리는 호환성을 위해 .NET Framework 2.0 동작을 사용하고 IDN 이름은 사용하지 않는 기본 설정으로 설정됩니다.  
  
 구성 설정에는 <xref:System.Configuration.IriParsingElement?displayProperty=fullName> 및 <xref:System.Configuration.IdnElement?displayProperty=fullName> 구성 클래스는 읽기 한 번 때 첫 번째 <xref:System.Uri?displayProperty=fullName> 클래스는 생성.  해당 시간 이후의 구성 설정 변경 내용은 무시됩니다.  
  
## 참고 항목  
 <xref:System.Configuration.IdnElement?displayProperty=fullName>   
 <xref:System.Configuration.IriParsingElement?displayProperty=fullName>   
 <xref:System.Uri?displayProperty=fullName>   
 <xref:System.Uri.DnsSafeHost%2A?displayProperty=fullName>