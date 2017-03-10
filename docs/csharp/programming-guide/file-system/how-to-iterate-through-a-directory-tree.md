---
title: "방법: 디렉터리 트리 반복(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "파일 반복[C#]"
  - "폴더 반복[C#]"
ms.assetid: c4be4a75-6b1b-46a7-9d38-bab353091ed7
caps.latest.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 10
---
# 방법: 디렉터리 트리 반복(C# 프로그래밍 가이드)
"디렉터리 트리 반복"이란 깊이에 관계없이 지정된 루트 폴더 아래에 있는 각 중첩 하위 디렉터리에서 각 파일에 액세스한다는 의미입니다.  이때 각 파일을 반드시 열어야 하는 것은 아닙니다.  파일이나 하위 디렉터리의 이름만 `string`으로 검색하거나 <xref:System.IO.FileInfo?displayProperty=fullName> 또는 <xref:System.IO.DirectoryInfo?displayProperty=fullName> 개체의 형태로 추가 정보를 검색할 수 있습니다.  
  
> [!NOTE]
>  Windows에서 "디렉터리"와 "폴더"라는 용어는 같은 의미로 사용됩니다.  대부분의 설명서와 사용자 인터페이스 텍스트에서는 "폴더"라는 용어가 사용되지만 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] 클래스 라이브러리에서는 "디렉터리"라는 용어가 사용됩니다.  
  
 지정된 루트 아래에 있는 모든 디렉터리에 대한 액세스 권한이 있는 경우가 가장 간단하며, 이 경우에는 `System.IO.SearchOption.AllDirectories` 플래그를 사용할 수 있습니다.  이 플래그는 지정된 패턴과 일치하는 모든 중첩 하위 디렉터리를 반환합니다.  다음 예제에서는 이 플래그를 사용하는 방법을 보여 줍니다.  
  
```c#  
root.GetDirectories("*.*", System.IO.SearchOption.AllDirectories);  
```  
  
 이 방식의 단점은 지정된 루트 아래에 있는 하위 디렉터리 중 하나가 <xref:System.IO.DirectoryNotFoundException> 또는 <xref:System.UnauthorizedAccessException>을 발생시키면 전체 메서드가 실패하고 디렉터리가 반환되지 않는다는 것입니다.  이것은 <xref:System.IO.DirectoryInfo.GetFiles%2A> 메서드를 사용할 경우에도 마찬가지입니다.  특정 하위 폴더에서 이러한 예외를 처리해야 한다면 다음 예제에서 볼 수 있는 것처럼 디렉터리 트리를 수동으로 탐색해야 합니다.  
  
 디렉터리 트리를 수동으로 탐색할 때 하위 디렉터리를 먼저\(*전위 탐색*\) 처리하거나 파일을 먼저\(*후위 탐색*\) 처리할 수 있습니다.  전위 탐색을 수행할 경우 폴더 자체에 들어 있는 파일을 반복하기 전에 먼저 현재 폴더 아래에 있는 전체 트리를 탐색합니다.  이 문서의 뒷부분에 있는 예제에서는 후위 탐색을 수행하지만 전위 탐색을 수행하도록 수정하는 것은 간단합니다.  
  
 다른 옵션은 재귀를 사용할지 스택 기반 탐색을 사용할지 결정하는 것입니다.  이 문서의 뒷부분에 있는 예제에서는 두 방식을 모두 보여 줍니다.  
  
 파일과 폴더에 대한 다양한 작업을 수행해야 한다면 단일 대리자를 통해 호출할 수 있는 별도의 함수로 작업을 리팩터링하여 이 예제를 모듈화할 수 있습니다.  
  
