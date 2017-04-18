---
title: "방법: 로컬 프로세스 간 통신에 익명 파이프 사용 | Microsoft Docs"
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
  - "익명 파이프[.NET Framework]"
  - "로컬 컴퓨터 통신[.NET Framework], 파이프"
  - "단방향 통신[.NET Framework]"
  - "부모-자식 통신[.NET Framework]"
  - "파이프[.NET Framework]"
ms.assetid: e7773c77-c646-4a01-8a96-a003d59fc4c9
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: 로컬 프로세스 간 통신에 익명 파이프 사용
익명 파이프는 로컬 컴퓨터에서 프로세스 간 통신을 제공합니다.  이것은 명명된 파이프보다 적은 기능을 제공하지만 오버로드를 더 적게 필요로 합니다.  익명 파이프를 사용하면 로컬 컴퓨터에서 프로세스 간 통신을 보다 쉽게 수행할 수 있습니다.  네트워크를 통한 통신에는 익명 파이프를 사용할 수 없습니다.  
  
 익명 파이프를 구현하려면, <xref:System.IO.Pipes.AnonymousPipeServerStream> 및 <xref:System.IO.Pipes.AnonymousPipeClientStream> 클래스를 사용합니다.  
  
## 예제  
 다음 예제에서는 익명 파이프를 사용하여 부모 프로세스에서 자식 프로세스로 문자열을 보내는 방법을 보여 줍니다.  이 예제에서는 <xref:System.IO.Pipes.PipeDirection> 값 <xref:System.IO.Pipes.PipeDirection>을 사용하여 부모 프로세스에 <xref:System.IO.Pipes.AnonymousPipeServerStream> 개체를 만듭니다.  그러면 부모 프로세스는 클라이언트 핸들을 통해 <xref:System.IO.Pipes.AnonymousPipeClientStream> 개체를 만들어 자식 프로세스를 만듭니다.  자식 프로세스는 <xref:System.IO.Pipes.PipeDirection>의 값으로 <xref:System.IO.Pipes.PipeDirection>을 갖습니다.  
  
 다음으로 부모 프로세스는 자식 프로세스에 사용자 제공 문자열을 보냅니다.  이 문자열은 자식 프로세스의 콘솔에 표시됩니다.  
  
 다음 예제에서는 서버 프로세스를 보여 줍니다.  
  
 [!code-cpp[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/vb/program.vb#01)]  
  
## 예제  
 다음 예제에서는 클라이언트 프로세스를 보여 줍니다.  서버 프로세스는 클라이언트 프로세스를 시작하고 클라이언트 핸들에 이 프로세스를 제공합니다.  서버 프로세스를 실행하기 전에 클라이언트 코드의 결과로 생성된 실행 파일에 `pipeClient.exe`라는 이름을 지정하고 이 파일을 서버 실행 파일과 같은 디렉터리에 복사해야 합니다.  
  
 [!code-cpp[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/vb/program.vb#01)]  
  
## 참고 항목  
 [파이프](../../../docs/standard/io/pipe-operations.md)   
 [방법: 네트워크 프로세스 간 통신에 명명된 파이프 사용](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md)