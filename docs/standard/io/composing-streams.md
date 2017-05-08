---
title: "스트림 작성 | Microsoft Docs"
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
  - "스트림, 기본 스트림"
  - "I/O[.NET Framework], 스트림 작성"
  - "스트림 클래스, 스트림 작성"
  - "기본 스트림"
  - "스트림, 백업 저장소"
ms.assetid: da761658-a535-4f26-a452-b30df47f73d5
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 10
---
# 스트림 작성
백업 저장소는 디스크나 메모리 같은 저장 미디어입니다.  각각의 백업 저장소는 <xref:System.IO.Stream> 클래스를 구현하는 방식으로 자신의 고유 스트림을 구현합니다.  각 스트림 형식은 지정된 백업 저장소에서 바이트를 읽고 이 저장소에 바이트를 씁니다.  백업 저장소에 연결되는 스트림을 기본 스트림이라고 합니다.  기본 스트림은 백업 저장소에 스트림을 연결하는 데 필요한 매개 변수를 사용하는 생성자를 가집니다.  예를 들어, <xref:System.IO.FileStream>은 프로세스에서 파일을 공유하는 방법 등을 지정하는 경로 매개 변수를 지정하는 생성자를 가집니다.  
  
 <xref:System.IO> 클래스 디자인을 사용하여 간소화된 스트림을 작성할 수 있습니다.  원하는 기능을 제공하는 하나 이상의 통과 스트림에 기본 스트림을 추가할 수 있으며  원하는 형식을 손쉽게 읽거나 쓸 수 있도록 체인의 끝에 판독기 또는 작성기를 추가할 수 있습니다.  
  
 다음 코드 예제에서는 `MyFile.txt`를 버퍼링하기 위해 기존의 `MyFile.txt`에 **FileStream**을 만듭니다. **FileStreams**는 기본적으로 버퍼링됩니다. 그런 다음 <xref:System.IO.StreamReader>를 만들어 **StreamReader**에 생성자 인수로 전달되는 **FileStream**에서 문자를 읽습니다.  <xref:System.IO.StreamReader.ReadLine%2A>은 <xref:System.IO.StreamReader.Peek%2A>가 더 이상 문자를 찾을 수 없을 때까지 읽습니다.  
  
 [!code-cpp[System.IO.StreamReader#20](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source2.cpp#20)]
 [!code-csharp[System.IO.StreamReader#20](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source2.cs#20)]
 [!code-vb[System.IO.StreamReader#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source2.vb#20)]  
  
 다음 코드 예제에서는 `MyFile.txt`를 버퍼링하기 위해 기존의 `MyFile.txt`에 **FileStream**을 만듭니다. **FileStreams**는 기본적으로 버퍼링됩니다. 그런 다음 **BinaryReader**를 만들어 **BinaryReader**에 생성자 인수로 전달되는 **FileStream**에서 바이트를 읽습니다.  <xref:System.IO.BinaryReader.ReadByte%2A>는 <xref:System.IO.BinaryReader.PeekChar%2A>가 바이트를 더 이상 찾을 수 없을 때까지 읽습니다.  
  
 [!code-cpp[System.IO.StreamReader#21](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source3.cpp#21)]
 [!code-csharp[System.IO.StreamReader#21](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source3.cs#21)]
 [!code-vb[System.IO.StreamReader#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source3.vb#21)]  
  
## 참고 항목  
 <xref:System.IO.StreamReader>   
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=fullName>   
 <xref:System.IO.StreamReader.Peek%2A?displayProperty=fullName>   
 <xref:System.IO.FileStream>   
 <xref:System.IO.BinaryReader>   
 <xref:System.IO.BinaryReader.ReadByte%2A?displayProperty=fullName>   
 <xref:System.IO.BinaryReader.PeekChar%2A?displayProperty=fullName>