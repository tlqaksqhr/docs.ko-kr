---
title: "방법: 디렉터리 및 파일 열거 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "I/O[.NET Framework], 디렉터리 및 파일 열거"
ms.assetid: 86b69a08-3bfa-4e5f-b4e1-3b7cb8478215
caps.latest.revision: 18
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 18
---
# 방법: 디렉터리 및 파일 열거
디렉터리 및 파일 이름의 문자열을 포함하는 열거 가능한 컬렉션을 반환하는 메서드를 사용하여 디렉터리 및 파일을 열거할 수 있습니다.  또한 <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo> 또는 <xref:System.IO.FileSystemInfo> 개체를 포함하는 열거 가능한 컬렉션을 반환하는 메서드도 사용할 수 있습니다.  열거 가능한 컬렉션 디렉터리 및 파일의 대규모 컬렉션을 사용 하면 배열 보다 나은 성능을 제공 합니다.  
  
 이러한 메서드를 통해 가져온 열거 가능한 컬렉션은 <xref:System.Collections.Generic.List%601> 클래스 같은 컬렉션 클래스의 생성자에 <xref:System.Collections.Generic.IEnumerable%601> 매개 변수를 제공하는 데 사용할 수도 있습니다.  
  
 디렉터리 또는 파일의 이름만 가져오려면 <xref:System.IO.Directory> 클래스의 열거 메서드를 사용합니다.  이름 외에 디렉터리 또는 파일의 다른 속성을 가져오려면 <xref:System.IO.DirectoryInfo> 및 <xref:System.IO.FileSystemInfo> 클래스를 사용합니다.  
  
 다음 표에서는 열거 가능한 컬렉션을 반환하는 메서드에 대한 지침을 제공합니다.  
  
|열거할 대상|반환되는 열거 가능한 컬렉션|사용할 메서드|  
|------------|---------------------|-------------|  
|디렉터리|디렉터리 이름|<xref:System.IO.Directory.EnumerateDirectories%2A?displayProperty=fullName>|  
||디렉터리 정보\(<xref:System.IO.DirectoryInfo>\)|<xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=fullName>|  
|파일|파일 이름|<xref:System.IO.Directory.EnumerateFiles%2A?displayProperty=fullName>|  
||파일 정보\(<xref:System.IO.FileInfo>\)|<xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=fullName>|  
|파일 시스템 정보|파일 시스템 항목|<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=fullName>|  
||파일 시스템 정보 \(<xref:System.IO.FileSystemInfo>\)|<xref:System.IO.DirectoryInfo.EnumerateFileSystemInfos%2A?displayProperty=fullName>|  
  
 <xref:System.IO.SearchOption> 열거형에서 제공된 <xref:System.IO.SearchOption> 검색 옵션을 사용하여 부모 디렉터리의 하위 디렉터리에 있는 모든 파일을 즉시 열거할 수 있지만, 이 경우 무단 액세스 예외\(<xref:System.UnauthorizedAccessException>\)로 인해 열거가 완료되지 않을 수도 있습니다.  이러한 예외가 발생할 것으로 보이면 예외를 catch하고 디렉터리를 먼저 열거한 다음 파일을 열거하여 계속합니다.  
  
### 디렉터리 이름을 열거하려면  
  
-   <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=fullName> 메서드를 사용하여 지정된 경로에 있는 최상위 수준 디렉터리의 이름 목록을 가져옵니다.  
  
     [!code-csharp[System.IO.EnumDirs1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.enumdirs1/cs/program.cs#1)]
     [!code-vb[System.IO.EnumDirs1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.enumdirs1/vb/program.vb#1)]  
  
### 디렉터리 및 하위 디렉터리의 파일 이름을 열거 하려면  
  
-   <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=fullName> 메서드를 사용해 디렉터리와 그 하위 디렉토리를 검색하여 지정된 경로에서 해당 검색 패턴과 일치하는 파일 이름의 목록을 가져옵니다.  
  
     [!code-csharp[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/cs/program.cs#1)]
     [!code-vb[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/vb/program.vb#1)]  
  
### DirectoryInfo 개체 컬렉션을 열거하려면  
  
-   <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=fullName> 메서드를 사용하여 최상위 디렉터리의 컬렉션을 가져옵니다.  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/vb/module1.vb#1)]  
  
### 모든 디렉터리에서 FileInfo 개체 컬렉션을 열거하려면  
  
-   <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=fullName> 메서드를 사용하여 모든 디렉터리에서 해당 검색 패턴과 일치하는 파일의 컬렉션을 가져옵니다.  이 예제에서는 먼저 최상위 수준 디렉터리를 열거하여 발생 가능한 무단 액세스 예외를 catch한 다음 파일을 열거합니다.  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/vb/program.vb#1)]  
  
## 참고 항목  
 [파일 및 스트림 I\/O](../../../docs/standard/io/index.md)