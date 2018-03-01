---
title: "방법: 인터페이스 및 프로토콜 정보 가져오기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Network
ms.assetid: fd88d26c-4063-495e-a253-736ac3e6b23f
caps.latest.revision: 
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: 20bee2f0d6821c8abec08231e9ab0b8fdb211854
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-get-interface-and-protocol-information"></a><span data-ttu-id="c7878-102">방법: 인터페이스 및 프로토콜 정보 가져오기</span><span class="sxs-lookup"><span data-stu-id="c7878-102">How to: Get Interface and Protocol Information</span></span>
<span data-ttu-id="c7878-103">이 샘플은 네트워크 인터페이스의 TCP 통계를 읽는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c7878-103">This sample shows how to read the TCP statistics of a network interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7878-104">예</span><span class="sxs-lookup"><span data-stu-id="c7878-104">Example</span></span>  
  
```  
public static void ShowTcpStatistics(NetworkInterfaceComponent version)  
{  
    IPGlobalProperties properties =  
          IPGlobalProperties.GetIPGlobalProperties();  
    TcpStatistics tcpstat = null;  
    Console.WriteLine("");  
    switch (version)  
    {  
        case NetworkInterfaceComponent.IPv4:  
             tcpstat = properties.GetTcpIPv4Statistics();  
            Console.WriteLine("TCP/IPv4 Statistics:");  
            break;  
        case NetworkInterfaceComponent.IPv6:  
            tcpstat = properties.GetTcpIPv6Statistics();  
            Console.WriteLine("TCP/IPv6 Statistics:");  
            break;  
        default:  
            throw new ArgumentException("version");  
            break;  
    }  
    Console.WriteLine("  Minimum Transmission Timeout. : {0}",   
        tcpstat.MinimumTransmissionTimeout);  
    Console.WriteLine("  Maximum Transmission Timeout. : {0}",   
        tcpstat.MaximumTransmissionTimeout);  
  
    Console.WriteLine("  Connection Data:");  
    Console.WriteLine("      Current : {0}",   
    tcpstat.CurrentConnections);  
    Console.WriteLine("      Cumulative : {0}",   
        tcpstat.CumulativeConnections);  
    Console.WriteLine("      Initiated  : {0}",   
        tcpstat.ConnectionsInitiated);  
    Console.WriteLine("      Accepted : {0}",   
        tcpstat.ConnectionsAccepted);  
    Console.WriteLine("      Failed Attempts : {0}",   
        tcpstat.FailedConnectionAttempts);  
    Console.WriteLine("      Reset : {0}",   
        tcpstat.ResetConnections);  
  
    Console.WriteLine("");  
    Console.WriteLine("  Segment Data:");  
    Console.WriteLine("      Received  ................... : {0}",   
        tcpstat.SegmentsReceived);  
    Console.WriteLine("      Sent : {0}",   
        tcpstat.SegmentsSent);  
    Console.WriteLine("      Retransmitted : {0}",   
        tcpstat.SegmentsResent);  
  
    Console.WriteLine("");  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c7878-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="c7878-105">Compiling the Code</span></span>  
 <span data-ttu-id="c7878-106">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c7878-106">This example requires:</span></span>  
  
-   <span data-ttu-id="c7878-107">**System.Net** 네임스페이스에 대한 참조.</span><span class="sxs-lookup"><span data-stu-id="c7878-107">References to the **System.Net** namespace.</span></span>
