---
title: "방법: 파일, 폴더 및 드라이브에 대한 정보 가져오기(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "파일[C#], 정보 가져오기"
ms.assetid: 22fc2da6-5494-405b-995e-c0b99142a93e
caps.latest.revision: 30
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 30
---
# 방법: 파일, 폴더 및 드라이브에 대한 정보 가져오기(C# 프로그래밍 가이드)
.NET Framework에서 다음과 같은 클래스를 사용하여 파일 시스템 정보에 액세스할 수 있습니다.  
  
-   <xref:System.IO.FileInfo?displayProperty=fullName>  
  
-   <xref:System.IO.DirectoryInfo?displayProperty=fullName>  
  
-   <xref:System.IO.DriveInfo?displayProperty=fullName>  
  
-   <xref:System.IO.Directory?displayProperty=fullName>  
  
-   <xref:System.IO.File?displayProperty=fullName>  
  
 <xref:System.IO.FileInfo> 및 <xref:System.IO.DirectoryInfo> 클래스는 파일 또는 디렉터리를 나타내며 NTFS 파일 시스템이 지원하는 많은 파일 특성을 노출하는 속성을 포함합니다.  또한 파일 및 폴더 열기, 닫기, 이동, 삭제를 위한 메서드도 포함합니다.  다음과 같이 생성자에 파일, 폴더 또는 드라이브 이름을 나타내는 문자열을 전달하여 이러한 클래스의 인스턴스를 만들 수 있습니다.  
  
```c#  
System.IO.DriveInfo di = new System.IO.DriveInfo(@"C:\");  
```  
  
 <xref:System.IO.DirectoryInfo.GetDirectories%2A?displayProperty=fullName>, <xref:System.IO.DirectoryInfo.GetFiles%2A?displayProperty=fullName> 및 <xref:System.IO.DriveInfo.RootDirectory%2A?displayProperty=fullName>를 호출하여 파일, 폴더 또는 드라이브 이름을 얻을 수도 있습니다.  
  
 <xref:System.IO.Directory?displayProperty=fullName> 및 <xref:System.IO.File?displayProperty=fullName> 클래스는 디렉터리 및 파일에 대한 정보를 검색하는 정적 메서드를 제공합니다.  
  
## 예제  
 다음 예제에서는 파일 및 폴더 정보에 액세스하는 여러 가지 방법을 보여 줍니다.  
  
 [!code-cs[csFilesandFolders#6](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-get-information-about-files-folders-and-drives_1.cs)]  
  
## 강력한 프로그래밍  
 사용자가 지정한 경로 문자열을 처리할 때 다음과 같은 예외 상황을 처리해야 합니다.  
  
-   파일 이름의 형식이 잘못된 경우.  예를 들어 파일 이름에 잘못된 문자가 들어 있거나 공백이 있을 수 있습니다.  
  
-   경로 이름이 null인 경우  
  
-   파일 이름이 시스템에 정의된 최대 길이보다 긴 경우  
  
-   파일 이름에 콜론\(:\)이 있는 경우  
  
 지정된 파일을 읽을 수 있는 충분한 권한이 응용 프로그램에 없으면 경로의 존재 여부와 상관없이 `Exists` 메서드에서 `false`를 반환합니다. 이때 메서드는 예외를 throw하지 않습니다.  
  
## 참고 항목  
 <xref:System.IO?displayProperty=fullName>   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [파일 시스템 및 레지스트리](../../../csharp/programming-guide/file-system/file-system-and-the-registry.md)