> [!NOTE]
>  NTFS 파일 시스템은 *연결 지점*, *기호화된 링크* 및 *하드 링크*의 형태로 *재분석 지점*을 포함할 수 있습니다.  <xref:System.IO.DirectoryInfo.GetFiles%2A> 및 <xref:System.IO.DirectoryInfo.GetDirectories%2A> 등의 .NET Framework 메서드는 재분석 지점 아래에 있는 하위 디렉터리를 반환하지 않습니다.  이 동작은 두 재분석 지점이 상호 참조하는 경우 무한 루프에 빠지지 않도록 보호합니다.  일반적으로 재분석 지점으로 작업할 때에는 실수로 파일을 수정하거나 삭제하지 않도록 특히 주의해야 합니다.  재분석 지점에 대한 정밀한 제어가 필요한 경우에는 적절한 Win32 파일 시스템 메서드를 직접 호출하는 플랫폼 호출이나 네이티브 코드를 사용하십시오.  
  
## 예제  
 다음 예제에서는 재귀를 사용하여 디렉터리 트리를 탐색하는 방법을 보여 줍니다.  재귀는 적절한 방식이기는 하지만 디렉터리 트리의 규모가 크고 복잡하게 중첩되어 있는 경우 스택 오버플로 예외를 발생시킬 위험이 있습니다.  
  
 처리되는 특정한 예외와 각 파일이나 폴더에 수행되는 특정 작업은 예제로만 제공됩니다.  따라서 해당 요구 사항에 맞게 이 코드를 수정해야 합니다.  자세한 내용은 코드의 주석을 참조하십시오.  
  
 [!code-cs[csFilesandFolders#1](../../../csharp/programming-guide/file-system/codesnippet/csharp/csFilesFolders/FileIteration.cs#1)]  
  
## 예제  
 다음 예제에서는 재귀를 사용하지 않고 디렉터리 트리에서 파일 및 폴더를 반복하는 방법을 보여 줍니다.  이 방법에서는 LIFO\(후입선출\) 스택인 제네릭 <xref:System.Collections.Generic.Stack%601> 컬렉션 형식을 사용합니다.  
  
 처리되는 특정한 예외와 각 파일이나 폴더에 수행되는 특정 작업은 예제로만 제공됩니다.  따라서 해당 요구 사항에 맞게 이 코드를 수정해야 합니다.  자세한 내용은 코드의 주석을 참조하십시오.  
  
 [!code-cs[csFilesandFolders#2](../../../csharp/programming-guide/file-system/codesnippet/csharp/csFilesFolders/FileIteration.cs#2)]  
  
 응용 프로그램에 폴더를 열 수 있는 권한이 있는지 확인하기 위해 모든 폴더를 테스트하는 작업은 시간이 너무 많이 걸립니다.  따라서 이 코드 예제에서는 작업의 해당 부분을 `try/catch` 블록으로 묶기만 했습니다.  폴더에 대한 액세스가 거부된 경우 권한을 상승시키고 다시 액세스할 수 있도록 `catch` 블록을 수정할 수 있습니다.  일반적으로 응용 프로그램을 알 수 없는 상태로 두지 않고 처리할 수 있는 예외만 catch합니다.  
  
 디렉터리 트리의 내용을 메모리나 디스크에 저장해야 하는 경우 각 파일의 <xref:System.IO.FileSystemInfo.FullName%2A> 속성\(`string` 형식\)만 저장하는 것이 좋습니다.  그런 다음 필요에 따라 이 문자열을 사용하여 새 <xref:System.IO.FileInfo> 또는 <xref:System.IO.DirectoryInfo> 개체를 만들거나 추가적인 처리가 필요한 파일을 열 수 있습니다.  
  
## 강력한 프로그래밍  
 강력한 파일 반복 코드에서는 파일 시스템의 여러 가지 복잡한 특성을 고려해야 합니다.  자세한 내용은 [NTFS Technical Reference](http://go.microsoft.com/fwlink/?LinkId=79488)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.IO>   
 [LINQ and File Directories](../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)   
 [파일 시스템 및 레지스트리](../../../csharp/programming-guide/file-system/file-system-and-the-registry.md)