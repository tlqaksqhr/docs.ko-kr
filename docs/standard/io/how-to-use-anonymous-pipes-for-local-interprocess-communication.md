---
title: "방법: 로컬 프로세스 간 통신에 익명 파이프 사용"
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
- anonymous pipes [.NET Framework]
- parent-child communication [.NET Framework]
- pipes [.NET Framework]
- one-way communication [.NET Framework]
- local computer communication [.NET Framework], pipes
ms.assetid: e7773c77-c646-4a01-8a96-a003d59fc4c9
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f457cc91e6fbfc118e5363d1b0a8e8c2ad800748
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-anonymous-pipes-for-local-interprocess-communication"></a>방법: 로컬 프로세스 간 통신에 익명 파이프 사용
익명 파이프는 로컬 컴퓨터에서 프로세스 간 통신을 제공합니다. 명명된 파이프보다 적은 기능을 제공하지만 오버로드를 더 적게 필요로 합니다. 프로세스 간 통신 로컬 컴퓨터에 쉽게 수행할 수 있도록 익명 파이프를 사용할 수 있습니다. 네트워크를 통한 통신에 대 한 익명 파이프를 사용할 수 없습니다.  
  
 익명 파이프를 구현하려면, <xref:System.IO.Pipes.AnonymousPipeServerStream> 및 <xref:System.IO.Pipes.AnonymousPipeClientStream> 클래스를 사용합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 익명 파이프를 사용 하는 자식 프로세스에는 부모 프로세스에서 문자열을 보내는 방법을 보여 줍니다. 이 예제에서는 만듭니다는 <xref:System.IO.Pipes.AnonymousPipeServerStream> 인 부모 프로세스의 개체는 <xref:System.IO.Pipes.PipeDirection> 값 <xref:System.IO.Pipes.PipeDirection.Out>합니다. 부모 프로세스를 만들려면 클라이언트 핸들을 사용 하 여 다음는 자식 프로세스를 생성 한 <xref:System.IO.Pipes.AnonymousPipeClientStream> 개체입니다. 자식 프로세스에는 <xref:System.IO.Pipes.PipeDirection> 값 <xref:System.IO.Pipes.PipeDirection.In>합니다.  
  
 그런 다음 부모 프로세스는 자식 프로세스에는 사용자가 제공한 문자열을 보냅니다. 문자열은 자식 프로세스에서 콘솔에 표시 됩니다.  
  
 다음 예제에서는 서버 프로세스를 보여 줍니다.  
  
 [!code-cpp[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/vb/program.vb#01)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 클라이언트 프로세스를 보여 줍니다. 서버 프로세스가 클라이언트 프로세스를 시작 하 고 클라이언트 핸들이 프로세스를 제공 합니다. 클라이언트 코드에서 결과 실행 파일 이름을 지정 해야 `pipeClient.exe` 서버 프로세스를 실행 하기 전에 실행 되는 서버와 동일한 디렉터리에 복사 됩니다.  
  
 [!code-cpp[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/vb/program.vb#01)]  
  
## <a name="see-also"></a>참고 항목  
 [파이프](../../../docs/standard/io/pipe-operations.md)  
 [방법: 네트워크 프로세스 간 통신에 명명된 파이프 사용](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md)
