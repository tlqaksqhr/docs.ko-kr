---
title: "방법: FTP를 사용하여 파일 다운로드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 892548b8-954a-4f6a-9bca-2ae620c3700f
caps.latest.revision: "5"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 6309bf4885b7a0f2ab7cedfb48af70dc76bf31f4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-download-files-with-ftp"></a><span data-ttu-id="68b4d-102">방법: FTP를 사용하여 파일 다운로드</span><span class="sxs-lookup"><span data-stu-id="68b4d-102">How to: Download Files with FTP</span></span>
<span data-ttu-id="68b4d-103">이 샘플은 FTP 서버에서 파일을 다운로드하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="68b4d-103">This sample shows how to download a file from an FTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="68b4d-104">예</span><span class="sxs-lookup"><span data-stu-id="68b4d-104">Example</span></span>  
  
```csharp  
using System;  
using System.IO;  
using System.Net;  
using System.Text;  
  
namespace Examples.System.Net  
{  
    public class WebRequestGetExample  
    {  
        public static void Main ()  
        {  
            // Get the object used to communicate with the server.  
            FtpWebRequest request = (FtpWebRequest)WebRequest.Create("ftp://www.contoso.com/test.htm");  
            request.Method = WebRequestMethods.Ftp.DownloadFile;  
  
            // This example assumes the FTP site uses anonymous logon.  
            request.Credentials = new NetworkCredential ("anonymous","janeDoe@contoso.com");  
  
            FtpWebResponse response = (FtpWebResponse)request.GetResponse();  
  
            Stream responseStream = response.GetResponseStream();  
            StreamReader reader = new StreamReader(responseStream);  
            Console.WriteLine(reader.ReadToEnd());  
  
            Console.WriteLine("Download Complete, status {0}", response.StatusDescription);  
  
            reader.Close();  
            response.Close();    
        }  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="68b4d-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="68b4d-105">Compiling the Code</span></span>  
 <span data-ttu-id="68b4d-106">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="68b4d-106">This example requires:</span></span>  
  
-   <span data-ttu-id="68b4d-107">**System.Net** 네임스페이스에 대한 참조.</span><span class="sxs-lookup"><span data-stu-id="68b4d-107">References to the **System.Net** namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="68b4d-108">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="68b4d-108">Robust Programming</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="68b4d-109">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="68b4d-109">.NET Framework Security</span></span>
