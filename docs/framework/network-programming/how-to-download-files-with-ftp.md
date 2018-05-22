---
title: '방법: FTP를 사용하여 파일 다운로드'
ms.date: 03/30/2017
ms.assetid: 892548b8-954a-4f6a-9bca-2ae620c3700f
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: a3e0b5773a98b42411e4dd76668dafb834b5cbd3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-download-files-with-ftp"></a><span data-ttu-id="95297-102">방법: FTP를 사용하여 파일 다운로드</span><span class="sxs-lookup"><span data-stu-id="95297-102">How to: Download Files with FTP</span></span>
<span data-ttu-id="95297-103">이 샘플은 FTP 서버에서 파일을 다운로드하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="95297-103">This sample shows how to download a file from an FTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="95297-104">예</span><span class="sxs-lookup"><span data-stu-id="95297-104">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="95297-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="95297-105">Compiling the Code</span></span>  
 <span data-ttu-id="95297-106">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="95297-106">This example requires:</span></span>  
  
-   <span data-ttu-id="95297-107">**System.Net** 네임스페이스에 대한 참조.</span><span class="sxs-lookup"><span data-stu-id="95297-107">References to the **System.Net** namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="95297-108">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="95297-108">Robust Programming</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="95297-109">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="95297-109">.NET Framework Security</span></span>
