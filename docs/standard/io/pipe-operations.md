---
title: ".NET Framework의 파이프 작업 | Microsoft Docs"
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
  - "파이프[.NET Framework]"
  - "파이프 작업[.NET Framework]"
  - "프로세스 간 통신[.NET Framework], 파이프"
  - "I/O[.NET Framework], 파이프"
ms.assetid: 7b964ebd-7a4f-4d28-8194-7841f9e4c702
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# .NET Framework의 파이프 작업
파이프는 프로세스 간 통신을 가능하게 하는 수단을 제공합니다.  파이프 형식에는 다음과 같은 두 가지가 있습니다.  
  
-   익명 파이프  
  
     익명 파이프는 로컬 컴퓨터에서 프로세스 간 통신을 제공합니다.  익명 파이프는 명명된 파이프보다 적은 오버헤드를 필요로 하지만 제한된 서비스를 제공합니다.  익명 파이프는 단방향으로 되어 있으면 네트워크를 통해 사용할 수 없습니다.  익명 파이프는 하나의 서버 인스턴스만 지원합니다.  익명 파이프는 스레드 간 통신이나 자식 프로세스가 만들어지면 파이프 핸들을 이 자식 프로세스에 손쉽게 전달할 수 있는 부모 프로세스와 자식 프로세스 간 통신에 유용합니다.  
  
     .NET Framework에서, <xref:System.IO.Pipes.AnonymousPipeServerStream> 및 <xref:System.IO.Pipes.AnonymousPipeClientStream> 클래스를 사용하여 익명 파이프를 구현합니다.  
  
     [방법: 로컬 프로세스 간 통신에 익명 파이프 사용](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)를 참조하십시오.  
  
-   명명된 파이프  
  
     명명된 파이프는 파이프 서버와 하나 이상의 파이프 클라이언트 간에 프로세스 간 통신을 제공합니다.  명명 파이프는 단방향 또는 양방향일 수 있습니다.  명명된 파이프는 메시지 기반 통신을 지원하고 여러 클라이언트가 동일한 파이프 이름을 사용하여 서버 프로세스에 동시에 연결할 수 있도록 합니다.  또한 명명된 파이프는 연결 프로세스가 원격 서버에서 고유한 권한을 사용할 수 있는 가장을 지원합니다.  
  
     .NET Framework에서, <xref:System.IO.Pipes.NamedPipeServerStream> 및 <xref:System.IO.Pipes.NamedPipeClientStream> 클래스를 사용하여 명명된 파이프를 구현합니다.  
  
     [방법: 네트워크 프로세스 간 통신에 명명된 파이프 사용](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md)를 참조하십시오.  
  
## 참고 항목  
 [파일 및 스트림 I\/O](../../../docs/standard/io/index.md)   
 [방법: 로컬 프로세스 간 통신에 익명 파이프 사용](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)   
 [방법: 네트워크 프로세스 간 통신에 명명된 파이프 사용](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md)