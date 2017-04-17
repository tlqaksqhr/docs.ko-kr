---
title: "방법: 네트워크 프로세스 간 통신에 명명된 파이프 사용 | Microsoft Docs"
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
  - "양방향 통신[.NET Framework], 명명된 파이프"
  - "가장[.NET Framework], 명명된 파이프"
  - "메시지 기반 통신[.NET Framework], 명명된 파이프"
  - "명명된 파이프를 통한 여러 연결"
  - "명명된 파이프[.NET Framework]"
  - "네트워크 통신[.NET Framework], 명명된 파이프"
  - "파이프[.NET Framework]"
ms.assetid: 4e4d7e64-9f1b-4026-98f7-20488ac7b42b
caps.latest.revision: 16
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 16
---
# 방법: 네트워크 프로세스 간 통신에 명명된 파이프 사용
명명된 파이프는 파이프 서버와 하나 이상의 파이프 클라이언트 간에 프로세스 간 통신을 제공합니다.  로컬 컴퓨터에서 프로세스 간 통신을 제공 하는 익명 파이프 보다 많은 기능을 제공 합니다.  명명된 파이프는 네트워크 및 다중 서버 인스턴스를 통한 양방향 통신, 메시지 기반 통신 및 연결 프로세스가 원격 서버에서 고유한 권한 집합을 사용할 수 있는 클라이언트 가장을 지원합니다.  
  
 명명된 파이프를 구현하려면, <xref:System.IO.Pipes.NamedPipeServerStream> 및 <xref:System.IO.Pipes.NamedPipeClientStream> 클래스를 사용합니다.  
  
## 예제  
 다음 예제에서는 <xref:System.IO.Pipes.NamedPipeServerStream> 클래스를 사용하여 명명된 파이프를 만드는 방법을 보여 줍니다.  이 예제에서 서버 프로세스는 네 개의 스레드를 만듭니다.  각 스레드는 클라이언트 연결을 받아들일 수 있습니다.  그러면 연결된 클라이언트 프로세스가 서버에 파일 이름을 제공합니다.  클라이언트에 충분한 권한이 있으면 서버 프로세스가 파일을 열고 파일의 내용을 클라이언트에 다시 보냅니다.  
  
 [!code-cpp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/vb/program.vb#01)]  
  
## 예제  
 다음 예제에서는 <xref:System.IO.Pipes.NamedPipeClientStream> 클래스를 사용하는 클라이언트 프로세스를 보여 줍니다.  클라이언트는 서버 프로세스에 연결하고 서버에 파일 이름을 보냅니다.  이 예제에서는 가장이 사용되므로 클라이언트 응용 프로그램을 실행 중인 ID에 파일에 대한 액세스 권한이 있어야 합니다.  그러면 서버가 파일의 내용을 클라이언트에 다시 보내고  이 파일 내용이 콘솔에 표시됩니다.  
  
 [!code-csharp[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/vb/program.vb#01)]  
  
## 강력한 프로그래밍  
 이 예제의 클라이언트 프로세스와 서버 프로세스는 동일한 컴퓨터에서 실행하기 위한 것이므로 <xref:System.IO.Pipes.NamedPipeClientStream> 개체에 제공되는 서버 이름은 `"."`입니다.  클라이언트 프로세스와 서버 프로세스가 서로 다른 컴퓨터에 있으면 `"."`가 서버 프로세스를 실행하는 컴퓨터의 네트워크 이름으로 바뀝니다.  
  
## 참고 항목  
 <xref:System.Security.Principal.TokenImpersonationLevel>   
 <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName%2A>   
 [파이프](../../../docs/standard/io/pipe-operations.md)   
 [방법: 로컬 프로세스 간 통신에 익명 파이프 사용](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)