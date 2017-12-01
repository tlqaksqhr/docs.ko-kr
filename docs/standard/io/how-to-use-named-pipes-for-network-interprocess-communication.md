---
title: "방법: 네트워크 프로세스 간 통신에 명명된 파이프 사용"
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
- message-based communication [.NET Framework], named pipes
- named pipes [.NET Framework]
- pipes [.NET Framework]
- multiple connections via named pipes
- network communications [.NET Framework], named pipes
- impersonation [.NET Framework], named pipes
- full duplex communcation [.NET Framework], named pipes
ms.assetid: 4e4d7e64-9f1b-4026-98f7-20488ac7b42b
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 952600e71311184c4a4f906734addbf335d0358a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-named-pipes-for-network-interprocess-communication"></a>방법: 네트워크 프로세스 간 통신에 명명된 파이프 사용
명명 된 파이프 파이프 서버와 하나 이상의 파이프 클라이언트 간의 통신을 제공합니다. 로컬 컴퓨터에서 프로세스 간 통신을 제공하는 익명 파이프보다 많은 기능을 제공합니다. 명명된 파이프는 네트워크 및 다중 서버 인스턴스를 통한 양방향 통신, 메시지 기반 통신 및 연결 프로세스가 원격 서버에서 고유한 권한 집합을 사용할 수 있는 클라이언트 가장을 지원합니다.  
  
 명명된 파이프를 구현하려면, <xref:System.IO.Pipes.NamedPipeServerStream> 및 <xref:System.IO.Pipes.NamedPipeClientStream> 클래스를 사용합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 사용 하 여 명명 된 파이프를 만들 수는 <xref:System.IO.Pipes.NamedPipeServerStream> 클래스입니다. 이 예제에서는 서버 프로세스는 4 개의 스레드를 만듭니다. 각 스레드에 대 한 클라이언트 연결을 사용할 수 있습니다. 연결 된 클라이언트 프로세스 파일 이름 사용 하 여 서버를 제공합니다. 클라이언트에 충분 한 권한이 있으면 서버 프로세스에서 파일을 열고 해당 내용을 다시 클라이언트로 보냅니다.  
  
 [!code-cpp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/vb/program.vb#01)]  
  
## <a name="example"></a>예제  
 다음 예에서는 사용 하는 클라이언트 프로세스는 <xref:System.IO.Pipes.NamedPipeClientStream> 클래스입니다. 클라이언트는 서버 프로세스에 연결 하 고 서버에 파일 이름을 보냅니다. 이 예제에서는 가장이 사용 되므로 클라이언트 응용 프로그램이 실행 중인 id는 파일에 액세스할 수 있는 권한이 있어야 합니다. 서버는 파일의 내용을 다시 클라이언트에 보냅니다. 그러면 파일 내용은 콘솔에 표시 됩니다.  
  
 [!code-csharp[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/vb/program.vb#01)]  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 이 예제에서 클라이언트 및 서버 프로세스에 서버 이름을 제공 하므로 동일한 컴퓨터에서 실행 되도록 설계 되었습니다는 <xref:System.IO.Pipes.NamedPipeClientStream> 개체가 `"."`합니다. 클라이언트 및 서버 프로세스 별도 컴퓨터에 있으면 `"."` 는 서버 프로세스를 실행 하는 컴퓨터의 네트워크 이름으로 대체 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Security.Principal.TokenImpersonationLevel>  
 <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName%2A>  
 [파이프](../../../docs/standard/io/pipe-operations.md)  
 [방법: 로컬 프로세스 간 통신에 익명 파이프 사용](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)
