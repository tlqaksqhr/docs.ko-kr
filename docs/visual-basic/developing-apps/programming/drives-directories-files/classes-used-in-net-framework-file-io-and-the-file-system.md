---
title: ".NET Framework 파일 I/O 및 파일 시스템에 사용되는 클래스(Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- file I/O classes
ms.assetid: 4a5ca924-eea8-4a95-a5f0-6ac10de276a3
caps.latest.revision: 15
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6bf3902995531768b8b065aca70790c16d77b0ce
ms.lasthandoff: 03/13/2017

---
# <a name="classes-used-in-net-framework-file-io-and-the-file-system-visual-basic"></a>.NET Framework 파일 I/O 및 파일 시스템에 사용되는 클래스(Visual Basic)
다음 표에는 .NET Framework 파일 I/O에 공통적으로 사용되고 파일 I/O 클래스로 범주화되는 클래스, 스트림을 만드는 데 사용되는 클래스 및 스트림을 읽고 스트림에 쓰는 데 사용되는 클래스가 나와 있습니다.  
  
 [!INCLUDE[dnprdnlong](../../../../csharp/programming-guide/events/includes/dnprdnlong_md.md)] 문서를 시작하고 더 포괄적인 목록을 찾으려면 [클래스 라이브러리 개요](https://msdn.microsoft.com/library/hfa3fa08)를 참조하세요.  
  
## <a name="basic-io-classes-for-files-drives-and-directories"></a>파일, 드라이브 및 디렉터리의 기본 I/O 클래스  
 다음 표에서는 파일 I/O에 사용되는 기본 클래스를 나열하고 설명합니다.  
  
|클래스|설명|  
|-----------|-----------------|  
|<xref:System.IO.Directory?displayProperty=fullName>|디렉터리와 하위 디렉터리를 통해 만들고, 이동하고, 열거하기 위한 정적 메서드를 제공합니다.|  
|<xref:System.IO.DirectoryInfo?displayProperty=fullName>|디렉터리와 하위 디렉터리를 통해 만들고, 이동하고, 열거하기 위한 인스턴스 메서드를 제공합니다.|  
|<xref:System.IO.DriveInfo?displayProperty=fullName>|드라이브를 통해 만들고, 이동하고, 열거하기 위한 인스턴스 메서드를 제공합니다.|  
|<xref:System.IO.File?displayProperty=fullName>|파일 만들기, 복사, 삭제, 이동 및 열기를 위한 정적 메서드를 제공하고 `FileStream`만들기를 지원합니다.|  
|<xref:System.IO.FileAccess?displayProperty=fullName>|파일에 대한 읽기, 쓰기 또는 읽기/쓰기 액세스 권한에 대한 상수를 정의합니다.|  
|<xref:System.IO.FileAttributes?displayProperty=fullName>|`Archive`, `Hidden` 및 `ReadOnly`와 같은 파일 및 디렉터리에 대한 특성을 제공합니다.|  
|<xref:System.IO.FileInfo?displayProperty=fullName>|파일 만들기, 복사, 삭제, 이동 및 열기를 위한 정적 메서드를 제공하고 `FileStream`만들기를 지원합니다.|  
|<xref:System.IO.FileMode?displayProperty=fullName>|파일을 여는 방식을 제어합니다. 이 매개 변수는 대부분의 `FileStream` 및 `IsolatedStorageFileStream`에 대한 생성자와 <xref:System.IO.File> 및 <xref:System.IO.FileInfo>의 `Open` 메서드에 대한 생성자에서 지정됩니다.|  
|<xref:System.IO.FileShare?displayProperty=fullName>|다른 파일 스트림이 같은 파일에 대해 가질 수 있는 액세스 형식을 제어하기 위한 상수를 정의합니다.|  
|<xref:System.IO.Path?displayProperty=fullName>|디렉터리 문자열을 처리하기 위한 메서드와 속성을 제공합니다.|  
|<xref:System.Security.Permissions.FileIOPermission?displayProperty=fullName>|<xref:System.Security.Permissions.FileIOPermissionAttribute.Read%2A>, <xref:System.Security.Permissions.FileIOPermissionAttribute.Write%2A>, <xref:System.Security.Permissions.FileIOPermissionAttribute.Append%2A> 및 <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> 권한을 정의하여 파일 및 폴더의 액세스를 제어합니다.|  
  
## <a name="classes-used-to-create-streams"></a>스트림을 만드는 데 사용되는 클래스  
 다음 표에서는 스트림을 만드는 데 사용되는 기본 클래스를 나열하고 설명합니다.  
  
|클래스|설명|  
|-----------|-----------------|  
|<xref:System.IO.BufferedStream?displayProperty=fullName>|다른 스트림에서 작업을 읽고 쓰기 위한 버퍼링 레이어를 추가합니다.|  
|<xref:System.IO.FileStream?displayProperty=fullName>|<xref:System.IO.FileStream.Seek%2A> 메서드를 통해 파일에 대한 임의 액세스를 지원합니다. <xref:System.IO.FileStream>은 기본적으로 파일을 동기적으로 열지만 비동기 작업도 지원합니다.|  
|<xref:System.IO.MemoryStream?displayProperty=fullName>|백업 저장소가 파일이 아니라 메모리인 스트림을 만듭니다.|  
|<xref:System.Net.Sockets.NetworkStream?displayProperty=fullName>|네트워크 액세스를 위한 데이터의 기본 스트림을 제공합니다.|  
|<xref:System.Security.Cryptography.CryptoStream?displayProperty=fullName>|데이터 스트림을 암호화 변환에 연결하는 스트림을 정의합니다.|  
  
## <a name="classes-used-to-read-from-and-write-to-streams"></a>스트림에서 읽고 스트림에 쓰는 데 사용되는 클래스  
 다음 표에는 스트림을 통해 파일에서 읽고 파일에 쓰는 데 사용되는 특정 클래스를 보여 줍니다.  
  
|**클래스**|**설명**|  
|---------------|---------------------|  
|<xref:System.IO.BinaryReader?displayProperty=fullName>|<xref:System.IO.FileStream>에서 인코딩된 문자열 및 기본 데이터 형식을 읽습니다.|  
|<xref:System.IO.BinaryWriter?displayProperty=fullName>|<xref:System.IO.FileStream>에 인코딩된 문자열 및 기본 데이터 형식을 씁니다.|  
|<xref:System.IO.StreamReader?displayProperty=fullName>|<xref:System.IO.FileStream>에서 문자를 읽어 <xref:System.IO.StreamReader.CurrentEncoding%2A>을 통해 문자를 바이트로 변환하거나 그 반대로 변환합니다. <xref:System.IO.StreamReader>에는 바이트 순서 표시와 같은 <xref:System.IO.StreamReader.CurrentEncoding%2A> 관련 프리앰블이 있는지 여부에 따라 제공된 스트림에 대한 올바른 <xref:System.IO.StreamReader.CurrentEncoding%2A> 확인을 시도하는 생성자가 있습니다.|  
|<xref:System.IO.StreamWriter?displayProperty=fullName>|`FileStream`에 문자를 써서 <xref:System.IO.StreamWriter.Encoding%2A>을 통해 문자를 바이트로 변환합니다.|  
|<xref:System.IO.StringReader?displayProperty=fullName>|`String`에서 문자를 읽습니다. 출력은 인코딩의 스트림 또는 `String` 중 하나일 수 있습니다.|  
|<xref:System.IO.StringWriter?displayProperty=fullName>|`String`에 문자를 씁니다. 출력은 인코딩의 스트림 또는 `String` 중 하나일 수 있습니다.|  
  
## <a name="see-also"></a>참고 항목  
 [스트림 작성](https://msdn.microsoft.com/library/e4y2dch9)   
 [파일 및 스트림 I/O](https://msdn.microsoft.com/library/k3352a4t)   
 [비동기 파일 I/O](https://msdn.microsoft.com/library/kztecsys)   
 [.NET Framework 파일 I/O 및 파일 시스템의 기본 사항(Visual Basic)](../../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md)
