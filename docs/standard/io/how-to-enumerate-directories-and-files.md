---
title: "방법: 디렉터리 및 파일 열거"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O [.NET Framework], enumerating directories and files
ms.assetid: 86b69a08-3bfa-4e5f-b4e1-3b7cb8478215
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 5d0f22853210144881e49c4192ea38a5c3e57cda
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-enumerate-directories-and-files"></a>방법: 디렉터리 및 파일 열거
디렉터리 및 파일 이름의 문자열을 포함하는 열거 가능한 컬렉션을 반환하는 메서드를 사용하여 디렉터리 및 파일을 열거할 수 있습니다. 또한 <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo> 또는 <xref:System.IO.FileSystemInfo> 개체의 열거 가능한 컬렉션을 반환하는 메서드도 사용할 수 있습니다. 열거 가능한 컬렉션은 대규모의 디렉터리 및 파일 컬렉션으로 작업할 때 배열보다 나은 성능을 제공합니다.  
  
 또한 이러한 메서드에서 가져온 열거 가능한 컬렉션을 사용하여 <xref:System.Collections.Generic.List%601> 클래스와 같은 컬렉션 클래스의 생성자에 대한 <xref:System.Collections.Generic.IEnumerable%601> 매개 변수를 제공할 수도 있습니다.  
  
 디렉터리 또는 파일의 이름만 가져오려면 <xref:System.IO.Directory> 클래스의 열거 메서드를 사용하세요. 디렉터리 또는 파일의 다른 속성을 가져오려면 <xref:System.IO.DirectoryInfo> 및 <xref:System.IO.FileSystemInfo> 클래스를 사용하세요.  
  
 다음 표는 열거 가능한 컬렉션을 반환하는 메서드에 대한 지침을 제공합니다.  
  
|열거 대상|반환할 열거 가능한 컬렉션|사용할 메서드|  
|------------------|-------------------------------------|-------------------|  
|디렉터리|디렉터리 이름|<xref:System.IO.Directory.EnumerateDirectories%2A?displayProperty=nameWithType>|  
||디렉터리 정보(<xref:System.IO.DirectoryInfo>)|<xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|파일|파일 이름|<xref:System.IO.Directory.EnumerateFiles%2A?displayProperty=nameWithType>|  
||파일 정보(<xref:System.IO.FileInfo>)|<xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>|  
|파일 시스템 정보|파일 시스템 항목|<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  
||파일 시스템 정보(<xref:System.IO.FileSystemInfo>)|<xref:System.IO.DirectoryInfo.EnumerateFileSystemInfos%2A?displayProperty=nameWithType>|  
  
 <xref:System.IO.SearchOption.AllDirectories> 열거형에서 제공된 <xref:System.IO.SearchOption> 검색 옵션을 사용하여 부모 디렉터리의 하위 디렉터리에 있는 모든 파일을 즉시 열거할 수 있지만, 이 경우 무단 액세스 예외(<xref:System.UnauthorizedAccessException>)로 인해 열거가 완료되지 않을 수도 있습니다. 이러한 예외가 발생할 경우 이를 catch하고 먼저 디렉터리를 열거한 다음, 파일을 열거하여 계속할 수 있습니다.  
  
### <a name="to-enumerate-directory-names"></a>디렉터리 이름을 열거하려면  
  
-   지정된 경로에서 최상위 디렉터리 이름의 목록을 가져오려면 <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType> 메서드를 사용합니다.  
  
     [!code-csharp[System.IO.EnumDirs1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.enumdirs1/cs/program.cs#1)]
     [!code-vb[System.IO.EnumDirs1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.enumdirs1/vb/program.vb#1)]  
  
### <a name="to-enumerate-file-names-in-a-directory-and-subdirectories"></a>디렉터리 및 하위 디렉터리의 파일 이름을 열거하려면  
  
-   <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> 메서드를 사용해 디렉터리와 그 하위 디렉터리(선택 사항)를 검색하여 지정된 검색 패턴과 일치하는 파일 이름의 목록을 가져옵니다.  
  
     [!code-csharp[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/cs/program.cs#1)]
     [!code-vb[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/vb/program.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-directoryinfo-objects"></a>DirectoryInfo 개체의 컬렉션을 열거하려면  
  
-   최상위 디렉터리의 컬렉션을 가져오려면 <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> 메서드를 사용합니다.  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/vb/module1.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-fileinfo-objects-in-all-directories"></a>모든 디렉터리에서 FileInfo 개체의 컬렉션을 열거하려면  
  
-   모든 디렉터리에서 지정된 검색 패턴과 일치하는 파일의 컬렉션을 가져오려면 <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> 메서드를 사용합니다. 이 예제는 먼저 최상위 디렉터리를 열거하여 가능한 권한 없는 액세스 예외를 catch하고 파일을 열거합니다.  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/vb/program.vb#1)]  
  
## <a name="see-also"></a>참고 항목  
 [파일 및 스트림 I/O](../../../docs/standard/io/index.md)
