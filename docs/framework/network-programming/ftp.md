---
title: "FTP | Microsoft Docs"
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
  - "FTP"
ms.assetid: 9b43f8b4-89d7-46a7-89fc-71aca916dd32
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# FTP
FTP 프로토콜에 대 한 포괄적인 지원을 제공 하는.NET Framework <xref:System.Net.FtpWebRequest> 및 <xref:System.Net.FtpWebResponse> 클래스입니다.  이러한 클래스에서 파생 된 <xref:System.Net.WebRequest> 및 <xref:System.Net.WebResponse>.  대부분의 경우에 <xref:System.Net.WebRequest> 및 <xref:System.Net.WebResponse> 클래스는 요청을 확인 하는 데 필요한 모든 제공 하지만 속성으로 노출 하는 FTP 관련 기능에 액세스 해야 하는 경우 이러한 클래스를 형식 변환할 수 <xref:System.Net.FtpWebRequest> 또는 <xref:System.Net.FtpWebResponse>.  
  
## 예제  
 자세한 내용은 다음 항목을 참조 하십시오: [방법: FTP를 사용하여 파일 다운로드](../../../docs/framework/network-programming/how-to-download-files-with-ftp.md), [방법: FTP를 사용하여 파일 업로드](../../../docs/framework/network-programming/how-to-upload-files-with-ftp.md), 및 [방법: FTP로 디렉터리 내용 나열](../../../docs/framework/network-programming/how-to-list-directory-contents-with-ftp.md).  
  
## FTP 및 프록시  
 프록시 경우 \(지정 하는 <xref:System.Net.FtpWebRequest.Proxy%2A> 속성\) HTTP 프록시를, 다음은 <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory>, 및 <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails> 명령이 지원 됩니다.  
  
## 참고 항목  
 [프록시를 통해 인터넷 액세스](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)   
 [네트워크 프로그래밍 샘플](../../../docs/framework/network-programming/network-programming-samples.md)   
 [FTP 클라이언트 기술 샘플](http://go.microsoft.com/fwlink/?LinkID=179557)   
 [FTP Explorer 기술 샘플](http://go.microsoft.com/fwlink/?LinkID=179569)   
 [응용 프로그램 프로토콜 사용](../../../docs/framework/network-programming/using-application-protocols.md)