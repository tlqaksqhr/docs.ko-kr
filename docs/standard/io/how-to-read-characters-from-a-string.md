---
title: "방법: 문자열에서 문자 읽기 | Microsoft Docs"
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
  - "문자열에서 문자 읽기"
  - "데이터 스트림, 문자열에서 문자 읽기"
  - "I/O[.NET Framework], 문자열에서 문자 읽기"
  - "데이터 읽기, 문자열"
  - "스트림, 문자열에서 문자 읽기"
ms.assetid: 27ea5e52-6db8-42d8-980a-50bcfc7fd270
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: 문자열에서 문자 읽기
다음 코드 예제에서는 문자열에서 문자를 동기적 및 비동기적으로 읽는 방법을 보여 줍니다.  
  
## 예제  
 이 예제에서는 문자열에서 동기적으로 13 문자 배열을 읽고 그들을 배열에 저장 및 해당 문자를 표시 합니다.  문자열의 나머지 문자를 읽고, 여섯 번째 요소부터 시작하여 배열에 저장하고 배열의 내용이 표시 됩니다.  
  
 [!code-cpp[Conceptual.StringReader#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.stringreader/cpp/source.cpp#1)]
 [!code-csharp[Conceptual.StringReader#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source.cs#1)]
 [!code-vb[Conceptual.StringReader#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source.vb#1)]  
  
## 예제  
 다음 예제에서는 모든 문자를 비동기적으로 <xref:System.Windows.Controls.TextBox> 컨트롤에서 읽고, 배열에 저장 합니다.  각 문자 또는 공백 문자 뒤에 줄 바꿈을 하는 별도 줄에 있는 <xref:System.Windows.Controls.TextBlock> 컨트롤을 비동기적으로 씁니다.  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source2.cs#2)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source2.vb#2)]  
  
## 참고 항목  
 <xref:System.IO.StringReader>   
 <xref:System.IO.StringReader.Read%2A?displayProperty=fullName>   
 [비동기 파일 I\/O](../../../docs/standard/io/비동기-파일-i-o.md)   
 [NIB: How to: Create a Directory Listing](http://msdn.microsoft.com/ko-kr/4d2772b1-b991-4532-a8a6-6ef733277e69)   
 [방법: 새로 만든 데이터 파일 읽기 및 쓰기](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)   
 [방법: 로그 파일 열기 및 추가](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)   
 [방법: 파일의 텍스트 읽기](../../../docs/standard/io/how-to-read-text-from-a-file.md)   
 [방법: 파일에 텍스트 쓰기](../../../docs/standard/io/how-to-write-text-to-a-file.md)   
 [방법: 문자열에 문자 쓰기](../../../docs/standard/io/how-to-write-characters-to-a-string.md)   
 [파일 및 스트림 I\/O](../../../docs/standard/io/index.md)