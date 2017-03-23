---
title: "Classes Used in .NET Framework File I/O and the File System (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "file I/O classes"
ms.assetid: 4a5ca924-eea8-4a95-a5f0-6ac10de276a3
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Classes Used in .NET Framework File I/O and the File System (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

다음 표에서는 .NET Framework 파일 I\/O에 일반적으로 사용되는 클래스, 파일 I\/O 클래스로 범주화된 클래스, 스트림 만들기에 사용되는 클래스, 스트림 읽기와 쓰기에 사용되는 클래스를 나열합니다.  
  
 [!INCLUDE[dnprdnlong](../../../../csharp/programming-guide/events/includes/dnprdnlong-md.md)] 문서에서 더 포괄적인 목록을 보려면 [클래스 라이브러리 개요](../Topic/.NET%20Framework%20Class%20Library%20Overview.md)를 참조하십시오.  
  
## 파일, 드라이브 및 디렉터리에 대한 기본 I\/O 클래스  
 다음 표에서는 파일 I\/O에 사용되는 주 클래스를 나열하고 설명합니다.  
  
|클래스|설명|  
|---------|--------|  
|<xref:System.IO.Directory?displayProperty=fullName>|디렉터리와 하위 디렉터리를 만들고, 이동하고 열거하기 위한 정적 메서드를 제공합니다.|  
|<xref:System.IO.DirectoryInfo?displayProperty=fullName>|디렉터리와 하위 디렉터리를 만들고 이동하고 열거하기 위한 인스턴스 메서드를 제공합니다.|  
|<xref:System.IO.DriveInfo?displayProperty=fullName>|드라이브를 만들고 이동하고 열거하기 위한 인스턴스 메서드를 제공합니다.|  
|<xref:System.IO.File?displayProperty=fullName>|파일 만들기, 복사, 삭제, 이동 및 열기를 위한 정적 메서드를 제공하고 `FileStream` 만들기를 지원합니다.|  
|<xref:System.IO.FileAccess?displayProperty=fullName>|파일에 대한 읽기, 쓰기 또는 읽기\/쓰기 액세스에 사용하는 상수를 정의합니다.|  
|<xref:System.IO.FileAttributes?displayProperty=fullName>|`Archive`, `Hidden` 및 `ReadOnly` 등과 같은 파일 및 디렉터리에 대한 특성을 제공합니다.|  
|<xref:System.IO.FileInfo?displayProperty=fullName>|파일 만들기, 복사, 삭제, 이동 및 열기를 위한 정적 메서드를 제공하고 `FileStream` 만들기를 지원합니다.|  
|<xref:System.IO.FileMode?displayProperty=fullName>|파일을 여는 방식을 제어합니다.  이 매개 변수는 `FileStream` 및 `IsolatedStorageFileStream`의 많은 생성자와 <xref:System.IO.File> 및 <xref:System.IO.FileInfo>의 `Open` 메서드에 지정합니다.|  
|<xref:System.IO.FileShare?displayProperty=fullName>|같은 파일에 대해 서로 다른 파일 시스템들이 가질 수 있는 액세스 형식을 제어하기 위한 상수를 정의합니다.|  
|<xref:System.IO.Path?displayProperty=fullName>|디렉터리 문자열 처리를 위한 메서드와 속성을 제공합니다.|  
|<xref:System.Security.Permissions.FileIOPermission?displayProperty=fullName>|<xref:System.Security.Permissions.FileIOPermissionAttribute.Read%2A>, <xref:System.Security.Permissions.FileIOPermissionAttribute.Write%2A>, <xref:System.Security.Permissions.FileIOPermissionAttribute.Append%2A> 및 <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> 권한을 정의하여 파일과 폴더의 액세스를 제어합니다.|  
  
## 스트림 만들기에 사용되는 클래스  
 다음 표에서는 스트림 만들기에 사용되는 주 클래스를 나열하고 설명합니다.  
  
|클래스|설명|  
|---------|--------|  
|<xref:System.IO.BufferedStream?displayProperty=fullName>|다른 스트림에 대한 읽기 및 쓰기 작업에 버퍼링 계층을 추가합니다.|  
|<xref:System.IO.FileStream?displayProperty=fullName>|<xref:System.IO.FileStream.Seek%2A> 메서드를 통해 파일에 대한 임의 액세스를 지원합니다.  <xref:System.IO.FileStream>은 기본적으로 파일을 동기적으로 열지만 비동기 작업도 지원합니다.|  
|<xref:System.IO.MemoryStream?displayProperty=fullName>|백업 저장소가 파일이 아니라 메모리인 스트림을 만듭니다.|  
|<xref:System.Net.Sockets.NetworkStream?displayProperty=fullName>|네트워크 액세스를 위한 기본 데이터 스트림을 제공합니다.|  
|<xref:System.Security.Cryptography.CryptoStream?displayProperty=fullName>|데이터 스트림을 암호화 변환에 연결하는 스트림을 정의합니다.|  
  
## 스트림 읽기와 쓰기에 사용되는 클래스  
 다음 표에서는 스트림으로 파일을 읽고 쓰는 데 사용되는 특정 클래스를 보여 줍니다.  
  
|**클래스**|**설명**|  
|-------------|------------|  
|<xref:System.IO.BinaryReader?displayProperty=fullName>|<xref:System.IO.FileStream>에서 인코딩된 문자열과 기본 데이터 형식을 읽습니다.|  
|<xref:System.IO.BinaryWriter?displayProperty=fullName>|인코딩된 문자열과 기본 데이터 형식을 <xref:System.IO.FileStream>에 씁니다.|  
|<xref:System.IO.StreamReader?displayProperty=fullName>|문자와 바이트 간을 변환하는 <xref:System.IO.StreamReader.CurrentEncoding%2A>을 사용하여 <xref:System.IO.FileStream>에서 문자를 읽습니다.  <xref:System.IO.StreamReader>에는 바이트 순서 표시와 같은 <xref:System.IO.StreamReader.CurrentEncoding%2A> 관련 preamble의 존재 여부를 기반으로 하여 지정된 스트림에 대한 올바른 <xref:System.IO.StreamReader.CurrentEncoding%2A>을 확인하는 생성자가 있습니다.|  
|<xref:System.IO.StreamWriter?displayProperty=fullName>|문자와 바이트 간을 변환하는 <xref:System.IO.StreamWriter.Encoding%2A>를 사용하여 문자를 `FileStream`에 씁니다.|  
|<xref:System.IO.StringReader?displayProperty=fullName>|`String`에서 문자를 읽습니다.  출력은 임의의 인코딩으로 된 스트림이거나 `String`일 수 있습니다.|  
|<xref:System.IO.StringWriter?displayProperty=fullName>|`String`에 문자를 씁니다.  출력은 임의의 인코딩으로 된 스트림이거나 `String`일 수 있습니다.|  
  
## 참고 항목  
 [스트림 작성](../Topic/Composing%20Streams.md)   
 [파일 및 스트림 I\/O](../Topic/File%20and%20Stream%20I-O.md)   
 [비동기 파일 I\/O](../Topic/Asynchronous%20File%20I-O.md)   
 [.NET Framework 파일 I\/O 및 파일 시스템의 기본 사항\(Visual Basic\)](../../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md)