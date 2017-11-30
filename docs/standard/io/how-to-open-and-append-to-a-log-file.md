---
title: "방법: 로그 파일 열기 및 추가"
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
helpviewer_keywords:
- log files, opening
- streams, opening and appending to log file
- log files, appending to
- I/O [.NET Framework], log files
ms.assetid: 74423362-1721-49cb-aa0a-e04005f72a06
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 60c31339231405a1cbbb98dae37d36ad3c3709c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-open-and-append-to-a-log-file"></a>방법: 로그 파일 열기 및 추가
<xref:System.IO.StreamWriter>및 <xref:System.IO.StreamReader> 스트림에서 문자를 읽고 쓰는 문자. 다음 코드 예제에서는 열립니다는 `log.txt` 입력의 경우 파일 또는 이미 존재 하지 않는 하 고 파일의 끝에 정보를 추가 하는 경우 파일을 만듭니다. 그런 다음 파일의 내용은 표시 하기 위한 표준 출력에 기록 됩니다. 이 예제에는 대신 정보 단일 문자열이 나 문자열 배열로 저장 수 및 <xref:System.IO.File.WriteAllText%2A> 또는 <xref:System.IO.File.WriteAllLines%2A> 메서드를 사용 하 여 동일한 기능을 적용할 수 없습니다.  
  
> [!NOTE]
>  Visual Basic 사용자는 메서드 및에서 제공 하는 속성을 사용 하도록 선택할 수는 <xref:Microsoft.VisualBasic.Logging.Log> 클래스 또는 <xref:Microsoft.VisualBasic.FileIO.FileSystem> 만들거나 로그 파일에 쓸 클래스입니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source2.cs#2)]
 [!code-vb[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source2.vb#2)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.IO.StreamWriter>  
 <xref:System.IO.StreamReader>  
 <xref:System.IO.File.AppendText%2A?displayProperty=nameWithType>  
 <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
 [방법: 디렉터리 및 파일 열거](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
 [방법: 새로 만든 데이터 파일 읽기 및 쓰기](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
 [방법: 파일의 텍스트 읽기](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
 [방법: 파일에 텍스트 쓰기](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [방법: 문자열에서 문자 읽기](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
 [방법: 문자열에 문자 쓰기](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
 [파일 및 스트림 I/O](../../../docs/standard/io/index.md)
