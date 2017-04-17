---
title: "방법: 로그 파일 열기 및 추가 | Microsoft Docs"
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
  - "로그 파일, 열기"
  - "스트림, 로그 파일 열기 및 추가"
  - "로그 파일, 추가"
  - "I/O[.NET Framework], 로그 파일"
ms.assetid: 74423362-1721-49cb-aa0a-e04005f72a06
caps.latest.revision: 15
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: 로그 파일 열기 및 추가
<xref:System.IO.StreamWriter>와 <xref:System.IO.StreamReader>는 각각 스트림에 문자를 쓰고 스트림에서 문자를 읽습니다.  다음 코드 예제는 입력에 사용할 `log.txt` 파일을 열거나 이 파일이 없는 경우에는 새로 만들고 파일의 끝에 정보를 추가합니다.  그런 다음 표시할 표준 출력에 파일 내용을 기록합니다.  이 예제의 정보는 단일 문자열이나 문자열 배열로 저장할 수 있고 <xref:System.IO.File.WriteAllText%2A> 또는 <xref:System.IO.File.WriteAllLines%2A> 메서드를 사용하여 같은 기능을 얻을 수 있습니다.  
  
> [!NOTE]
>  Visual Basic 사용자는 로그 파일에 대한 만들기 또는 쓰기에 대해 <xref:Microsoft.VisualBasic.Logging.Log> 클래스 또는 <xref:Microsoft.VisualBasic.FileIO.FileSystem> 클래스에서 제공하는 메서드와 속성을 사용하도록 선택할 수 있습니다.  
  
## 예제  
 [!code-csharp[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source2.cs#2)]
 [!code-vb[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source2.vb#2)]  
  
## 참고 항목  
 <xref:System.IO.StreamWriter>   
 <xref:System.IO.StreamReader>   
 <xref:System.IO.File.AppendText%2A?displayProperty=fullName>   
 <xref:System.IO.File.OpenText%2A?displayProperty=fullName>   
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=fullName>   
 [방법: 디렉터리 및 파일 열거](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)   
 [방법: 새로 만든 데이터 파일 읽기 및 쓰기](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)   
 [방법: 파일의 텍스트 읽기](../../../docs/standard/io/how-to-read-text-from-a-file.md)   
 [방법: 파일에 텍스트 쓰기](../../../docs/standard/io/how-to-write-text-to-a-file.md)   
 [방법: 문자열에서 문자 읽기](../../../docs/standard/io/how-to-read-characters-from-a-string.md)   
 [방법: 문자열에 문자 쓰기](../../../docs/standard/io/how-to-write-characters-to-a-string.md)   
 [파일 및 스트림 I\/O](../../../docs/standard/io/index.md)