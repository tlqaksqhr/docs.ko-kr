---
title: ".NET Framework의 파이프 작업"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipes [.NET Framework]
- pipe operations [.NET Framework]
- interprocess communication [.NET Framework], pipes
- I/O [.NET Framework], pipes
ms.assetid: 7b964ebd-7a4f-4d28-8194-7841f9e4c702
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 879e5a73417f9347224bc22b397814b83972751c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="pipe-operations-in-the-net-framework"></a><span data-ttu-id="fced7-102">.NET Framework의 파이프 작업</span><span class="sxs-lookup"><span data-stu-id="fced7-102">Pipe Operations in the .NET Framework</span></span>
<span data-ttu-id="fced7-103">파이프는 프로세스 간 통신 수단을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fced7-103">Pipes provide a means for interprocess communication.</span></span> <span data-ttu-id="fced7-104">파이프는 다음과 같은 두 종류가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fced7-104">There are two types of pipes:</span></span>  
  
-   <span data-ttu-id="fced7-105">익명 파이프 합니다.</span><span class="sxs-lookup"><span data-stu-id="fced7-105">Anonymous pipes.</span></span>  
  
     <span data-ttu-id="fced7-106">익명 파이프는 로컬 컴퓨터에서 프로세스 간 통신을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fced7-106">Anonymous pipes provide interprocess communication on a local computer.</span></span> <span data-ttu-id="fced7-107">익명 파이프 명명 된 파이프 보다 적은 오버 헤드를 필요로 하지만 제한 된 서비스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fced7-107">Anonymous pipes require less overhead than named pipes but offer limited services.</span></span> <span data-ttu-id="fced7-108">익명 파이프는 단방향 및 네트워크를 통해 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fced7-108">Anonymous pipes are one-way and cannot be used over a network.</span></span> <span data-ttu-id="fced7-109">단일 서버 인스턴스 하나만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="fced7-109">They support only a single server instance.</span></span> <span data-ttu-id="fced7-110">익명 파이프는를 파이프 핸들 쉽게 전달할 수 있습니다는 자식 프로세스에 생성 될 때 부모 및 자식 프로세스 또는 스레드 간에 통신 하는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fced7-110">Anonymous pipes are useful for communication between threads, or between parent and child processes where the pipe handles can be easily passed to the child process when it is created.</span></span>  
  
     <span data-ttu-id="fced7-111">.NET Framework에서는 <xref:System.IO.Pipes.AnonymousPipeServerStream> 및 <xref:System.IO.Pipes.AnonymousPipeClientStream> 클래스를 사용하여 익명 파이프를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="fced7-111">In the .NET Framework, you implement anonymous pipes by using the <xref:System.IO.Pipes.AnonymousPipeServerStream> and <xref:System.IO.Pipes.AnonymousPipeClientStream> classes.</span></span>  
  
     <span data-ttu-id="fced7-112">참조 [하는 방법: 로컬 프로세스 간 통신에 대 한 익명 파이프를 사용 하 여](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fced7-112">See [How to: Use Anonymous Pipes for Local Interprocess Communication](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md).</span></span>  
  
-   <span data-ttu-id="fced7-113">명명 된 파이프 합니다.</span><span class="sxs-lookup"><span data-stu-id="fced7-113">Named pipes.</span></span>  
  
     <span data-ttu-id="fced7-114">명명 된 파이프 파이프 서버와 하나 이상의 파이프 클라이언트 간의 통신을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fced7-114">Named pipes provide interprocess communication between a pipe server and one or more pipe clients.</span></span> <span data-ttu-id="fced7-115">명명 된 파이프는 단방향 또는 양방향일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fced7-115">Named pipes can be one-way or duplex.</span></span> <span data-ttu-id="fced7-116">이들은 메시지 기반 통신을 지원 하며 여러 클라이언트가 동시에 같은 파이프 이름을 사용 하 여 서버 프로세스에 연결할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fced7-116">They support message-based communication and allow multiple clients to connect simultaneously to the server process using the same pipe name.</span></span> <span data-ttu-id="fced7-117">또한 명명 된 파이프 연결 프로세스가 원격 서버에 직접 사용 권한을 사용 하도록 하는 가장을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="fced7-117">Named pipes also support impersonation, which enables connecting processes to use their own permissions on remote servers.</span></span>  
  
     <span data-ttu-id="fced7-118">.NET Framework에서는 <xref:System.IO.Pipes.NamedPipeServerStream> 및 <xref:System.IO.Pipes.NamedPipeClientStream> 클래스를 사용하여 명명된 파이프를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="fced7-118">In the .NET Framework, you implement named pipes by using the <xref:System.IO.Pipes.NamedPipeServerStream> and <xref:System.IO.Pipes.NamedPipeClientStream> classes.</span></span>  
  
     <span data-ttu-id="fced7-119">참조 [하는 방법: 네트워크 프로세스 간 통신에 대 한 명명 된 파이프를 사용 하 여](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fced7-119">See [How to: Use Named Pipes for Network Interprocess Communication](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fced7-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fced7-120">See Also</span></span>  
 [<span data-ttu-id="fced7-121">파일 및 스트림 I/O</span><span class="sxs-lookup"><span data-stu-id="fced7-121">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)  
 [<span data-ttu-id="fced7-122">방법: 로컬 프로세스 간 통신에 익명 파이프 사용</span><span class="sxs-lookup"><span data-stu-id="fced7-122">How to: Use Anonymous Pipes for Local Interprocess Communication</span></span>](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)  
 [<span data-ttu-id="fced7-123">방법: 네트워크 프로세스 간 통신에 명명된 파이프 사용</span><span class="sxs-lookup"><span data-stu-id="fced7-123">How to: Use Named Pipes for Network Interprocess Communication</span></span>](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md)
