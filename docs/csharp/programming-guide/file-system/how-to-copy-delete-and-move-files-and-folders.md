---
title: "방법: 파일 및 폴더 복사, 삭제 및 이동(C# 프로그래밍 가이드) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "I/O[C#]"
ms.assetid: 62e52cd7-9597-4e4a-acf9-1315f5cdbf05
caps.latest.revision: 13
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 방법: 파일 및 폴더 복사, 삭제 및 이동(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

다음 예제에서는 <xref:System.IO?displayProperty=fullName> 네임스페이스의 <xref:System.IO.File?displayProperty=fullName>, <xref:System.IO.Directory?displayProperty=fullName>, <xref:System.IO.FileInfo?displayProperty=fullName> 및 <xref:System.IO.DirectoryInfo?displayProperty=fullName> 클래스를 사용하여 파일 및 폴더를 동기화된 방식으로 복사, 이동 및 삭제하는 방법을 보여 줍니다.  이러한 예제에서는 진행률 표시줄이나 다른 사용자 인터페이스는 제공하지 않습니다.  표준 진행률 대화 상자를 제공하려면 [방법: 파일 작업에 대한 진행률 대화 상자 제공](../../../csharp/programming-guide/file-system/how-to-provide-a-progress-dialog-box-for-file-operations.md)을 참조하십시오.  
  
 <xref:System.IO.FileSystemWatcher?displayProperty=fullName>를 사용하면 여러 파일을 처리할 때 진행률을 계산할 수 있는 이벤트를 제공할 수 있습니다.  또 다른 방법은 Windows 셸에서 파일 관련 메서드를 호출하는 플랫폼 호출을 사용하는 것입니다.  이러한 파일 작업을 비동기적으로 수행하는 방법에 대한 자세한 내용은 [비동기 파일 I\/O](../Topic/Asynchronous%20File%20I-O.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 파일 및 디렉터리를 복사하는 방법을 보여 줍니다.  
  
 [!code-cs[csFilesandFolders#7](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_1.cs)]  
  
## 예제  
 다음 예제에서는 파일 및 디렉터리를 이동하는 방법을 보여 줍니다.  
  
 [!code-cs[csFilesandFolders#8](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_2.cs)]  
  
## 예제  
 다음 예제에서는 파일 및 디렉터리를 삭제하는 방법을 보여 줍니다.  
  
 [!code-cs[csFilesandFolders#9](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_3.cs)]  
  
## 참고 항목  
 <xref:System.IO?displayProperty=fullName>   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [파일 시스템 및 레지스트리](../../../csharp/programming-guide/file-system/file-system-and-the-registry.md)   
 [방법: 파일 작업에 대한 진행률 대화 상자 제공](../../../csharp/programming-guide/file-system/how-to-provide-a-progress-dialog-box-for-file-operations.md)   
 [파일 및 스트림 I\/O](../Topic/File%20and%20Stream%20I-O.md)   
 [공통적인 I\/O 작업](../Topic/Common%20I-O%20Tasks.md)