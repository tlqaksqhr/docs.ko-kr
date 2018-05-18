---
title: '방법: 새로 만든 데이터 파일 읽기 및 쓰기'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- streams, reading and writing data
- BinaryReader class, examples
- I/O [.NET Framework], reading data
- I/O [.NET Framework], writing data
- BinaryWriter class, examples
ms.assetid: e209d949-31e8-44ea-8e38-87f9093f3093
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6b854495a32755b2cbbd0421b1a45458fd2b7863
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-read-and-write-to-a-newly-created-data-file"></a>방법: 새로 만든 데이터 파일 읽기 및 쓰기
<xref:System.IO.BinaryWriter>와 <xref:System.IO.BinaryReader?displayProperty=nameWithType> 클래스는 문자열이 아닌 데이터를 쓰고 읽는 데 사용됩니다. 다음 예제에서는 `Test.data`라는 새로 만든 빈 파일 스트림에서 데이터를 읽거나 이 스트림에 데이터를 쓰는 방법을 보여 줍니다. 현재 디렉터리에 데이터 파일을 만든 후 관련된 <xref:System.IO.BinaryWriter> 및 <xref:System.IO.BinaryReader> 개체를 만들고 <xref:System.IO.BinaryWriter> 개체를 사용하여 0부터 10까지의 정수를 `Test.data`에 씁니다. 이렇게 하면 파일 포인터가 파일 끝에 옵니다. 파일 포인터를 다시 원점으로 설정하고 나면, <xref:System.IO.BinaryReader> 개체는 지정된 내용을 읽습니다.  
  
## <a name="example"></a>예  
 [!code-cpp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CPP/source6.cpp#7)]
 [!code-csharp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CS/source6.cs#7)]
 [!code-vb[System.IO.BinaryReaderWriter#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/VB/source6.vb#7)]  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 현재 디렉터리에 `Test.data`가 이미 있는 경우, <xref:System.IO.IOException> 예외가 throw됩니다. 파일 스트림을 초기화하여 예외를 throw하지 않고 항상 새 파일을 만들려면 <xref:System.IO.FileMode.Create?displayProperty=nameWithType> 파일 모드 옵션을 사용합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.IO.BinaryReader>  
 <xref:System.IO.BinaryWriter>  
 <xref:System.IO.FileStream>  
 <xref:System.IO.FileStream.Seek%2A?displayProperty=nameWithType>  
 <xref:System.IO.SeekOrigin>  
 [방법: 디렉터리 및 파일 열거](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
 [방법: 로그 파일 열기 및 추가](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
 [방법: 파일의 텍스트 읽기](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
 [방법: 파일에 텍스트 쓰기](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [방법: 문자열에서 문자 읽기](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
 [방법: 문자열에 문자 쓰기](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
 [파일 및 스트림 I/O](../../../docs/standard/io/index.md)
