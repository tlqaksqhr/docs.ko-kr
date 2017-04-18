---
title: "인터넷 요청 만들기 | Microsoft Docs"
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
  - "WebRequest 클래스, 데이터 보내기 및 받기"
  - "네트워킹"
  - "HttpWebResponse 클래스, 데이터 보내기 및 받기"
  - "인터넷에서 데이터 요청, 요청 만들기"
  - "네트워크 리소스"
  - "인터넷, 데이터 요청"
  - "데이터 요청, 요청 만들기"
ms.assetid: faab683e-3f1e-4eee-b5e9-59f7245033d5
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# 인터넷 요청 만들기
응용 프로그램을 만드는 <xref:System.Net.WebRequest> 를 통해 인스턴스를 <xref:System.Net.WebRequest.Create%2A?displayProperty=fullName> 메서드.  이 파생 된 클래스를 만드는 정적 메서드인  **WebRequest** 전달 URI 체계를 기반으로 합니다.  
  
## 웹, 파일 및 FTP 요청  
 제공.NET Framework <xref:System.Net.HttpWebRequest> 에서 파생 된 클래스  **WebRequest**, HTTP 및 HTTPS 요청을 처리 합니다.  대부분의 경우에  **WebRequest** 클래스; 요청에 필요한 모든 속성을 제공 합니다. 그러나 필요한 경우 캐스팅할 수  **WebRequest** 만든 개체는  **WebRequest.Create** 메서드에  **HttpWebRequest** 요청의 HTTP 관련 속성에 액세스 합니다.  마찬가지로  **HttpWebResponse** 개체는 HTTP 및 HTTPS 요청에서 응답을 처리 합니다.  HTTP 관련 속성에 액세스 하는  **HttpWebResponse** 개체를 캐스팅 해야  **WebResponse** 개체에  **HttpWebResponse**  형식입니다.  
  
 .NET Framework 제공 된 <xref:System.Net.FileWebRequest> 및 <xref:System.Net.FileWebResponse> 클래스를 사용 하는 리소스에 대 한 요청을 처리 하는 "파일:" URI 체계.  마찬가지로 <xref:System.Net.FtpWebRequest> 및 <xref:System.Net.FtpWebResponse> 클래스 사용 하는 리소스에 대 한 요청을 처리 하도록 제공 되는 "ftp:" 구성표입니다.  이러한 스키마를 사용 하 여 리소스에 대 한 요청이 있으면 수는  **WebRequest.Create** 개체에 요청을 구하는 방법.  
  
 다른 응용 프로그램 수준 프로토콜을 사용 하는 요청을 처리 하려면 프로토콜 관련 클래스에서 파생 된 구현에 필요한  **WebRequest**  및  **WebResponse**.  자세한 내용은  [플러그형 프로토콜 프로그래밍](../../../docs/framework/network-programming/programming-pluggable-protocols.md).  
  
## 참고 항목  
 [방법: WebRequest 클래스를 사용하여 데이터 요청](../../../docs/framework/network-programming/how-to-request-data-using-the-webrequest-class.md)   
 [데이터 요청](../../../docs/framework/network-programming/requesting-data.md)