---
title: "방법: 파일, 폴더 및 드라이브에 대한 정보 가져오기(C# 프로그래밍 가이드) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- files [C#], getting information about
ms.assetid: 22fc2da6-5494-405b-995e-c0b99142a93e
caps.latest.revision: 30
author: BillWagner
ms.author: wiwagn
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
ms.openlocfilehash: 16950f835938846804ade1a8ad23d907aa69b9c3
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-get-information-about-files-folders-and-drives--c-programming-guide"></a>방법: 파일, 폴더 및 드라이브에 대한 정보 가져오기(C# 프로그래밍 가이드)
.NET Framework에서 다음 클래스를 사용하여 파일 시스템 정보에 액세스할 수 있습니다.  
  
-   <xref:System.IO.FileInfo?displayProperty=fullName>  
  
-   <xref:System.IO.DirectoryInfo?displayProperty=fullName>  
  
-   <xref:System.IO.DriveInfo?displayProperty=fullName>  
  
-   <xref:System.IO.Directory?displayProperty=fullName>  
  
-   <xref:System.IO.File?displayProperty=fullName>  
  
 <xref:System.IO.FileInfo> 및 <xref:System.IO.DirectoryInfo> 클래스는 파일 또는 디렉터리를 나타내며, NTFS 파일 시스템에서 지원되는 많은 파일 특성을 노출하는 속성을 포함합니다. 또한 파일 및 폴더를 열고, 닫고, 이동, 삭제하기 위한 메서드도 포함합니다. 파일, 폴더 또는 드라이브의 이름을 나타내는 문자열을 생성자에 전달하여 이러한 클래스의 인스턴스를 만들 수 있습니다.  
  
```csharp  
System.IO.DriveInfo di = new System.IO.DriveInfo(@"C:\");  
```  
  
 <xref:System.IO.DirectoryInfo.GetDirectories%2A?displayProperty=fullName>, <xref:System.IO.DirectoryInfo.GetFiles%2A?displayProperty=fullName> 및 <xref:System.IO.DriveInfo.RootDirectory%2A?displayProperty=fullName> 호출을 사용하여 파일, 폴더 또는 드라이브의 이름을 가져올 수도 있습니다.  
  
 <xref:System.IO.Directory?displayProperty=fullName> 및 <xref:System.IO.File?displayProperty=fullName> 클래스는 디렉터리 및 파일에 대한 정보를 검색하기 위한 정적 메서드를 제공합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 파일 및 폴더에 대한 정보에 액세스하는 다양한 방법을 보여 줍니다.  
  
 [!code-cs[csFilesandFolders#6](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-get-information-about-files-folders-and-drives_1.cs)]  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 사용자 지정 경로 문자열을 처리하는 경우 다음 조건에 대한 예외도 처리해야 합니다.  
  
-   파일 이름 형식이 잘못된 경우. 예를 들어 잘못된 문자를 포함하거나 공백만 포함합니다.  
  
-   파일 이름이 null인 경우  
  
-   파일 이름이 시스템에 정의된 최대 길이보다 긴 경우  
  
-   파일 이름에 콜론(:)이 포함된 경우  
  
 응용 프로그램에 지정된 파일을 읽을 수 있는 권한이 없는 경우 `Exists` 메서드는 경로가 있는지 여부에 관계없이 `false`를 반환합니다. 이 메서드는 예외를 throw하지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.IO?displayProperty=fullName>   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [파일 시스템 및 레지스트리(C# 프로그래밍 가이드)](../../../csharp/programming-guide/file-system/index.md)
