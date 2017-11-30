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
helpviewer_keywords: I/O [.NET Framework], enumerating directories and files
ms.assetid: 86b69a08-3bfa-4e5f-b4e1-3b7cb8478215
caps.latest.revision: "18"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: caf9bdec017a5466269ff7fe97be4d0243035b4a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-enumerate-directories-and-files"></a>방법: 디렉터리 및 파일 열거
디렉터리 및 파일 이름의 문자열을 포함하는 열거 가능한 컬렉션을 반환하는 메서드를 사용하여 디렉터리 및 파일을 열거할 수 있습니다. 열거 가능한 컬렉션을 반환 하는 메서드를 사용할 수도 있습니다 <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo>, 또는 <xref:System.IO.FileSystemInfo> 개체입니다. 열거 가능한 컬렉션은 대규모의 디렉터리 및 파일 컬렉션으로 작업할 때 배열보다 나은 성능을 제공합니다.  
  
 제공 하려면 이러한 방법 중에서 얻은 열거 가능한 컬렉션을 사용할 수도 있습니다는 <xref:System.Collections.Generic.IEnumerable%601> 와 같은 컬렉션의 생성자에 대 한 매개 변수 클래스는 <xref:System.Collections.Generic.List%601> 클래스입니다.  
  
 디렉터리 또는 파일의 이름만 가져오려는 경우의 열거형 메서드를 사용는 <xref:System.IO.Directory> 클래스입니다. 디렉터리 또는 파일의 다른 속성을 가져오는 경우 사용할는 <xref:System.IO.DirectoryInfo> 및 <xref:System.IO.FileSystemInfo> 클래스입니다.  
  
 다음 표에서 열거 가능한 컬렉션을 반환 하는 방법에 대 한 지침을 제공 합니다.  
  
|열거 하려면|열거 가능한 컬렉션을 반환 하려면|사용 하는 메서드|  
|------------------|-------------------------------------|-------------------|  
|디렉터리|디렉터리 이름|<xref:System.IO.Directory.EnumerateDirectories%2A?displayProperty=nameWithType>|  
||디렉터리 정보(<xref:System.IO.DirectoryInfo>)|<xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|파일|파일 이름|<xref:System.IO.Directory.EnumerateFiles%2A?displayProperty=nameWithType>|  
||파일 정보(<xref:System.IO.FileInfo>)|<xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>|  
|파일 시스템 정보|파일 시스템 항목|<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  
||파일 시스템 정보(<xref:System.IO.FileSystemInfo>)|<xref:System.IO.DirectoryInfo.EnumerateFileSystemInfos%2A?displayProperty=nameWithType>|  
  
 <xref:System.IO.SearchOption.AllDirectories> 열거형에서 제공된 <xref:System.IO.SearchOption> 검색 옵션을 사용하여 부모 디렉터리의 하위 디렉터리에 있는 모든 파일을 즉시 열거할 수 있지만, 이 경우 무단 액세스 예외(<xref:System.UnauthorizedAccessException>)로 인해 열거가 완료되지 않을 수도 있습니다. 이러한 예외를 가능한 경우에 catch 수 있으며 디렉터리를 먼저 열거 한 다음 파일을 열거 하 여 계속할 수 있습니다.  
  
### <a name="to-enumerate-directory-names"></a>디렉터리 이름을 열거 하려면  
  
-   사용 하 여는 <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType> 메서드를 지정된 된 경로에서 최상위 디렉터리 이름의 목록을 가져옵니다.  
  
     [!code-csharp[System.IO.EnumDirs1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.enumdirs1/cs/program.cs#1)]
     [!code-vb[System.IO.EnumDirs1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.enumdirs1/vb/program.vb#1)]  
  
### <a name="to-enumerate-file-names-in-a-directory-and-subdirectories"></a>디렉터리 및 하위 디렉터리의 파일 이름을 열거하려면  
  
-   <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> 메서드를 사용해 디렉터리와 그 하위 디렉터리(선택 사항)를 검색하여 지정된 검색 패턴과 일치하는 파일 이름의 목록을 가져옵니다.  
  
     [!code-csharp[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/cs/program.cs#1)]
     [!code-vb[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/vb/program.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-directoryinfo-objects"></a>DirectoryInfo 개체의 컬렉션을 열거 하려면  
  
-   사용 하 여 <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> 메서드 최상위 디렉터리의 컬렉션을 가져옵니다.  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/vb/module1.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-fileinfo-objects-in-all-directories"></a>모든 디렉터리의 FileInfo 개체의 컬렉션을 열거 하려면  
  
-   사용 하 여 <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> 메서드 모든 디렉터리에서 지정 된 검색 패턴과 일치 하는 파일의 컬렉션을 가져옵니다. 이 예에서는 먼저 가능한 무단된 액세스 예외를 catch 하는 최상위 디렉터리를 열거 하 고 파일을 열거 합니다.  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/vb/program.vb#1)]  
  
## <a name="see-also"></a>참고 항목  
 [파일 및 스트림 I/O](../../../docs/standard/io/index.md)
