---
title: "스트림 작성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- streams, base streams
- I/O [.NET Framework], composing streams
- Stream class, composing streams
- base streams
- streams, backing stores
ms.assetid: da761658-a535-4f26-a452-b30df47f73d5
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 75800210a52620c5b08a01c5f8fa888bf40843fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="composing-streams"></a>스트림 작성
백업 저장소는 디스크 또는 메모리와 같은 저장소 미디어입니다. 각각의 백업 저장소의 구현으로 자체 스트림을 구현는 <xref:System.IO.Stream> 클래스입니다. 각 스트림 형식을 읽고과 지정 된 백업 저장소 바이트를 씁니다. 백업 저장소에 연결 하는 스트림의 기본 스트림 라고 합니다. 기본 스트림 백업 저장소에 스트림을 연결 하는 데 필요한 매개 변수가 있는 생성자가 있는 합니다. 예를 들어 <xref:System.IO.FileStream> 프로세스, 및 등의 파일을 공유 하는 방법을 지정 하는 경로 매개 변수를 지정 하는 생성자가 있습니다.  
  
 디자인은 <xref:System.IO> 간소화 된 스트림을 작성할 클래스를 제공 합니다. 기본 스트림 원하는 기능을 제공 하는 통과 스트림을 하나 이상 연결할 수 있습니다. 판독기 또는 작성기 기본 유형 읽거나 쉽게 쓸 수 있도록 체인의 끝에 연결할 수 있습니다.  
  
 다음 코드 예제에서는 한 **FileStream** 기존 주위 `MyFile.txt` 버퍼로 순서로 `MyFile.txt`합니다. (유의 **FileStreams** 기본적으로 버퍼링 됩니다.) 다음으로 <xref:System.IO.StreamReader> 에서 문자를 읽으려면 만들어집니다는 **FileStream**로 전달 되는 **StreamReader** 생성자 인수로 합니다. <xref:System.IO.StreamReader.ReadLine%2A>될 때까지 읽습니다 <xref:System.IO.StreamReader.Peek%2A> 문자가 더 이상 찾습니다.  
  
 [!code-cpp[System.IO.StreamReader#20](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source2.cpp#20)]
 [!code-csharp[System.IO.StreamReader#20](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source2.cs#20)]
 [!code-vb[System.IO.StreamReader#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source2.vb#20)]  
  
 다음 코드 예제에서는 한 **FileStream** 기존 주위 `MyFile.txt` 버퍼로 순서로 `MyFile.txt`합니다. (유의 **FileStreams** 기본적으로 버퍼링 됩니다.) 다음으로 **BinaryReader** 에서 바이트를 읽으려고 만들어집니다는 **FileStream**로 전달 되는 **BinaryReader** 생성자 인수로 합니다. <xref:System.IO.BinaryReader.ReadByte%2A>될 때까지 읽습니다 <xref:System.IO.BinaryReader.PeekChar%2A> 추가 바이트를 찾습니다.  
  
 [!code-cpp[System.IO.StreamReader#21](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source3.cpp#21)]
 [!code-csharp[System.IO.StreamReader#21](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source3.cs#21)]
 [!code-vb[System.IO.StreamReader#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source3.vb#21)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.IO.StreamReader>  
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
 <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType>  
 <xref:System.IO.FileStream>  
 <xref:System.IO.BinaryReader>  
 <xref:System.IO.BinaryReader.ReadByte%2A?displayProperty=nameWithType>  
 <xref:System.IO.BinaryReader.PeekChar%2A?displayProperty=nameWithType>
