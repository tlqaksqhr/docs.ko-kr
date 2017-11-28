---
title: "방법: 텍스트 파일에서 읽기(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: StreamReader.ReadToEnd
helpviewer_keywords:
- text files, writing to
- reading text files
- reading data, text files
- text files, reading
ms.assetid: 92246c5b-e819-4eea-9370-1a9460e12de3
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d2af6102ac6793b4612a6fbc41f8c50189cc24d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-read-from-a-text-file-c-programming-guide"></a>방법: 텍스트 파일에서 읽기(C# 프로그래밍 가이드)
이 예제에서는 <xref:System.IO.File?displayProperty=nameWithType> 클래스의 정적 메서드 <xref:System.IO.File.ReadAllText%2A> 및 <xref:System.IO.File.ReadAllLines%2A>를 사용하여 텍스트 파일의 내용을 읽습니다.  
  
 <xref:System.IO.StreamReader>를 사용하는 예제는 [방법: 텍스트 파일을 한 번에 한 줄씩 읽기](../../../csharp/programming-guide/file-system/how-to-read-a-text-file-one-line-at-a-time.md)를 참조하세요.  
  
> [!NOTE]
>  이 예제에 사용되는 파일은 [방법: 텍스트 파일에 쓰기](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md) 항목에서 생성되었습니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[csFilesandFolders#4](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-read-from-a-text-file_1.cs)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 코드를 복사하고 C# 콘솔 응용 프로그램에 붙여넣습니다.  
  
 [방법: 텍스트 파일에 쓰기](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md)의 텍스트 파일을 사용하지 않는 경우 `ReadAllText` 및 `ReadAllLines`에 대한 인수를 사용자 컴퓨터의 적절한 경로 및 파일 이름으로 바꿉니다.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 다음 조건에서 예외가 발생합니다.  
  
-   파일이 없거나 지정된 위치에 없는 경우. 경로와 파일 이름의 철자를 확인합니다.  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 파일 이름을 사용하여 파일 내용을 확인하지 마세요. 예를 들어 `myFile.cs` 파일이 C# 소스 파일이 아닐 수도 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.IO?displayProperty=nameWithType>  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [파일 시스템 및 레지스트리(C# 프로그래밍 가이드)](../../../csharp/programming-guide/file-system/index.md)
