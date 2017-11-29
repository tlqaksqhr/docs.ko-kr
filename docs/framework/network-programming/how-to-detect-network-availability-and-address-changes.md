---
title: "방법: 네트워크 가용성 및 주소 변경 검색"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Network
ms.assetid: d4377115-4a76-4848-ab23-4898d65c771c
caps.latest.revision: "4"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 68d21502b9033b4102c22fb4e0ea10a031e2e7cb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-detect-network-availability-and-address-changes"></a><span data-ttu-id="c225c-102">방법: 네트워크 가용성 및 주소 변경 검색</span><span class="sxs-lookup"><span data-stu-id="c225c-102">How to: Detect Network Availability and Address Changes</span></span>
<span data-ttu-id="c225c-103">이 샘플은 인터페이스에서 네트워크 주소의 변경 내용을 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c225c-103">This sample shows how to detect changes in the network address of an interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c225c-104">예제</span><span class="sxs-lookup"><span data-stu-id="c225c-104">Example</span></span>  
  
```  
using System;  
using System.Net;  
using System.Net.NetworkInformation;  
  
namespace Examples.Net.AddressChanges  
{  
    public class NetworkingExample  
    {  
        public static void Main()  
        {  
            NetworkChange.NetworkAddressChanged += new   
             NetworkAddressChangedEventHandler(AddressChangedCallback);  
            Console.WriteLine("Listening for address changes. Press any key to exit.");  
            Console.ReadLine();  
        }  
        static void AddressChangedCallback(object sender, EventArgs e)  
        {  
  
            NetworkInterface[] adapters = NetworkInterface.GetAllNetworkInterfaces();  
            foreach(NetworkInterface n in adapters)  
            {  
                Console.WriteLine("   {0} is {1}", n.Name, n.OperationalStatus);  
            }  
        }  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c225c-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="c225c-105">Compiling the Code</span></span>  
 <span data-ttu-id="c225c-106">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c225c-106">This example requires:</span></span>  
  
-   <span data-ttu-id="c225c-107">**System.Net** 네임스페이스에 대한 참조.</span><span class="sxs-lookup"><span data-stu-id="c225c-107">References to the **System.Net** namespace.</span></span>
