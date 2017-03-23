---
title: "방법: 텍스트 파일에서 읽기(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "StreamReader.ReadToEnd"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "데이터 읽기, 텍스트 파일"
  - "텍스트 파일 읽기"
  - "텍스트 파일, 읽기"
  - "텍스트 파일, 쓰기"
ms.assetid: 92246c5b-e819-4eea-9370-1a9460e12de3
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# 방법: 텍스트 파일에서 읽기(C# 프로그래밍 가이드)
정적 메서드를 사용 하 여이 예제 텍스트 파일의 내용을 읽어 <xref:System.IO.File.ReadAllText%2A> 및 <xref:System.IO.File.ReadAllLines%2A> 에서 <xref:System.IO.File?displayProperty=fullName> 클래스입니다.  
  
 <xref:System.IO.StreamReader>을 사용하는 예제를 보려면 [방법: 텍스트 파일을 한 번에 한 줄씩 읽기](../../../csharp/programming-guide/file-system/how-to-read-a-text-file-one-line-at-a-time.md)을 참조하십시오.  
  
> [!NOTE]
>  이 예제에서 사용 되는 파일에서 만들어진 [방법: 텍스트 파일에 쓰기](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md).  
  
## 예제  
 [!code-cs[csFilesandFolders#4](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-read-from-a-text-file_1.cs)]  
  
## 코드 컴파일  
 코드를 복사 하 여 C\# 콘솔 응용 프로그램에 붙여넣습니다.  
  
 텍스트 파일에서 사용 하는 경우 [방법: 텍스트 파일에 쓰기](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md), 교체에 대 한 인수 `ReadAllText` 및 `ReadAllLines` 컴퓨터에 적절 한 경로 및 파일 이름으로.  
  
## 강력한 프로그래밍  
 다음 조건에서 예외가 발생할 수 있습니다.  
  
-   파일이 존재 하지 않거나 지정한 위치에 존재 하지 않습니다.  경로 파일 이름이 올바른지 확인 하십시오.  
  
## .NET Framework 보안  
 파일의 내용을 확인 하기 위해 파일 이름에 의존 하지 않습니다.  예를 들어, 파일 `myFile.cs` C\# 소스 파일이 아닐 수도 있습니다.  
  
## 참고 항목  
 <xref:System.IO?displayProperty=fullName>   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [파일 시스템 및 레지스트리](../../../csharp/programming-guide/file-system/file-system-and-the-registry.md)